---
title: Ошибка компилятора C2341
ms.date: 11/04/2016
f1_keywords:
- C2341
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
ms.openlocfilehash: 4356182758398fa7ed1ec6a069affa4bb99ace1a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631690"
---
# <a name="compiler-error-c2341"></a>Ошибка компилятора C2341

«имя_раздела»: сегмент должен быть определен с помощью #pragma data_seg, code_seg или предыдущего раздела, для использования

[Выделить](../../cpp/allocate.md) Инструкция ссылается на сегмент, который еще не определен [code_seg](../../preprocessor/code-seg.md), [data_seg](../../preprocessor/data-seg.md), или [разделе](../../preprocessor/section.md) директивы pragma.

Следующий пример приводит к возникновению ошибки C2341:

```
// C2341.cpp
// compile with: /c
__declspec(allocate(".test"))   // C2341
int j = 1;
```

Возможное решение

```
// C2341b.cpp
// compile with: /c
#pragma data_seg(".test")
__declspec(allocate(".test"))
int j = 1;
```