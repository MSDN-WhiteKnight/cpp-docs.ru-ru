---
title: Ошибка компилятора C2227
ms.date: 11/04/2016
f1_keywords:
- C2227
helpviewer_keywords:
- C2227
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
ms.openlocfilehash: 8f9fc435682eb400574eea61a6f90392fa679233
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452745"
---
# <a name="compiler-error-c2227"></a>Ошибка компилятора C2227

выражение слева от "->член" должно указывать на тип класса, структуры или объединения либо на универсальный тип

Операнд слева от `->` не является указателем на класс, структуру или объединение.

Следующий пример приводит к возникновению ошибки C2227:

```
// C2227.cpp
int *pInt;
struct S {
public:
    int member;
} s, *pS = &s;

int main() {
   pInt->member = 0;   // C2227 pInt points to an int
   pS->member = 0;   // OK
}
```