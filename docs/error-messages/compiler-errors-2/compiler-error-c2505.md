---
title: Ошибка компилятора C2505
ms.date: 11/04/2016
f1_keywords:
- C2505
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
ms.openlocfilehash: bf5ffb9b6bad3db1d264941a6aefa391be521c98
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610214"
---
# <a name="compiler-error-c2505"></a>Ошибка компилятора C2505

«символ»: параметр «__declspec(модификатор)» может применяться только в объявлениях или определениях глобальных объектов или статические данные-члены

Объект `__declspec` модификатор, который должен использоваться только в глобальной области видимости был использован в функции.

Дополнительные сведения см. в разделах [appdomain](../../cpp/appdomain.md) и [process](../../cpp/process.md).

Следующий пример приводит к возникновению ошибки C2505:

```
// C2505.cpp
// compile with: /clr

// OK
__declspec(process) int ii;
__declspec(appdomain) int jj;

int main() {
   __declspec(process) int i;   // C2505
   __declspec(appdomain) int j;   // C2505
}
```