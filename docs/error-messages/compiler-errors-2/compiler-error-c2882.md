---
title: Ошибка компилятора C2882
ms.date: 11/04/2016
f1_keywords:
- C2882
helpviewer_keywords:
- C2882
ms.assetid: 617018ee-5a0d-4b8d-9612-77e8ae52679b
ms.openlocfilehash: e5fd20695f6922ba5832abb1042cce63b7c4f5a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598502"
---
# <a name="compiler-error-c2882"></a>Ошибка компилятора C2882

«name»: Недопустимое использование идентификатора пространства имен в выражении

Предпринята попытка использовать имя пространства имен в выражении.

Следующий пример приводит к возникновению ошибки C2882:

```
// C2882.cpp
// compile with: /c
namespace A {
   int k;
}

int i = A;   // C2882, can't assign A to i
```