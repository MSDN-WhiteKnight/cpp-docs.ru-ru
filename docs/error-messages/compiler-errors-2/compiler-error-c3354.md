---
title: Ошибка компилятора C3354
ms.date: 11/04/2016
f1_keywords:
- C3354
helpviewer_keywords:
- C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
ms.openlocfilehash: 1ff2967f602722c99b58b679324bd4f50575f109
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523169"
---
# <a name="compiler-error-c3354"></a>Ошибка компилятора C3354

"функция": функция, используемая для создания делегата, не может иметь тип возврата "тип"

Следующие типы недопустимы в качестве типов возврата для `delegate`:

- Указатель на функцию

- Указатель на член

- Указатель на функцию-член

- Ссылка на функцию

- Ссылка на функцию-член

В следующем примере возникает ошибка C3354:

```
// C3354_2.cpp
// compile with: /clr /c
using namespace System;
typedef void ( *VoidPfn )();

delegate VoidPfn func(); // C3354
// try the following line instead
// delegate  void func();
```
