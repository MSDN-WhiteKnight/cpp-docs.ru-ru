---
title: Предупреждение компилятора (уровень 1) C4281
ms.date: 11/04/2016
f1_keywords:
- C4281
helpviewer_keywords:
- C4281
ms.assetid: a9771261-5725-4fc6-87b6-16cf92113a25
ms.openlocfilehash: 69496438d8078ee0298bdb447fcf4f7df1b75464
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441994"
---
# <a name="compiler-warning-level-3-c4281"></a>Предупреждение компилятора (уровень 1) C4281

произошла рекурсия «operator ->» через тип «тип»

Код разрешает **operator ->** вызывать самого себя.

Следующий пример приводит к возникновению ошибки C4281:

```
// C4281.cpp
// compile with: /W3 /WX
struct A;
struct B;
struct C;

struct A
{
   int z;
   B& operator->();
};

struct B
{
   C& operator->();
};

struct C
{
   A& operator->();
};

void f(A p)
{
   int i = p->z; // C4281
}
```