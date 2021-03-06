---
title: Ошибка компилятора C2932
ms.date: 11/04/2016
f1_keywords:
- C2932
helpviewer_keywords:
- C2932
ms.assetid: c28e88d9-e654-4367-bfb4-13c780bca9bd
ms.openlocfilehash: 004767d4adbd87a2a21ec73fa720d6992eb31044
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564463"
---
# <a name="compiler-error-c2932"></a>Ошибка компилятора C2932

"класс": идентификатор класса типа переопределен как элемент данных "идентификатор"

Универсальный класс или класс шаблона нельзя использовать в качестве элемента данных.

Следующий пример приводит к возникновению ошибки C2932:

```
// C2932.cpp
// compile with: /c
template<class T>
struct TC {};

struct MyStruct {
   int TC<int>;   // C2932
   int TC;   // OK
};
```

Ошибка C2932 также может возникнуть при использовании универсальных шаблонов:

```
// C2932b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};

struct MyStruct {
   int GC<int>;   // C2932
   int GC;   // OK
};
```