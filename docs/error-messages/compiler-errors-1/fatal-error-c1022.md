---
title: Неустранимая ошибка C1022
ms.date: 11/04/2016
f1_keywords:
- C1022
helpviewer_keywords:
- C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
ms.openlocfilehash: 044ebbbe895677acf74977e56879c292486e18cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432569"
---
# <a name="fatal-error-c1022"></a>Неустранимая ошибка C1022

непредвиденный #endif

Директива `#if`, `#ifdef`или `#ifndef` не имеет соответствующей директивы `#endif` . Убедитесь, что каждая директива `#if`, `#ifdef`или `#ifndef` имеет соответствующую директиву `#endif`.

В следующем примере возникает ошибка C1022:

```
// C1022.cpp
#define true 1

#if (true)
#else
#else    // C1022
```

Возможное решение

```
// C1022b.cpp
// compile with: /c
#define true 1

#if (true)
#else
#endif
```