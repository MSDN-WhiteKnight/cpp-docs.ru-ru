---
title: Ошибка компилятора C3747
ms.date: 11/04/2016
f1_keywords:
- C3747
helpviewer_keywords:
- C3747
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
ms.openlocfilehash: 860a990e35b0d51dfc1316a11a2d2512eb40c273
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574363"
---
# <a name="compiler-error-c3747"></a>Ошибка компилятора C3747

отсутствует параметр типа по умолчанию: параметр param

Параметры универсального класса или шаблона со значениями по умолчанию не может следовать в списке параметров по параметрам, у которых нет значения по умолчанию.

Следующий пример приводит к возникновению ошибки C3747:

```
// C3747.cpp
template <class T1 = int, class T2>   // C3747
struct MyStruct {};
```

Возможное решение

```
// C3747b.cpp
// compile with: /c
template <class T1, class T2 = int>
struct MyStruct {};
```