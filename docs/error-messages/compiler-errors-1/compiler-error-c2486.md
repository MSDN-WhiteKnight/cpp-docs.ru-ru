---
title: Ошибка компилятора C2486
ms.date: 11/04/2016
f1_keywords:
- C2486
helpviewer_keywords:
- C2486
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
ms.openlocfilehash: 8d745c03530f331da83b45c765a2cb4bb7d76d8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555665"
---
# <a name="compiler-error-c2486"></a>Ошибка компилятора C2486

«__LOCAL_SIZE» допускается только в функции с атрибутом «naked»

Во встроенных функциях сборки, имя `__LOCAL_SIZE` зарезервировано для функций, объявленных с [с атрибутом naked](../../cpp/naked-cpp.md) атрибута.

Следующий пример приводит к возникновению ошибки C2486:

```
// C2486.cpp
// processor: x86
void __declspec(naked) f1() {
   __asm {
      mov   eax,   __LOCAL_SIZE
   }
}
void f2() {
   __asm {
      mov   eax,   __LOCAL_SIZE   // C2486
   }
}
```