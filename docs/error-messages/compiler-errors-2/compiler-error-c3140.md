---
title: Ошибка компилятора C3140
ms.date: 11/04/2016
f1_keywords:
- C3140
helpviewer_keywords:
- C3140
ms.assetid: 122f8943-fac3-4db8-a3a8-2c5d19233de6
ms.openlocfilehash: e7dde3eb27c018502225ea3bc45e4bee7c699379
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623162"
---
# <a name="compiler-error-c3140"></a>Ошибка компилятора C3140

в одном блоке компиляции не может быть несколько атрибутов «module»

[Модуль](../../windows/module-cpp.md) атрибута может быть определен для проекта только один раз.

Следующий пример приводит к возникновению ошибки C3140:

```
// C3140.cpp
// compile with: /c
[emitidl];
[module(name = "MyLibrary")];
[module(name = "MyLibrary2")];   // C3140
```