---
title: Ошибка компилятора C3417
ms.date: 11/04/2016
f1_keywords:
- C3417
helpviewer_keywords:
- C3417
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
ms.openlocfilehash: 574af940f17c1a79472d6d20d63c9ff74d4c411e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615776"
---
# <a name="compiler-error-c3417"></a>Ошибка компилятора C3417

«член»: типы значений не может содержать определяемые пользователем специальные функции-члены

Типы значений не может содержать функции, такие как конструктор экземпляров по умолчанию, деструктор или конструктор копии.

Следующий пример приводит к возникновению ошибки C3517:

```
// C3417.cpp
// compile with: /clr /c
value class VC {
   VC(){}   // C3417

   // OK
   static VC(){}
   VC(int i){}
};
```