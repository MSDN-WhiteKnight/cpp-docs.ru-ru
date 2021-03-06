---
title: Предупреждение компилятора (уровень 3) C4414
ms.date: 11/04/2016
f1_keywords:
- C4414
helpviewer_keywords:
- C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
ms.openlocfilehash: 0a9ceb332888e306b8cb3bcbe1832f773d02d63d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629818"
---
# <a name="compiler-warning-level-3-c4414"></a>Предупреждение компилятора (уровень 3) C4414

«функция»: короткий переход к функции преобразован в Ближний переход

Сокращенный переход генерирует компактную инструкцию, которая разветвляется на адреса в ограниченном диапазоне из инструкции. Инструкция включает короткое смещение, которое представляет расстояние между переходом и конечным адресом, определение функции. Во время компоновки функция может быть перемещена или подвергнута оптимизации во время компоновки, которые вызывают функцию за пределы диапазона, доступного из короткого смещения. Компилятор должен создать конкретную запись для перехода, который требуется инструкция jmp БЛИЖАЙШЕМ или ДАЛЕКО. Компилятор сделал преобразование.

Например следующий код создает C4414:

```
// C4414.cpp
// compile with: /W3 /c
// processor: x86
int DoParityEven();
int DoParityOdd();
unsigned char global;
int __declspec(naked) DoParityEither()
{
   __asm
   {
      test global,0
      jpe SHORT DoParityEven  // C4414
      jmp SHORT DoParityOdd   // C4414
   }
}
```