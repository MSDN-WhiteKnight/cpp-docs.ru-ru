---
title: Предупреждение компилятора (уровень 1) C4684
ms.date: 11/04/2016
f1_keywords:
- C4684
helpviewer_keywords:
- C4684
ms.assetid: e95f1a83-2784-4b05-ae94-12148e056e26
ms.openlocfilehash: 8ba3d75ecb370ac86c9a6ab47f05dd49fc12ba23
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479122"
---
# <a name="compiler-warning-level-1-c4684"></a>Предупреждение компилятора (уровень 1) C4684

«атрибут»: предупреждение!! атрибут может привести к недействительного кода: используйте с осторожностью

Вы использовали атрибут, который обычно не следует использовать.

Следующий пример приводит к возникновению ошибки C4684:

```
// C4684.cpp
// compile with: /W1 /LD
[module(name="xx")]; // C4684 expected
[no_injected_text];
```