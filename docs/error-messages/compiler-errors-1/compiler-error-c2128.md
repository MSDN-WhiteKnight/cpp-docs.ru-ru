---
title: Ошибка компилятора C2128
ms.date: 11/04/2016
f1_keywords:
- c2128
helpviewer_keywords:
- C2128
ms.assetid: 08cbf734-75b3-49f2-9026-9b319947612d
ms.openlocfilehash: 80015118bf9e8bc8d8c4fba578f4ff1fa4651034
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452563"
---
# <a name="compiler-error-c2128"></a>Ошибка компилятора C2128

«функция»: alloc_text и same_seg применимы только к функциям с компоновкой C

`pragma` `alloc_text` может использоваться только с функциями, которые объявлены с компоновкой.

Следующий пример приводит к возникновению ошибки C2128:

```
// C2128.cpp
// compile with: /c

// Delete the following line to resolve.
void func();
// #pragma alloc_text("my segment", func)   // C2128

extern "C" {
void func();
}

#pragma alloc_text("my segment", func)
void func() {}
```