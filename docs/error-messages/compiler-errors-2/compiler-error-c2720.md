---
title: Ошибка компилятора C2720
ms.date: 11/04/2016
f1_keywords:
- C2720
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
ms.openlocfilehash: c6499fd3f279099ea7c5b31860e70bdaa285e3f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638598"
---
# <a name="compiler-error-c2720"></a>Ошибка компилятора C2720

> "*идентификатор*": "*описатель*" спецификатор класса хранения недопустим для членов

Класс хранения нельзя использовать для членов класса вне объявления. Чтобы устранить эту ошибку, удалите ненужный [класс хранения](../../cpp/storage-classes-cpp.md) описатель из определения члена вне объявления класса.

## <a name="example"></a>Пример

В следующем примере показано возникновение ошибки C2720 и приводятся сведения по ее устранению.

```cpp
// C2720.cpp
struct S {
   static int i;
};
static S::i;   // C2720 - remove the unneeded 'static' to fix it
```