---
title: Ошибка компилятора C3645
ms.date: 11/04/2016
f1_keywords:
- C3645
helpviewer_keywords:
- C3645
ms.assetid: 346da528-ae86-4cd0-9654-f41bee26ac0d
ms.openlocfilehash: f733de6920e00f1f53c87884a7a334e575bceb06
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500338"
---
# <a name="compiler-error-c3645"></a>Ошибка компилятора C3645

«функция»: __clrcall невозможно использовать с функциями, скомпилированными в машинный код

Наличие некоторые ключевые слова в функции вызовет функцию для компиляции в машинный код.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3645.

```
// C3645.cpp
// compile with: /clr /c
#pragma unmanaged
int __clrcall dog() {}   // C3645
```