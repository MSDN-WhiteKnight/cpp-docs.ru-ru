---
title: Ошибка компилятора C2195
ms.date: 11/04/2016
f1_keywords:
- C2195
helpviewer_keywords:
- C2195
ms.assetid: 9f9f035c-9c51-4173-a8ea-c6f907fc5c63
ms.openlocfilehash: 9d0fdb3623a86adb07e910b186305f3e468d24b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606457"
---
# <a name="compiler-error-c2195"></a>Ошибка компилятора C2195

«Идентификатор»: является сегментом данных

`code_seg` Pragma использует имя сегмента с `data_seg` директивы pragma.

Следующий пример приводит к возникновению ошибки C2195:

```
// C2195.cpp
#pragma data_seg("MYDATA")
#pragma code_seg("MYDATA")   // C2195
#pragma code_seg("MYDATA2")   // OK
```