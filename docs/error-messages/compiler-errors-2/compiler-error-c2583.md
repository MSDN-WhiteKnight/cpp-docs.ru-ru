---
title: Ошибка компилятора C2583
ms.date: 11/04/2016
f1_keywords:
- C2583
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
ms.openlocfilehash: b78b9dd69b701e1a66646234d4603973657e90c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597981"
---
# <a name="compiler-error-c2583"></a>Ошибка компилятора C2583

«Идентификатор»: «const или volatile» указатель «this» является недопустимым для конструкторов и деструкторов

Конструктор или деструктор был объявлен `const` или `volatile`. Это не допускается.

Следующий пример приводит к возникновению ошибки C2583:

```
// C2583.cpp
// compile with: /c
class A {
public:
   int i;
   A() const;   // C2583

   // try the following line instead
   // A();
};
```