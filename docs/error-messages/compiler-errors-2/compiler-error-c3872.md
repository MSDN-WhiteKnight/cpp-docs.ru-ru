---
title: Ошибка компилятора C3872
ms.date: 11/04/2016
f1_keywords:
- C3872
helpviewer_keywords:
- C3872
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
ms.openlocfilehash: 5cadb8165b5b63b2f7ac2d4cc31e2623b0f6bce9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649906"
---
# <a name="compiler-error-c3872"></a>Ошибка компилятора C3872

"char": этот символ невозможно использовать в идентификаторе

Компилятор C++ следует стандарту C++11 в отношении разрешенных символов в идентификаторе. В идентификаторе можно использовать только определенные диапазоны символов и универсальных имен символов. Дополнительные ограничения применяются к начальному символу идентификатора. Дополнительные сведения и список разрешенных символов и диапазонов универсальных имен символов см. в разделе [Identifiers](../../cpp/identifiers-cpp.md).

Диапазон разрешенных символов в идентификаторе шире, чем при компиляции кода C++/CLI. Идентификаторы в коде, скомпилированном с помощью /clr, должны соответствовать  [стандарту ECMA-335: Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).

Следующий пример приводит к возникновению ошибки C3872:

```
// C3872.cpp
int main() {
   int abc_\u0040;   // C3872, U+0040 is in base char set
   int abc_\u3001;   // C3872, U+3001 is not in allowed range
   int \u30A2_abc_\u3042;   // OK, UCNs in allowed range
}
```