---
title: Ошибка компилятора C3485
ms.date: 11/04/2016
f1_keywords:
- C3485
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
ms.openlocfilehash: 09080a402767835cda9711c2f0fc4d7c8d787439
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508035"
---
# <a name="compiler-error-c3485"></a>Ошибка компилятора C3485

определение лямбда-выражения не может содержать cv-квалификаторы

Нельзя использовать квалификатор `const` или `volatile` как часть определения лямбда-выражения.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите квалификатор `const` или `volatile` из определения лямбда-выражения.

## <a name="example"></a>Пример

Приведенный ниже пример приводит к возникновению ошибки C3485, так как в нем квалификатор `const` используется как часть определения лямбда-выражения.

```
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)