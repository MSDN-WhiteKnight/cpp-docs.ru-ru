---
title: Ошибка компилятора C2422
ms.date: 11/04/2016
f1_keywords:
- C2422
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
ms.openlocfilehash: 524eeadb6cf066d3eba3a7e88c45a9e2b993c0ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509139"
---
# <a name="compiler-error-c2422"></a>Ошибка компилятора C2422

Недопустимое переопределение сегмента в «операнд»

Встроенный код ассемблера неправильно использует оператор переопределения сегмента (двоеточие) для операнда.  Возможные причины:

- Регистр, перед оператором не регистр.

- Регистр, перед оператором не только регистром сегмента в операнде.

- Переопределение segment, оператор отображается в оператор косвенного обращения (скобки).

- Выражения, следующего оператора переопределения сегмента не непосредственного операнда или операндов памяти.

Следующий пример приводит к возникновению ошибки C2422:

```
// C2422.cpp
// processor: x86
int main() {
   _asm {
      mov AX, [BX:ES]   // C2422
      mov AX, ES   // OK
   }
}
```