---
title: Предупреждение компилятора (уровень 1) C4230
ms.date: 11/04/2016
f1_keywords:
- C4230
helpviewer_keywords:
- C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
ms.openlocfilehash: c8d223a286b8d42ca404fbfe7cbc51b67b3dd497
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529677"
---
# <a name="compiler-warning-level-1-c4230"></a>Предупреждение компилятора (уровень 1) C4230

устаревший элемент: модификаторов и квалификаторов; пропуск квалификатора

С помощью квалификаторов перед модификатором Майкрософт, таких как `__cdecl` устарело.

## <a name="example"></a>Пример

```
// C4230.cpp
// compile with: /W1 /LD
int __cdecl const function1();   // C4230 const ignored
```