---
title: Ошибка компилятора C3053
ms.date: 11/04/2016
f1_keywords:
- C3053
helpviewer_keywords:
- C3053
ms.assetid: ab9a25f3-e341-4f6e-8e69-069b4a963a64
ms.openlocfilehash: cb01207be15a628fb0c6206df3e6a673067f568a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441373"
---
# <a name="compiler-error-c3053"></a>Ошибка компилятора C3053

"символ": "threadprivate" допускается только для глобальных или статических элементов данных

Символы, передаваемые в [threadprivate](../../parallel/openmp/reference/threadprivate.md) , должны быть глобальными или статическими.

Следующий пример приводит к возникновению ошибки C3053.

```
// C3053.cpp
// compile with: /openmp
void Test() {
   int x, y;
   #pragma omp threadprivate(x, y)   // C3053
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

Возможное решение

```
// C3053b.cpp
// compile with: /openmp /LD
int x, y;
#pragma omp threadprivate(x, y)

void Test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```