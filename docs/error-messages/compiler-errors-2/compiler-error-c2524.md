---
title: Ошибка компилятора C2524
ms.date: 11/04/2016
f1_keywords:
- C2524
helpviewer_keywords:
- C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
ms.openlocfilehash: 369aa5f21c072472808ffba06c3bc5c5e608ac22
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640119"
---
# <a name="compiler-error-c2524"></a>Ошибка компилятора C2524

«деструктор»: метод завершения или деструктор должен иметь список параметров «void»

Деструктор или метод завершения бы список параметров, не [void](../../cpp/void-cpp.md). Другие типы параметров не разрешены.

## <a name="example"></a>Пример

Следующий код приводит к возникновению C2524.

```
// C2524.cpp
// compile with: /c
class A {
   A() {}
   ~A(int i) {}    // C2524
   // try the following line instead
   // ~A() {}
};
```

## <a name="example"></a>Пример

Следующий код приводит к возникновению C2524.

```
// C2524_b.cpp
// compile with: /clr /c
ref struct I1 {
protected:
   !I1(int i);   // C2524
   // try the following line instead
   // !I1();
};
```