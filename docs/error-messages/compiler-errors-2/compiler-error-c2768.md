---
title: Ошибка компилятора C2768
ms.date: 11/04/2016
f1_keywords:
- C2768
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
ms.openlocfilehash: 9c0fb8fb0a98830aaf061ba980e7bdd7903f25e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626178"
---
# <a name="compiler-error-c2768"></a>Ошибка компилятора C2768

«функция»: Недопустимое использование явных аргументов шаблона

Компилятору не удалось определить, если определение функции должна быть явной специализации шаблона функции или определении функции должна быть новой функции.

Эта ошибка появилась в Visual Studio .NET 2003, в рамках улучшения соответствия компилятора.

Следующий пример приводит к возникновению ошибки C2768:

```
// C2768.cpp
template<typename T>
void f(T) {}

void f<int>(int) {}   // C2768

// an explicit specialization
template<>
void f<int>(int) {}

// global nontemplate function overload
void f(int) {}
```