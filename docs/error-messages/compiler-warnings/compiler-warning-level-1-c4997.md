---
title: Предупреждение компилятора (уровень 1) C4997
ms.date: 11/04/2016
f1_keywords:
- C4997
helpviewer_keywords:
- C4997
ms.assetid: d39678fd-0c1a-4104-8a45-9e3f20de0407
ms.openlocfilehash: 298653e7ebed272db1baa11514ac5bff27944b3c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564181"
---
# <a name="compiler-warning-level-1-c4997"></a>Предупреждение компилятора (уровень 1) C4997

"класс": компонентный класс не реализует COM-интерфейс или псевдоинтерфейс

Класс, помеченный атрибутом [coclass](../../windows/coclass.md) , не реализует интерфейс.

Следующий пример приводит к возникновению предупреждения C4997:

```
// C4997.cpp
// compile with: /WX
// to resolve this C4997, uncomment all code
#include <objbase.h>

[ object ]
__interface I {
   HRESULT func();
};

[ coclass ]
struct C /*: I*/ {
   /*
   HRESULT func() {
      return S_OK;
   }
   */
};   // C4997
```