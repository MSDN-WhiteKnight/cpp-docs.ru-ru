---
title: Предупреждение компилятора (уровень 3) C4521
ms.date: 11/04/2016
f1_keywords:
- C4521
helpviewer_keywords:
- C4521
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
ms.openlocfilehash: 887526810f7e65280adcde422ef871a67ccdde1f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591819"
---
# <a name="compiler-warning-level-3-c4521"></a>Предупреждение компилятора (уровень 3) C4521

«класс»: заданы несколько конструкторов копий

Класс имеет несколько конструкторов копий одного типа. Это сообщение является информационным; конструкторы можно вызвать в приложении.

Используйте [предупреждение](../../preprocessor/warning.md) директиву pragma, чтобы отключить это предупреждение.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4521.

```
// C4521.cpp
// compile with: /EHsc /W3
#include <iostream>

using namespace std;
class A {
public:
   A() { cout << "A's default constructor" << endl; }
   A( A &o ) { cout << "A&" << endl; }
   A( const A &co ) { cout << "const A&" << endl; }   // C4521
};

int main() {
   A o1;         // Calls default constructor.
   A o2( o1 );   // Calls A( A& ).
   const A o3;   // Calls default constructor.
   A o4( o3 );   // Calls A( const A& ).
}
```