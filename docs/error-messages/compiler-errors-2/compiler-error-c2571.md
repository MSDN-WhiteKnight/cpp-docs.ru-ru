---
title: Ошибка компилятора C2571
ms.date: 11/04/2016
f1_keywords:
- C2571
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
ms.openlocfilehash: d7d4898e5f0b55c50a4c18cef053cc150394d7e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485076"
---
# <a name="compiler-error-c2571"></a>Ошибка компилятора C2571

«функция»: виртуальная функция не может быть в объединении «объединение»

Виртуальная функция объявляется объединение. Можно объявить виртуальной функции только в классе или структуре.  Возможные решения:

1. Преобразуйте объединение в классе или структуре.

1. Не делайте функцию виртуальной.

Следующий пример приводит к возникновению ошибки C2571:

```
// C2571.cpp
// compile with: /c
union A {
   virtual void func1();   // C2571
   void func2();   // OK
};
```