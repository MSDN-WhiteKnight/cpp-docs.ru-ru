---
title: Ошибка компилятора C2371
ms.date: 11/04/2016
f1_keywords:
- C2371
helpviewer_keywords:
- C2371
ms.assetid: d383993d-05ef-4e35-8129-3b58a6f7b7b7
ms.openlocfilehash: 6fe9e85451d973ddd3983a935a9d1349c2699efb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615037"
---
# <a name="compiler-error-c2371"></a>Ошибка компилятора C2371

"идентификатор": переопределение; различные базовые типы

Идентификатор уже объявлен.

Следующий пример приводит к возникновению ошибки C2371:

```
// C2371.cpp
int main() {
   int i;
   float i;   // C2371, redefinition
   float f;   // OK
}
```