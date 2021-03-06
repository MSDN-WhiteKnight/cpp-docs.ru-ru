---
title: Предупреждение компилятора (уровень 1) C4733
ms.date: 11/04/2016
f1_keywords:
- C4733
helpviewer_keywords:
- C4733
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
ms.openlocfilehash: 0d0b0b912ef15294f9a4362a79dffd6d7eeabed8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474923"
---
# <a name="compiler-warning-level-1-c4733"></a>Предупреждение компилятора (уровень 1) C4733

Присваивание для «FS:0»: обработчик не зарегистрирован как безопасный

Функция, изменив значение в FS:0, чтобы добавить новый обработчик исключений может не работать с безопасных исключений, поскольку обработчик не может быть зарегистрирован как допустимый обработчик исключений (см. в разделе [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)).

Чтобы устранить это предупреждение, либо удалите определения FS:0 или отключить это предупреждение и используйте [. SAFESEH](../../assembler/masm/dot-safeseh.md) для указания безопасных обработчиков исключений.

Следующий пример приводит к возникновению ошибки C4733:

```
// C4733.cpp
// compile with: /W1 /c
// processor: x86
#include "stdlib.h"
#include "stdio.h"
void my_handler()
{
   printf("Hello from my_handler\n");
   exit(1);
}

int main()
{
   _asm {
      push    my_handler
      mov     eax, DWORD PTR fs:0
      push    eax
      mov     DWORD PTR fs:0, esp   // C4733
   }

   *(int*)0 = 0;
}
```