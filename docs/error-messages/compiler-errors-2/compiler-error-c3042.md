---
title: Ошибка компилятора C3042
ms.date: 11/04/2016
f1_keywords:
- C3042
helpviewer_keywords:
- C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
ms.openlocfilehash: deb3b8d6251316bceb71ce03f2bda88520bbb9b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626802"
---
# <a name="compiler-error-c3042"></a>Ошибка компилятора C3042

Предложения "copyprivate" и "nowait" не могут указываться вместе в директиве "директива" OpenMP

Предложения [copyprivate](../../parallel/openmp/reference/copyprivate.md) и [nowait](../../parallel/openmp/reference/nowait.md) являются взаимоисключающими для конкретной директивы. Чтобы устранить эту ошибку, удалите одно из предложений `copyprivate` и `nowait` или оба.

В следующем примере возникает ошибка C3042:

```
// C3042.cpp
// compile with: /openmp /c
#include <stdio.h>
#include "omp.h"

double d;

int main() {
    #pragma omp parallel private(d)
   {
      #pragma omp single copyprivate(d) nowait   // C3042
      {
      }
   }
}
```