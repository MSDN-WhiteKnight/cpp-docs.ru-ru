---
title: Предупреждение компилятора (уровень 3) C4522
ms.date: 11/04/2016
f1_keywords:
- C4522
helpviewer_keywords:
- C4522
ms.assetid: 7065dc27-0b6c-4e68-a345-c51cdb99a20b
ms.openlocfilehash: de163f0a3925b711f2f3437b700f75bbe994b3e7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622967"
---
# <a name="compiler-warning-level-3-c4522"></a>Предупреждение компилятора (уровень 3) C4522

«класс»: заданы несколько операторов присваивания

Этот класс содержит несколько операторов присваивания одного типа. Это сообщение является информационным; конструкторы можно вызвать в приложении.

Используйте [предупреждение](../../preprocessor/warning.md) директиву pragma, чтобы отключить это предупреждение.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4522.

```
// C4522.cpp
// compile with: /EHsc /W3
#include <iostream>

using namespace std;
class A {
public:
   A& operator=( A & o ) { cout << "A&" << endl; return *this; }
   A& operator=( const A &co ) { cout << "const A&" << endl; return *this; }   // C4522
};

int main() {
   A o1, o2;
   o2 = o1;
   const A o3;
   o1 = o3;
}
```