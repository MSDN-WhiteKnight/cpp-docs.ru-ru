---
title: Ошибка компилятора C3749
ms.date: 11/04/2016
f1_keywords:
- C3749
helpviewer_keywords:
- C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
ms.openlocfilehash: 7535f82a392f3d54b265ada2bd40a8d433838f4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596525"
---
# <a name="compiler-error-c3749"></a>Ошибка компилятора C3749

«атрибут»: настраиваемый атрибут не может использоваться внутри функции

Настраиваемый атрибут не может использоваться внутри функции. Дополнительные сведения о настраиваемых атрибутах см. в разделе [атрибут](../../windows/attributes/attribute.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3749:

```
// C3749a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All)]
public ref struct ABC : public Attribute {
   ABC() {}
};

void f1() { [ABC]; };  // C3749
```
