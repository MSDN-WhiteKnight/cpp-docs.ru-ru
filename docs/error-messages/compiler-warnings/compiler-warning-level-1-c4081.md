---
title: Предупреждение компилятора (уровень 1) C4081
ms.date: 11/04/2016
f1_keywords:
- C4081
helpviewer_keywords:
- C4081
ms.assetid: 6f656373-a080-4989-bbc9-e2f894b03293
ms.openlocfilehash: f43a736a73b4a504755cd8dc079a41e59aaf72bd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624657"
---
# <a name="compiler-warning-level-1-c4081"></a>Предупреждение компилятора (уровень 1) C4081

требуется "токен1"; обнаружено "токен2"

Компилятору в данном контексте требуется другой токен.

## <a name="example"></a>Пример

```
// C4081.cpp
// compile with: /W1 /LD
#pragma optimize) "l", on )   // C4081
```