---
title: Ошибка компилятора C2250
ms.date: 11/04/2016
f1_keywords:
- C2250
helpviewer_keywords:
- C2250
ms.assetid: f990986f-5c7d-4af4-a25c-b35540f1e217
ms.openlocfilehash: ea426e071eecb09359c3a99a6f569f628595784a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438055"
---
# <a name="compiler-error-c2250"></a>Ошибка компилятора C2250

«Идентификатор»: неоднозначное наследование «класс::член»

Производный класс наследует более одного переопределения виртуальной функции виртуального базового класса. Эти переопределения являются неоднозначными в производном классе.

При компиляции следующего примера возникнет ошибка C2286:

```
// C2250.cpp
// compile with: /c
// C2250 expected
struct V {
   virtual void vf();
};

struct A : virtual V {
   void vf();
};

struct B : virtual V {
   void vf();
};

struct D : A, B {
   // Uncomment the following line to resolve.
   // void vf();
};
```