---
title: Ошибка компилятора C2777
ms.date: 11/04/2016
f1_keywords:
- C2777
helpviewer_keywords:
- C2777
ms.assetid: 5fe158c0-2a65-488a-aca2-61d4a8b32d43
ms.openlocfilehash: cfbe2c729141108565f00b7b5a7fd581b49e516d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589258"
---
# <a name="compiler-error-c2777"></a>Ошибка компилятора C2777

только один метод «put» может быть задан для свойства

Объект [свойство](../../cpp/property-cpp.md) модификатор declspec имеет несколько `put` свойство.

Следующий пример приводит к возникновению ошибки C2777:

```
// C2777.cpp
struct A {
   __declspec(property(put=PutProp,put=PutPropToo))   // C2777
   // try the following line instead
   // __declspec(property(put=PutProp))
      int prop;
   int PutProp(void);
   int PutPropToo(void);
};
```