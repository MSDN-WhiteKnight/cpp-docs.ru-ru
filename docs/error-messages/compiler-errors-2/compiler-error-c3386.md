---
title: Ошибка компилятора C3386
ms.date: 11/04/2016
f1_keywords:
- C3386
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
ms.openlocfilehash: a9183e1f62e7ebaf5db04a35a45806ec02169e69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637480"
---
# <a name="compiler-error-c3386"></a>Ошибка компилятора C3386

«Тип»: __declspec(dllexport) /\__declspec(dllimport) не может использоваться для управляемого или WinRTtype

`dllimport` И [dllexport](../../cpp/dllexport-dllimport.md) `__declspec` модификаторы недопустимы для управляемого или среды выполнения Windows тип.

В следующем примере показано возникновение ошибки C3386 и приводятся сведения по ее устранению.

```
// C3386.cpp
// compile with: /clr /c
ref class __declspec(dllimport) X1 {   // C3386
// try the following line instead
// ref class X1 {
};
```