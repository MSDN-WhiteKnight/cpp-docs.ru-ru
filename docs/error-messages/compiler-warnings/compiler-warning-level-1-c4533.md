---
title: Предупреждение компилятора (уровень 1) C4533
ms.date: 11/04/2016
f1_keywords:
- C4533
helpviewer_keywords:
- C4533
ms.assetid: 359fecda-d540-46e5-b214-dbabe9ef50d2
ms.openlocfilehash: 8ac7f00ad3401e88224c0150324822ce71e95018
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652170"
---
# <a name="compiler-warning-level-1-c4533"></a>Предупреждение компилятора (уровень 1) C4533

Пропуск инициализации «переменной», «инструкции»

Инструкции в программе изменить поток управления, таким образом, что не была выполнена инструкция, инициализирующая переменную. Следующий пример приводит к возникновению ошибки C4533:

```
// C4533.cpp
// compile with: /W1
#include <stdio.h>

struct A
{
   int m_data;
};

int main()
{
   if (1)
   {
      goto Label;
   }

   A a = { 100 };

   Label:   // C4533
      printf("\n%d", a.m_data);   // prints an uninitialized value
}
```