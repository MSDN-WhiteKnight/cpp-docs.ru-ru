---
title: Ошибка компилятора C2614
ms.date: 11/04/2016
f1_keywords:
- C2614
helpviewer_keywords:
- C2614
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
ms.openlocfilehash: 71f0fe3211ce253bcf30347658692651e84ab608
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463600"
---
# <a name="compiler-error-c2614"></a>Ошибка компилятора C2614

«класс1»: недопустимая инициализация члена: «класс2» не является основание или член

Только члены или базовые классы могут отображаться в списке инициализации для класса или структуры.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2614.

```
// C2614.cpp
// compile with: /c
struct A {
   int i;
   A( int ia ) : B( i ) {};   // C2614 B is not a member of A
};

struct A2 {
   int B;
   int i;
   A2( int ia ) : B( i ) {};   // OK
};
```