---
title: Ошибка компилятора C2165
ms.date: 11/04/2016
f1_keywords:
- C2165
helpviewer_keywords:
- C2165
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
ms.openlocfilehash: 1dadc56dafca056db9b4a14ab39127306b797f8a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570395"
---
# <a name="compiler-error-c2165"></a>Ошибка компилятора C2165

"ключевое_слово": невозможно изменить указатели на данные

Ключевое слово `__stdcall`, `__cdecl`или `__fastcall` пытается изменить указатель на данные.

Следующий пример приводит к возникновению ошибки C2165:

```
// C2165.cpp
// compile with: /c
char __cdecl *p;   // C2165
char *p;   // OK
```