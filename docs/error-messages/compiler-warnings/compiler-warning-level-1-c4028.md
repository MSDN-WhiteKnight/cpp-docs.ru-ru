---
title: Компилятор предупреждение (уровень 1) C4028
ms.date: 11/04/2016
f1_keywords:
- C4028
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
ms.openlocfilehash: bfe54fc40b4d6927a1d75f529ec9b619f9b29226
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490523"
---
# <a name="compiler-warning-level-1-c4028"></a>Компилятор предупреждение (уровень 1) C4028

формальный параметр «число» отличается от объявления

Тип формального параметра не совпадает с соответствующим параметром в объявлении. Тип в исходном объявлении используется.

Это предупреждение допустимо только для C исходного кода.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4028.

```
// C4028.c
// compile with: /W1 /Za
void f(int , ...);
void f(int i, int j) {}   // C4028

void g(int , int);
void g(int i, int j) {}   // OK

int main() {}
```