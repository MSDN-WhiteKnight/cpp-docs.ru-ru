---
title: Ошибка компилятора C3252
ms.date: 11/04/2016
f1_keywords:
- C3252
helpviewer_keywords:
- C3252
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
ms.openlocfilehash: ee9245fb8eb89b9234e76dc10304b1d05bc1fdcb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600386"
---
# <a name="compiler-error-c3252"></a>Ошибка компилятора C3252

method: нельзя уменьшить доступность виртуального метода в управляемом типе или типе WinRT

Класс, реализующий виртуальный метод из базового класса или любой метод интерфейса, не может понизить уровень доступа этого метода.

Обратите внимание, что все методы интерфейса являются открытыми.

В следующем примере показано возникновение ошибки C3252 и приводятся сведения по ее устранению.

```
// C3252.cpp
// compile with: /clr /c
ref class A {
public:
   virtual void f1() {}
};

ref class B : public A {
// To fix, uncomment the following line:
// public:
   virtual void f1() override sealed {}   // C3252, make this method public
};
```