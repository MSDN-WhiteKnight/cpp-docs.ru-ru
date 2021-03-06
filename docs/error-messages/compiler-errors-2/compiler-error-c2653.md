---
title: Ошибка компилятора C2653
ms.date: 11/30/2017
f1_keywords:
- C2653
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
ms.openlocfilehash: d4a3a8a74483317b87e16458f44016f0aeca1379
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471153"
---
# <a name="compiler-error-c2653"></a>Ошибка компилятора C2653

> "*идентификатор*": не является именем класса или пространства имен

Синтаксис языка требует класса, структуры, объединения или имя пространства имен.

Эта ошибка может возникать при использовании имени, который не был объявлен как класса, структуры, объединения или пространства имен перед оператор области действия. Чтобы устранить эту проблему, объявите имя или включать заголовок, который объявляет имя, перед их использованием.

C2653 можно также при попытке определить *составное пространство имен*, пространство имен, содержащее одно или несколько имен вложенные области пространства имен. Комплексная пространство имен определения не допускаются в C++ до C ++ 17. Составные пространства имен поддерживаются начиная с Visual Studio 2015 с обновлением 3, при указании [/std: c ++ последнюю](../../build/reference/std-specify-language-standard-version.md) параметр компилятора. Начиная с Visual C++ 2017 версии 15.5, компилятор поддерживает определения комплексной пространств имен при [/std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) параметра.

## <a name="examples"></a>Примеры

Этот пример приводит к возникновению ошибки C2653, так как используется имя области, но не объявлен. Компилятор ожидает класса, структуры, объединения или имя пространства имен до оператора области действия (::).

```cpp
// C2653.cpp
// compile with: /c
class yy {
   void func1(int i);
};

void xx::func1(int m) {}   // C2653, xx is not declared
void yy::func1(int m) {}   // OK
```

В коде, не компилируется для C ++ 17 или более поздней версии стандартов вложенные пространства имен необходимо использовать в объявлении явное пространство имен на каждом уровне вложенности:

```cpp
// C2653b.cpp
namespace a::b {int i;}   // C2653 prior to Visual C++ 2015 Update 3,
                          // C2429 thereafter. Use /std:c++17 or /std:c++latest to fix.

namespace a {             // Use this form for compliant code under /std:c++14 (the default)
   namespace b {          // or when using compilers before Visual Studio 2015 update 3.
      int i;
   }
}

int main() {
   a::b::i = 2;
}
```
