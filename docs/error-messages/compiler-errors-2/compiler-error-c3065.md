---
title: Ошибка компилятора C3065
ms.date: 11/04/2016
f1_keywords:
- C3065
helpviewer_keywords:
- C3065
ms.assetid: e7a0bc69-1c68-459e-a7c4-93c65609ff7c
ms.openlocfilehash: e12f6e318d51ecaccc7c29e1e01d1aedcaac937e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526565"
---
# <a name="compiler-error-c3065"></a>Ошибка компилятора C3065

не допускается объявление свойства не в области класса

Модификатор [свойства](../../cpp/property-cpp.md) __declspec использовался вне класса.  Свойства могут объявляться только внутри класса.

Следующий пример приводит к возникновению ошибки C3065:

```
// C3065.cpp
// compile with: /c
__declspec(property(get=get_i)) int i;   // C3065

class x {
public:
   __declspec(property(get=get_i)) int i;   // OK
};
```