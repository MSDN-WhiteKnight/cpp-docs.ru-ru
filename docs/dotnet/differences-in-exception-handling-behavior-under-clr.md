---
title: Различия в поведении в - CLR при обработке исключений
ms.date: 11/04/2016
helpviewer_keywords:
- EXCEPTION_CONTINUE_EXECUTION macro
- set_se_translator function
ms.assetid: 2e7e8daf-d019-44b0-a51c-62d7aaa89104
ms.openlocfilehash: 4898ff7893ec327495e757f2ffa0eb37ae051875
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551337"
---
# <a name="differences-in-exception-handling-behavior-under-clr"></a>Различия в поведении при обработке исключений в /CLR

[Основные понятия в использование управляемых исключений](../dotnet/basic-concepts-in-using-managed-exceptions.md) Описание обработки исключений в управляемых приложениях. В этом разделе подробно обсуждаются отличия от стандартного поведения обработки исключений и некоторые ограничения. Дополнительные сведения см. в разделе [_set_se_translator функция](../c-runtime-library/reference/set-se-translator.md).

##  <a name="vcconjumpingoutofafinallyblock"></a> Выход из блока Finally

В машинном коде C/C++, переход из __**наконец** блок, с помощью структурированной обработки исключений (SEH) допускается в том случае, несмотря на то, что он выдает предупреждение.  В разделе [/CLR](../build/reference/clr-common-language-runtime-compilation.md), выход из **наконец** блок вызывает ошибку:

```cpp
// clr_exception_handling_4.cpp
// compile with: /clr
int main() {
   try {}
   finally {
      return 0;   // also fails with goto, break, continue
    }
}   // C3276
```

##  <a name="vcconraisingexceptionswithinanexceptionfilter"></a> Создание исключений в фильтре исключений

Когда возникает исключение во время обработки [фильтра исключений](../cpp/writing-an-exception-filter.md) управляемого кода, исключение перехватывается и считается, что фильтр возвращает значение 0.

Это отличается от поведения в машинном коде, где вложенное исключение возникает, **ExceptionRecord** в **EXCEPTION_RECORD** структуры (возвращенная [ GetExceptionInformation](/windows/desktop/Debug/getexceptioninformation)) имеет значение и **ExceptionFlags** поле устанавливает бит 0x10. В следующем примере демонстрируется это различие в поведении:

```cpp
// clr_exception_handling_5.cpp
#include <windows.h>
#include <stdio.h>
#include <assert.h>

#ifndef false
#define false 0
#endif

int *p;

int filter(PEXCEPTION_POINTERS ExceptionPointers) {
   PEXCEPTION_RECORD ExceptionRecord =
                     ExceptionPointers->ExceptionRecord;

   if ((ExceptionRecord->ExceptionFlags & 0x10) == 0) {
      // not a nested exception, throw one
      *p = 0; // throw another AV
   }
   else {
      printf("Caught a nested exception\n");
      return 1;
    }

   assert(false);

   return 0;
}

void f(void) {
   __try {
      *p = 0;   // throw an AV
   }
   __except(filter(GetExceptionInformation())) {
      printf_s("We should execute this handler if "
                 "compiled to native\n");
    }
}

int main() {
   __try {
      f();
   }
   __except(1) {
      printf_s("The handler in main caught the "
               "exception\n");
    }
}
```

### <a name="output"></a>Вывод

```Output
Caught a nested exception
We should execute this handler if compiled to native
```

##  <a name="vccondisassociatedrethrows"></a>Разделенные реторы

**/ CLR** не поддерживает повторное создание исключения за пределами обработчика catch (известный как Разделенные реторы). Исключения этого типа, обрабатываются как стандартный rethrow C++. Если rethrow при обнаружении active управляемого исключения, исключение упаковываться как исключения C++, а затем выдаваться повторно. Исключения этого типа может быть перехвачен только как исключение типа [System::SEHException](https://msdn.microsoft.com/library/system.runtime.interopservices.sehexception.aspx).

В следующем примере показано управляемое исключение повторно создаются как исключения C++:

```cpp
// clr_exception_handling_6.cpp
// compile with: /clr
using namespace System;
#include <assert.h>
#include <stdio.h>

void rethrow( void ) {
   // This rethrow is a dissasociated rethrow.
   // The exception would be masked as SEHException.
   throw;
}

int main() {
   try {
      try {
         throw gcnew ApplicationException;
      }
      catch ( ApplicationException^ ) {
         rethrow();
         // If the call to rethrow() is replaced with
         // a throw statement within the catch handler,
         // the rethrow would be a managed rethrow and
         // the exception type would remain
         // System::ApplicationException
      }
   }

    catch ( ApplicationException^ ) {
      assert( false );

      // This will not be executed since the exception
      // will be masked as SEHException.
    }
   catch ( Runtime::InteropServices::SEHException^ ) {
      printf_s("caught an SEH Exception\n" );
    }
}
```

### <a name="output"></a>Вывод

```Output
caught an SEH Exception
```

##  <a name="vcconexceptionfiltersandexception_continue_execution"></a> Фильтры исключений и EXCEPTION_CONTINUE_EXECUTION

Если фильтр возвращает `EXCEPTION_CONTINUE_EXECUTION` в управляемом приложении, он рассматривается как фильтр вернул `EXCEPTION_CONTINUE_SEARCH`. Дополнительные сведения о этих констант см. в разделе [try-except Statement](../cpp/try-except-statement.md).

В следующем примере демонстрируется это различие:

```cpp
// clr_exception_handling_7.cpp
#include <windows.h>
#include <stdio.h>
#include <assert.h>

int main() {
   int Counter = 0;
   __try {
      __try  {
         Counter -= 1;
         RaiseException (0xe0000000|'seh',
                         0, 0, 0);
         Counter -= 2;
      }
      __except (Counter) {
         // Counter is negative,
         // indicating "CONTINUE EXECUTE"
         Counter -= 1;
      }
    }
    __except(1) {
      Counter -= 100;
   }

   printf_s("Counter=%d\n", Counter);
}
```

### <a name="output"></a>Вывод

```Output
Counter=-3
```

##  <a name="vcconthe_set_se_translatorfunction"></a> _Set_se_translator-функция

Функция-преобразователь, заданный вызовом к `_set_se_translator`, затрагивает только элементы перехвата в неуправляемом коде. В следующем примере показано это ограничение:

```cpp
// clr_exception_handling_8.cpp
// compile with: /clr /EHa
#include <iostream>
#include <windows.h>
#include <eh.h>
#pragma warning (disable: 4101)
using namespace std;
using namespace System;

#define MYEXCEPTION_CODE 0xe0000101

class CMyException {
public:
   unsigned int m_ErrorCode;
   EXCEPTION_POINTERS * m_pExp;

   CMyException() : m_ErrorCode( 0 ), m_pExp( NULL ) {}

   CMyException( unsigned int i, EXCEPTION_POINTERS * pExp )
         : m_ErrorCode( i ), m_pExp( pExp ) {}

   CMyException( CMyException& c ) : m_ErrorCode( c.m_ErrorCode ),
                                      m_pExp( c.m_pExp ) {}

   friend ostream& operator <<
                 ( ostream& out, const CMyException& inst ) {
      return out <<  "CMyException[\n" <<
             "Error Code: " << inst.m_ErrorCode <<  "]";
    }
};

#pragma unmanaged
void my_trans_func( unsigned int u, PEXCEPTION_POINTERS pExp ) {
   cout <<  "In my_trans_func.\n";
   throw CMyException( u, pExp );
}

#pragma managed
void managed_func() {
   try  {
      RaiseException( MYEXCEPTION_CODE, 0, 0, 0 );
   }
   catch ( CMyException x ) {}
   catch ( ... ) {
      printf_s("This is invoked since "
               "_set_se_translator is not "
               "supported when /clr is used\n" );
    }
}

#pragma unmanaged
void unmanaged_func() {
   try  {
      RaiseException( MYEXCEPTION_CODE,
                      0, 0, 0 );
   }
   catch ( CMyException x ) {
      printf("Caught an SEH exception with "
             "exception code: %x\n", x.m_ErrorCode );
    }
    catch ( ... ) {}
}

// #pragma managed
int main( int argc, char ** argv ) {
   _set_se_translator( my_trans_func );

   // It does not matter whether the translator function
   // is registered in managed or unmanaged code
   managed_func();
   unmanaged_func();
}
```

### <a name="output"></a>Вывод

```Output
This is invoked since _set_se_translator is not supported when /clr is used
In my_trans_func.
Caught an SEH exception with exception code: e0000101
```

## <a name="see-also"></a>См. также

[Обработка исключений](../windows/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../windows/safe-cast-cpp-component-extensions.md)<br/>
[Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)