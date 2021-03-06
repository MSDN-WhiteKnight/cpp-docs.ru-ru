---
title: Предупреждение компилятора (уровень 4) C4256
ms.date: 11/04/2016
f1_keywords:
- C4256
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
ms.openlocfilehash: b1f7534098a04c7c65a380d302999260c960f284
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627582"
---
# <a name="compiler-warning-level-4-c4256"></a>Предупреждение компилятора (уровень 4) C4256

«функция»: конструктор класса с виртуальными базами содержит «...»; вызовы могут оказаться несовместимыми с более ранними версиями Visual C++

Возможная несовместимость.

Рассмотрим следующий пример кода: Если определение конструктора S2::S2 (int i,...) был скомпилирован с использованием версии компилятора Visual C++ до версии 7, но следующий пример компилируется с помощью текущей версии, вызов конструктора для S3 будет работать неправильно из-за Изменение соглашения о вызовах особым случаем. Если оба были скомпилированы с помощью Visual C++ 6.0, вызов будет работать правильно, если параметры не были переданы для кнопку с многоточием.

Чтобы устранить это предупреждение

1. Не используйте кнопку с многоточием в конструкторе.

1. Убедитесь, что все компоненты в проекте создаются в текущей версии (включая все библиотеки, которые могут определять или ссылаться на этот класс), а затем отключить предупреждение с помощью [предупреждение](../../preprocessor/warning.md) директивы pragma.

Следующий пример приводит к возникновению ошибки C4256:

```
// C4256.cpp
// compile with: /W4
// #pragma warning(disable : 4256)
struct S1
{
};

struct S2: virtual public S1
{
   S2( int i, ... )    // C4256
   {
      i = 0;
   }
   /*
   // try the following line instead
   S2( int i)
   {
      i = 0;
   }
   */
};

void func1()
{
   S2 S3( 2, 1, 2 );   // C4256
   // try the following line instead
   // S2 S3( 2 );
}

int main()
{
}
```