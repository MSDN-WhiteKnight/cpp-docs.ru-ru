---
title: Ошибка компилятора C2786
ms.date: 11/04/2016
f1_keywords:
- C2786
helpviewer_keywords:
- C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
ms.openlocfilehash: b03155ad1a209ae59327dd31d432f5623f380ac9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511427"
---
# <a name="compiler-error-c2786"></a>Ошибка компилятора C2786

«Тип»: недопустимый операнд для __uuidof

[__Uuidof](../../cpp/uuidof-operator.md) оператор принимает определяемого пользователем типа с присоединенным идентификатором GUID или объект такого типа определяемых пользователем.  Возможные причины:

1. Аргумент не определяемого пользователем типа.

1. `__uuidof` не удается извлечь идентификатор GUID из аргумента.

Следующий пример приводит к возникновению ошибки C2786:

```
// C2786.cpp
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};

int main() {
   __uuidof(int);   // C2786
   __uuidof(int *);   // C2786
   __uuidof(A **);   // C2786

   // no error
   __uuidof(A);
   __uuidof(A *);
   __uuidof(A &);
   __uuidof(A[]);

   int i;
   int *pi;
   A **ppa;

   __uuidof(i);      // C2786
   __uuidof(pi);     // C2786
   __uuidof(ppa);    // C2786
}
```