---
title: Ошибка компилятора C3006
ms.date: 11/04/2016
f1_keywords:
- C3006
helpviewer_keywords:
- C3006
ms.assetid: 449082ec-fd45-4c47-8ab3-ba6a719e4dc4
ms.openlocfilehash: 7200d0ab3b14a1f9faa310f466963d74f7c98985
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436209"
---
# <a name="compiler-error-c3006"></a>Ошибка компилятора C3006

"предложение": в предложении директивы OpenMP "директива" отсутствует необходимый аргумент

В директиве OpenMP отсутствует ожидаемый аргумент.

Следующий пример приводит к возникновению ошибки C3006:

```
// C3006.c
// compile with: /openmp
int main()
{
   #pragma omp parallel shared   // C3006
   // Try the following line instead:
   // #pragma omp parallel shared(x) {}

}
```