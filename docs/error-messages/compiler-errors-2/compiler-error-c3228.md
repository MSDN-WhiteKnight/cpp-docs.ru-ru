---
title: Ошибка компилятора C3228
ms.date: 11/04/2016
f1_keywords:
- C3228
helpviewer_keywords:
- C3228
ms.assetid: 9015adf9-17b0-4312-b4a7-c1f33e4126f4
ms.openlocfilehash: 63e7afa16c21aa8c4e335d22693ca71d7ab8d6a8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512570"
---
# <a name="compiler-error-c3228"></a>Ошибка компилятора C3228

"функция": аргумент универсального типа для param не может быть типа "тип", он должен иметь тип значения или тип дескриптора

Неправильный тип был передан в качестве аргумента универсального типа.

В следующем примере возникает ошибка C3228:

```
// C3228.cpp
// compile with: /clr
class A {};

value class B {};

generic <class T>
void Test() {}

ref class C {
public:
   generic <class T>
   static void f() {}
};

int main() {
   C::f<A>();   // C3228
   C::f<B>();   // OK

   Test<C>();   // C3228
   Test<C ^>();   // OK
}
```