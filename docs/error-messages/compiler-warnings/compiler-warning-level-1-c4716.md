---
title: Предупреждение компилятора (уровень 1) C4716
ms.date: 11/04/2016
f1_keywords:
- C4716
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
ms.openlocfilehash: 5ec0aea543053d699db7483df7dd7ea91b3af715
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594549"
---
# <a name="compiler-warning-level-1-c4716"></a>Предупреждение компилятора (уровень 1) C4716

Функция "функция" должна возвращать значение

Данная функция не возвратил значение.

Работает только с типом возвращаемого значения void может использовать команду возвращения без возвращаемого значения.

При вызове этой функции, возвращается неопределенное значение.

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить это поведение, используйте [#pragma warning](../../preprocessor/warning.md).

Следующий пример приводит к возникновению ошибки C4716:

```
// C4716.cpp
// compile with: /c /W1
// C4716 expected
#pragma warning(default:4716)
int test() {
   // uncomment the following line to resolve
   // return 0;
}
```