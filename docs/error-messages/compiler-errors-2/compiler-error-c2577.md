---
title: Ошибка компилятора C2577
ms.date: 11/04/2016
f1_keywords:
- C2577
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
ms.openlocfilehash: 4406aa90b26bc517308132ae9cccd003d44a9aad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530550"
---
# <a name="compiler-error-c2577"></a>Ошибка компилятора C2577

«член»: деструктор или метод завершения не может иметь тип возвращаемого значения

Деструктор или метод завершения не может возвращать значение `void` или любого другого типа. Удалить `return` оператора из определения деструктора.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2577.

```
// C2577.cpp
// compile with: /c
class A {
public:
   A() {}
   ~A(){
      return 0;   // C2577
   }
};
```