---
title: Ошибка компилятора C3210
ms.date: 11/04/2016
f1_keywords:
- C3210
helpviewer_keywords:
- C3210
ms.assetid: c6e9d309-fabc-4e7d-b526-be20d9fe3f6a
ms.openlocfilehash: 9e0ac1aded7eef40be0e923b3ac1ebc9ef00c7a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528743"
---
# <a name="compiler-error-c3210"></a>Ошибка компилятора C3210

«Тип»: объявление доступа может применяться только к члену базового класса

Объект [объявление using](../../cpp/using-declaration.md) указан неправильно.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3210.

```
// C3210.cpp
// compile with: /c
struct A {
protected:
   int i;
};

struct B {
   using A::i;   // C3210
};

struct C : public A {
   using A::i;   // OK
};
```