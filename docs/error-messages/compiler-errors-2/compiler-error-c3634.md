---
title: Ошибка компилятора C3634
ms.date: 11/04/2016
f1_keywords:
- C3634
helpviewer_keywords:
- C3634
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
ms.openlocfilehash: 2acd76fee5e7ca309991e639044a45ea83ed112b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527547"
---
# <a name="compiler-error-c3634"></a>Ошибка компилятора C3634

«функция»: невозможно определить абстрактный метод управляемого или WinRTclass

Абстрактный метод может быть объявлен в управляемом классе или классе WinRT, но он не может быть определен.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3634:

```
// C3634.cpp
// compile with: /clr
ref class C {
   virtual void f() = 0;
};

void C::f() {   // C3634 - don't define managed class' pure virtual method
}
```
