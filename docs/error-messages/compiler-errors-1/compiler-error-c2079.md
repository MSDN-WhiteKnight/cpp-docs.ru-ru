---
title: Ошибка компилятора C2079
ms.date: 11/04/2016
f1_keywords:
- C2079
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
ms.openlocfilehash: 68435610680e3b21415a1d9439a8133fd1e2557f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621667"
---
# <a name="compiler-error-c2079"></a>Ошибка компилятора C2079

«Идентификатор» использует неопределенный класс, структуру или объединение «name»

Указанный идентификатор является неопределенным класса, структуры или объединения.

Эта ошибка может быть вызвана инициализация анонимного объединения.

Следующий пример приводит к возникновению ошибки C2079:

```
// C2079.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   std::ifstream g;   // C2079
}
```

Возможное решение

```
// C2079b.cpp
// compile with: /EHsc
#include <fstream>
int main( ) {
   std::ifstream g;
}
```

C2079 также может возникать при попытке объявить объект в стеке которого опережающее объявление находится только в области типа.

```
// C2079c.cpp
class A;

class B {
   A a;   // C2079
};

class A {};
```

Возможное решение

```
// C2079d.cpp
// compile with: /c
class A;
class C {};

class B {
   A * a;
   C c;
};

class A {};
```