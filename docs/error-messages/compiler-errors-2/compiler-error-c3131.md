---
title: Ошибка компилятора C3131
ms.date: 11/04/2016
f1_keywords:
- C3131
helpviewer_keywords:
- C3131
ms.assetid: 38f20fac-83c9-4cd9-b7b5-74ca8f650ea6
ms.openlocfilehash: 082839c01a2da4b0d149962367b9719932d2b272
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530891"
---
# <a name="compiler-error-c3131"></a>Ошибка компилятора C3131

проект должен иметь атрибут «module» со свойством «name»

[Модуль](../../windows/module-cpp.md) атрибут должен иметь имя параметра.

Следующий пример приводит к возникновению ошибки C3131:

```
// C3131.cpp
[emitidl];
[module];   // C3131
// try the following line instead
// [module (name="MyLib")];

[public]
typedef long int LongInt;
```