---
title: Ошибка компилятора C2850
ms.date: 11/04/2016
f1_keywords:
- C2850
helpviewer_keywords:
- C2850
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
ms.openlocfilehash: 34c2054226ea452f76fdb15b87454677a6a6fe8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611774"
---
# <a name="compiler-error-c2850"></a>Ошибка компилятора C2850

«конструктор»: допускается только на уровне файла; может оказаться во вложенном конструкторе

Конструкций, таких как некоторые директивы pragma может использоваться только в глобальной области.

В следующем примере возникает ошибка C2850:

```
// C2850.cpp
// compile with: /c /Yc
// try the following line instead
// #pragma hdrstop
namespace X {
   #pragma hdrstop   // C2850
};
```