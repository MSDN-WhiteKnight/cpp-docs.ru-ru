---
title: Предупреждение компилятора (уровень 4) C4918
ms.date: 11/04/2016
f1_keywords:
- C4918
helpviewer_keywords:
- C4918
ms.assetid: 1bcf6d35-3467-4aa8-b2ef-cb33f4e70238
ms.openlocfilehash: 9662b561f6ce6c9f41327b267d17082b1eaa21a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668511"
---
# <a name="compiler-warning-level-4-c4918"></a>Предупреждение компилятора (уровень 4) C4918

"символ": недопустимый символ в списке оптимизации директивы pragma

В списке оптимизации оператора прагмы [optimize](../../preprocessor/optimize.md) был найден неизвестный символ.

Например, следующий оператор приводит к созданию предупреждения C4918:

```
// C4918.cpp
// compile with: /W4
#pragma optimize("X", on) // C4918 expected
int main()
{
}
```