---
title: Встроенные функции _InterlockedDecrement
ms.date: 12/17/2018
f1_keywords:
- _InterlockedDecrement16_rel_cpp
- _InterlockedDecrement16_acq_cpp
- _InterlockedDecrement16_rel
- _InterlockedDecrement64_acq
- _InterlockedDecrement_nf
- _InterlockedDecrement16_nf
- _InterlockedDecrement64_rel_cpp
- _InterlockedDecrement_rel_cpp
- _InterlockedDecrement16_acq
- _InterlockedDecrement64_acq_cpp
- _InterlockedDecrement_rel
- _InterlockedDecrement64_nf
- _InterlockedDecrement16_cpp
- _InterlockedDecrement64
- _InterlockedDecrement_cpp
- _InterlockedDecrement64_rel
- _InterlockedDecrement16
- _InterlockedDecrement
- _InterlockedDecrement64_cpp
- _InterlockedDecrement_acq
- _InterlockedDecrement_acq_cpp
helpviewer_keywords:
- InterlockedDecrement64_rel intrinsic
- InterlockedDecrement64 intrinsic
- _InterlockedDecrement16 intrinsic
- _InterlockedDecrement16_acq intrinsic
- _InterlockedDecrement intrinsic
- _InterlockedDecrement_nf intrinsic
- _InterlockedDecrement_acq intrinsic
- _InterlockedDecrement64_rel intrinsic
- _InterlockedDecrement16_rel intrinsic
- InterlockedDecrement intrinsic
- InterlockedDecrement16 intrinsic
- _InterlockedDecrement16_nf intrinsic
- InterlockedDecrement64_acq intrinsic
- _InterlockedDecrement_rel intrinsic
- InterlockedDecrement_acq intrinsic
- _InterlockedDecrement64_acq intrinsic
- _InterlockedDecrement64 intrinsic
- _InterlockedDecrement64_nf intrinsic
- InterlockedDecrement_rel intrinsic
ms.assetid: 5268fce3-86b5-4b2b-b96c-2e531a3fb9b5
ms.openlocfilehash: d180ed8d416483d1be5e2bbd52f1a8752996f3f9
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627490"
---
# <a name="interlockeddecrement-intrinsic-functions"></a>Встроенные функции _InterlockedDecrement

**Блок, относящийся только к системам Microsoft**

Предоставляет встроенную поддержку компилятора для пакета SDK Windows Win32 [InterlockedDecrement](/windows/desktop/api/winbase/nf-winbase-interlockeddecrement) функции.

## <a name="syntax"></a>Синтаксис

```
long _InterlockedDecrement(
   long * lpAddend
);
long _InterlockedDecrement_acq(
   long * lpAddend
);
long _InterlockedDecrement_rel(
   long * lpAddend
);
long _InterlockedDecrement_nf(
   long * lpAddend
);
short _InterlockedDecrement16(
   short * lpAddend
);
short _InterlockedDecrement16_acq(
   short * lpAddend
);
short _InterlockedDecrement16_rel(
   short * lpAddend
);
short _InterlockedDecrement16_nf(
   short * lpAddend
);
__int64 _InterlockedDecrement64(
   __int64 * lpAddend
);
__int64 _InterlockedDecrement64_acq(
   __int64 * lpAddend
);
__int64 _InterlockedDecrement64_rel(
   __int64 * lpAddend
);
__int64 _InterlockedDecrement64_nf(
   __int64 * lpAddend
);
```

#### <a name="parameters"></a>Параметры

*lpAddend*<br/>
[in, out] Указатель на переменную на единицу.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение, полученное после уменьшения.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_InterlockedDecrement`, `_InterlockedDecrement16`, `_InterlockedDecrement64`|x86, ARM, x64|
|`_InterlockedDecrement_acq`, `_InterlockedDecrement_rel`, `_InterlockedDecrement_nf`, `_InterlockedDecrement16_acq`, `_InterlockedDecrement16_rel`, `_InterlockedDecrement16_nf`, `_InterlockedDecrement64_acq`, `_InterlockedDecrement64_rel`, `_InterlockedDecrement64_nf`,|ARM|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Существуют несколько вариантов `_InterlockedDecrement`, они различаются в зависимости от типов данных, которые включают, и от того, используется ли семантика получения или освобождения конкретного процессора.

Функция `_InterlockedDecrement` работает с 32-разрядными целыми значениями, `_InterlockedDecrement16``_InterlockedDecrement64` работает с 16-разрядными целыми значениями и работает с 64-разрядными целыми значениями.

На платформах ARM используйте встроенные функции с суффиксами `_acq` и `_rel`, если нужно получить и освободить семантику, например в начале и конце критической секции. Встроенные функции с суффиксом `_nf` («без границ») не действуют как барьер памяти.

Переменная, на который указывает параметр `lpAddend`, должна быть выровнена по границе 32 разрядов; в противном случае эта функция не выполняется на многопроцессорных системах x86 и любой системе не-x86. Дополнительные сведения см. в разделе [выровнять](../cpp/align-cpp.md).

Эти процедуры доступны только как встроенные объекты.

## <a name="example"></a>Пример

```cpp
// compiler_intrinsics_interlocked.cpp
// compile with: /Oi
#define _CRT_RAND_S

#include <cstdlib>
#include <cstdio>
#include <process.h>
#include <windows.h>

// To declare an interlocked function for use as an intrinsic,
// include intrin.h and put the function in a #pragma intrinsic
// statement.
#include <intrin.h>

#pragma intrinsic (_InterlockedIncrement)

// Data to protect with the interlocked functions.
volatile LONG data = 1;

void __cdecl SimpleThread(void* pParam);

const int THREAD_COUNT = 6;

int main() {
   DWORD num;
   HANDLE threads[THREAD_COUNT];
   int args[THREAD_COUNT];
   int i;

   for (i = 0; i < THREAD_COUNT; i++) {
      args[i] = i + 1;
      threads[i] = reinterpret_cast<HANDLE>(_beginthread(SimpleThread, 0,
                           args + i));
      if (threads[i] == reinterpret_cast<HANDLE>(-1))
         // error creating threads
         break;
   }

   WaitForMultipleObjects(i, threads, true, INFINITE);
}

// Code for our simple thread
void __cdecl SimpleThread(void* pParam) {
   int threadNum = *((int*)pParam);
   int counter;
   unsigned int randomValue;
   unsigned int time;
   errno_t err = rand_s(&randomValue);

   if (err == 0) {
      time = (unsigned int) ((double) randomValue / (double) UINT_MAX * 500);
      while (data < 100) {
         if (data < 100) {
            _InterlockedIncrement(&data);
            printf_s("Thread %d: %d\n", threadNum, data);
         }

         Sleep(time);   // wait up to half of a second
      }
   }

   printf_s("Thread %d complete: %d\n", threadNum, data);
}
```

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Конфликты с 32-разрядным (x86) компилятором](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)