---
title: Ошибка компилятора C2457
ms.date: 11/04/2016
f1_keywords:
- C2457
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
ms.openlocfilehash: a08ac9f9cfbc332b90ad16c663349ee227427278
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446644"
---
# <a name="compiler-error-c2457"></a>Ошибка компилятора C2457

> "*макрос*": добавлен предустановленный макрос не может находиться вне тела функции

Предпринята попытка использования предопределенного макроса, такие как [ &#95; &#95;ФУНКЦИЯ&#95;&#95;](../../preprocessor/predefined-macros.md), в глобальном пространстве.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2457, а также показано правильное использование:

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```