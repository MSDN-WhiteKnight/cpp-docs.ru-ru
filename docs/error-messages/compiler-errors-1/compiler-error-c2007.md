---
title: Ошибка компилятора C2007
ms.date: 11/04/2016
f1_keywords:
- C2007
helpviewer_keywords:
- C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
ms.openlocfilehash: f3c7b1a18dda9b2f9af7e346c2a1ed2f0303bb61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434688"
---
# <a name="compiler-error-c2007"></a>Ошибка компилятора C2007

\#синтаксис #define

Отсутствует идентификатор указывается после `#define`. Чтобы устранить эту ошибку, используйте идентификатор.

Следующий пример приводит к возникновению ошибки C2007:

```
// C2007.cpp
#define   // C2007
```

Возможное решение

```
// C2007b.cpp
// compile with: /c
#define true 1
```