---
title: Предупреждение компилятора (уровень 1) C4180
ms.date: 11/04/2016
f1_keywords:
- C4180
helpviewer_keywords:
- C4180
ms.assetid: 40c91bd4-37f1-4d59-a4f3-d5ddab68239b
ms.openlocfilehash: 8ed09edae5a9577773c573337b6e646a49599862
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508875"
---
# <a name="compiler-warning-level-1-c4180"></a>Предупреждение компилятора (уровень 1) C4180

квалификатор, примененный к типу-функции, не имеет смысла; пропуск

Квалификатор, например **const**, применен к типу функции, определенному с помощью `typedef`.

## <a name="example"></a>Пример

```
// C4180.cpp
// compile with: /W1 /c
typedef int FuncType(void);

// the const qualifier cannot be applied to the
// function type FuncType
const FuncType f;   // C4180
```