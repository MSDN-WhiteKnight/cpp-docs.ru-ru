---
title: Ошибка компилятора C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: 3f32307e519394433927d49aa92333fdff7b70f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587516"
---
# <a name="compiler-error-c2883"></a>Ошибка компилятора C2883

«name»: объявление функции вступает в конфликт с «идентификатор», представленное в объявление using

Предпринята попытка определить функцию более одного раза. Первое определение был сделан из пространства имен с `using` объявления. Вторая была локальное определение.

Следующий пример приводит к возникновению ошибки C2883:

```
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```