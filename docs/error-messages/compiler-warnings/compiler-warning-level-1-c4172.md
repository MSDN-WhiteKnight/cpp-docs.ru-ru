---
title: Компилятор предупреждение (уровень 1) C4172
ms.date: 11/04/2016
f1_keywords:
- C4172
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
ms.openlocfilehash: caa71da9182c1da1d17d87d901084d0ee9badf73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536627"
---
# <a name="compiler-warning-level-1-c4172"></a>Компилятор предупреждение (уровень 1) C4172

возвращение адреса локальной переменной или временной

Функция возвращает адрес локальной переменной или временной объекта. Локальные переменные и временные объекты уничтожаются при возврате функции, возвращаемый адрес является недопустимым.

Измените функцию, чтобы он не возвращает адрес локального объекта.

Следующий пример приводит к возникновению ошибки C4172:

```
// C4172.cpp
// compile with: /W1 /LD
float f = 10;

const double& bar() {
// try the following line instead
// const float& bar() {
   return f;   // C4172
}
```