---
title: Ошибка компилятора C2724
ms.date: 11/04/2016
f1_keywords:
- C2724
helpviewer_keywords:
- C2724
ms.assetid: 4e4664bc-8c96-4156-b79f-03436f532ea8
ms.openlocfilehash: 3014a12767cb9a73dc65852c544b7ac9574b9a52
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585254"
---
# <a name="compiler-error-c2724"></a>Ошибка компилятора C2724

«Идентификатор»: «static» не должен использоваться для функций-членов определены в области видимости файла

Статические функции-члены должны объявляться с внешней компоновкой.

Следующий пример приводит к возникновению ошибки C2724:

```
// C2724.cpp
class C {
   static void func();
};

static void C::func(){};   // C2724
// try the following line instead
// void C::func(){};
```