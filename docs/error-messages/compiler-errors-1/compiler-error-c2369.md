---
title: Ошибка компилятора C2369
ms.date: 11/04/2016
f1_keywords:
- C2369
helpviewer_keywords:
- C2369
ms.assetid: 2a3933f6-2313-40ff-800f-921b296fdbbf
ms.openlocfilehash: 8abb9a7b8d15fa2dd9999612551a0d0da1e34e30
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500473"
---
# <a name="compiler-error-c2369"></a>Ошибка компилятора C2369

"массив": переопределение; разные индексы

Массив уже объявлен с другим индексом.

В следующем примере возникает ошибка C2369:

```
// C2369.cpp
// compile with: /c
int a[10];
int a[20];   // C2369
int b[20];   // OK
```