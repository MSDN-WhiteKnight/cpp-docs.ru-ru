---
title: Ошибка компилятора C2274
ms.date: 11/04/2016
f1_keywords:
- C2274
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
ms.openlocfilehash: f2fcb75098f18ad113ba68959035b37d9cddd6e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667029"
---
# <a name="compiler-error-c2274"></a>Ошибка компилятора C2274

«Тип»: недопустимо в качестве правой части выражения "." оператор

Тип отображается как правый операнд оператора доступа к членам (.).

Эта ошибка может быть вызвана пытается получить доступ к преобразования определяемого пользователем типа. Используйте ключевое слово `operator` между период и `type`.

При компиляции следующего примера возникнет ошибка C2286:

```
// C2274.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};

int main() {
   MyClass ClassName;
   int i = ClassName.int();   // C2274
   int j = ClassName.operator int();   // OK
}
```