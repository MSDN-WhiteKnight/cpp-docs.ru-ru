---
title: Ошибка компилятора C2480
ms.date: 11/04/2016
f1_keywords:
- C2480
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
ms.openlocfilehash: 90016b65d4ddd58da3fb3c5ab6d81322dc0ef394
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566729"
---
# <a name="compiler-error-c2480"></a>Ошибка компилятора C2480

«Идентификатор»: «thread» допускается только для статических элементов данных

Нельзя использовать `thread` атрибут с автоматической переменной, нестатический элемент данных, параметр функции, а также в объявлениях или определениях функций.

Используйте `thread` атрибут для глобальные переменные, статические данные-члены и только локальные статические переменные.

Следующий пример приводит к возникновению ошибки C2480:

```
// C2480.cpp
// compile with: /c
__declspec( thread ) void func();   // C2480
__declspec( thread ) static int i;   // OK
```