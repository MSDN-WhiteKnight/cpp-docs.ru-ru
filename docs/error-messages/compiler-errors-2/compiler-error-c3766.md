---
title: Ошибка компилятора C3766
ms.date: 11/04/2016
f1_keywords:
- C3766
helpviewer_keywords:
- C3766
ms.assetid: b5af2089-2e1e-4e45-a41d-495b6c55656e
ms.openlocfilehash: 2d871e331987cb2731aad8b4fbc6ec2f094bd218
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518330"
---
# <a name="compiler-error-c3766"></a>Ошибка компилятора C3766

«Тип» необходимо обеспечить реализацию для интерфейса метод «function»

Класс, наследуемый от интерфейса должен реализовывать члены интерфейса.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3766.

```
// C3766.cpp
// compile with: /clr /c

delegate void MyDel();

interface struct IFace {
   virtual event MyDel ^ E;
};

ref struct Class1 : public IFace {};   // C3766

// OK
ref struct Class2 : public IFace {
   virtual event MyDel ^ E {
      void add(MyDel ^) {}
      void remove(MyDel ^) {}
   }
};
```