---
title: Ошибка компилятора C3235
ms.date: 11/04/2016
f1_keywords:
- C3235
helpviewer_keywords:
- C3235
ms.assetid: 0554d6c7-e1dc-4c99-8934-cbcf491c8203
ms.openlocfilehash: 1e74d479e75aee98dada16107b7e33d5cfe0c0cd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520324"
---
# <a name="compiler-error-c3235"></a>Ошибка компилятора C3235

"специализация": явная или частичная специализация универсального класса не допускается

Универсальные классы нельзя использовать для явных или частичных специализаций.

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C3235.

```
// C3235.cpp
// compile with: /clr
generic<class T>
public ref class C {};

generic<>
public ref class C<int> {};   // C3235 Remove this specialization to resolve this error.
```