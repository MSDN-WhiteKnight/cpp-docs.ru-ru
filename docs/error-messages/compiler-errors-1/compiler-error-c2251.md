---
title: Ошибка компилятора C2251
ms.date: 11/04/2016
f1_keywords:
- C2251
helpviewer_keywords:
- C2251
ms.assetid: fefe050c-f8d3-4316-b237-8007dbcdd3bf
ms.openlocfilehash: b7ffb5b8d425e74523e491827ffb8878b8e03b38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452342"
---
# <a name="compiler-error-c2251"></a>Ошибка компилятора C2251

в пространстве имен "пространство_имен" отсутствует член "член" — имелся в виду "член"?

Компилятору не удалось обнаружить идентификатор в указанном пространстве имен.

В следующем примере возникает ошибка C2251:

```
// C2251.cpp
// compile with: /c
namespace A {
   namespace B {
      void f1();
   }

   using namespace B;
}

void A::f1() {}   // C2251
void A::B::f1() {}   // OK
```