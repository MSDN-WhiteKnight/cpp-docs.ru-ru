---
title: Ошибка компилятора C3874
ms.date: 11/04/2016
f1_keywords:
- C3874
helpviewer_keywords:
- C3874
ms.assetid: fd55fc05-69a7-4237-b3b7-dca1d5400b4f
ms.openlocfilehash: 73476d50b6cfe098ee9d8084837c2090e198a6cd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445049"
---
# <a name="compiler-error-c3874"></a>Ошибка компилятора C3874

Тип возвращаемого значения «function» должен быть «int» вместо «тип»

Функция не имеет тип возвращаемого значения, которое должно было компилятором.

Следующий пример приводит к возникновению ошибки C3874:

```
// C3874b.cpp
double main()
{   // C3874
}
```