---
title: Предупреждение компилятора (уровень 1) C4353
ms.date: 11/04/2016
f1_keywords:
- C4353
helpviewer_keywords:
- C4353
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
ms.openlocfilehash: 305c1156ae8dc664edba17287786db50bfabbd18
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483711"
---
# <a name="compiler-warning-level-1-c4353"></a>Предупреждение компилятора (уровень 1) C4353

использовано нестандартное расширение: константа 0 в качестве выражения функции. Вместо этого используйте функцию «__noop»

Нельзя использовать константы нуль (0) как выражение функции. Дополнительные сведения см. в разделе [__noop](../../intrinsics/noop.md).

Следующий пример приводит к возникновению ошибки C4353:

```
// C4353.cpp
// compile with: /W1
void MyPrintf(void){};
#define X 0
#if X
   #define DBPRINT MyPrint
#else
   #define DBPRINT 0   // C4353 expected
#endif
int main(){
DBPRINT();
}
```