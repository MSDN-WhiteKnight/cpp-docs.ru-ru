---
title: Ошибка компилятора C2507
ms.date: 11/04/2016
f1_keywords:
- C2507
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
ms.openlocfilehash: 63f9594eb9ee8a251faafe7323418b343c03063c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618036"
---
# <a name="compiler-error-c2507"></a>Ошибка компилятора C2507

«Идентификатор»: слишком много виртуальных модификаторов для базового класса

Класс или структура объявляется как `virtual` более одного раза. Только один `virtual` модификатор может отображаться для каждого класса в списке базовых классов.

Следующий пример приводит к возникновению ошибки C2507:

```
// C2507.cpp
// compile with: /c
class A {};
class B : virtual virtual public A {};   // C2507
class C : virtual public A {};   // OK
```