---
title: Предупреждение компилятора (уровень 1) C4667
ms.date: 11/04/2016
f1_keywords:
- C4667
helpviewer_keywords:
- C4667
ms.assetid: 5d2b7fe0-4f0e-4cd6-b432-ca02c3d194ab
ms.openlocfilehash: 685cdc2577e1207360c793c82808919c39753f49
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496555"
---
# <a name="compiler-warning-level-1-c4667"></a>Предупреждение компилятора (уровень 1) C4667

«функция»: функция шаблон не определен, соответствующий принудительному созданию экземпляра

Не удается создать экземпляр шаблона функции, который не был объявлен.

Следующий пример вызывает ошибку C4667:

```
// C4667a.cpp
// compile with: /LD /W1
template
void max(const int &, const int &); // C4667 expected
```

Чтобы устранить это предупреждение, необходимо сначала объявите шаблон функции:

```
// C4667b.cpp
// compile with: /LD
// Declare the function template
template<typename T>
const T &max(const T &a, const T &b) {
   return (a > b) ? a : b;
}
// Then forcibly instantiate it with a desired type ... i.e. 'int'
//
template
const int &max(const int &, const int &);
```