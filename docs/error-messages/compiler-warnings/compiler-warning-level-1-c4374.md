---
title: Предупреждение компилятора (уровень 1) C4374
ms.date: 11/04/2016
f1_keywords:
- C4374
helpviewer_keywords:
- C4374
ms.assetid: 4ac9aaec-d815-4b6e-825f-fa872092dd3b
ms.openlocfilehash: 5cf18a3dcd94f59ce1ae8feb675f251bea5715a5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652287"
---
# <a name="compiler-warning-level-1-c4374"></a>Предупреждение компилятора (уровень 1) C4374

«функция1»: метод интерфейса не будет реализован невиртуальным методом «функция2»

Компилятор ожидает найти [виртуального](../../cpp/virtual-specifier.md) ключевое слово в определении метода.

Следующий пример приводит к возникновению ошибки C4374:

```
// C4374.cpp
// compile with: /clr /W1 /c /WX
public interface class I {
   void f();
};

public ref struct B {
   void f() {
      System::Console::WriteLine("B::f()");
   }
};

public ref struct C {
   virtual void f() {
      System::Console::WriteLine("C::f()");
   }
};

public ref struct D : B, I {};   // C4374
public ref struct E : C, I {};   // OK
```