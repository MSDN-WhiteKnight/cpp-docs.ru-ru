---
title: Ошибка компилятора C2611
ms.date: 11/04/2016
f1_keywords:
- C2611
helpviewer_keywords:
- C2611
ms.assetid: 3f2d5253-f24f-4724-83d0-6b2aa6a4e551
ms.openlocfilehash: b3c043f8aa8b6fcf4f63e9432e4a1b7222528285
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482476"
---
# <a name="compiler-error-c2611"></a>Ошибка компилятора C2611

«токен»: недопустимый следующий "~" (требуется идентификатор)

Токен не является идентификатором.

Следующий пример приводит к возникновению ошибки C2611:

```
// C2611.cpp
// compile with: /c
class C {
   C::~operator int();   // C2611
   ~C();   // OK
};
```