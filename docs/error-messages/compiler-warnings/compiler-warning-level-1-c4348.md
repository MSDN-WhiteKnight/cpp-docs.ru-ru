---
title: Предупреждение компилятора (уровень 1) C4348
ms.date: 11/04/2016
f1_keywords:
- C4348
helpviewer_keywords:
- C4348
ms.assetid: 816010eb-6079-48d5-a41b-0fc4d67cfe4c
ms.openlocfilehash: b39d5a596594367d1ca2aea17d9a752c991d06be
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594185"
---
# <a name="compiler-warning-level-1-c4348"></a>Предупреждение компилятора (уровень 1) C4348

«Тип»: переопределение параметра по умолчанию: номер параметра

Параметр шаблона было переопределено.

Следующий пример приводит к возникновению ошибки C4348:

```
// C4348.cpp
// compile with: /LD /W1
template <class T=int> struct A;   // forward declaration

template <class T=int> struct A { };
// C4348, redefinition of default parameter
// try the following line instead
// template <class T> struct A { };
```