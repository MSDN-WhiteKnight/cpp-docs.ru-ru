---
title: Ошибка компилятора C2117
ms.date: 11/04/2016
f1_keywords:
- C2117
helpviewer_keywords:
- C2117
ms.assetid: b947379d-5861-42fc-ac26-170318579cbd
ms.openlocfilehash: 2f6a1e26972f093e50c5e655935f750195ab7d3b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435169"
---
# <a name="compiler-error-c2117"></a>Ошибка компилятора C2117

«Идентификатор»: переполнение границ массива

Массив имеет слишком много инициализаторов:

- Размер и количество инициализаторов и элементов массива не совпадают.

- Нет места для завершающего в строке.

Следующий пример приводит к возникновению ошибки C2117:

```
// C2117.cpp
int main() {
   char abc[4] = "abcd";   // C2117
   char def[4] = "abd";   // OK
}
```