---
title: Предупреждение компилятора (уровень 1) C4377
ms.date: 11/04/2016
f1_keywords:
- C4377
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
ms.openlocfilehash: d8c89967e0dc900e098ca03d22932451f26a6a0a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531036"
---
# <a name="compiler-warning-level-1-c4377"></a>Предупреждение компилятора (уровень 1) C4377

собственные типы являются закрытыми по умолчанию; -d1PrivateNativeTypes запрещен

В предыдущих выпусках собственные типы в сборках были открытыми по умолчанию и параметр компилятора внутренней, недокументированной (**/d1PrivateNativeTypes**) был использован для их преобразования в закрытый.

Все типы в собственном и CLR, теперь по умолчанию являются частными в сборке, поэтому **/d1PrivateNativeTypes** больше не используется.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4377.

```
// C4377.cpp
// compile with: /clr /d1PrivateNativeTypes /W1
// C4377 warning expected
int main() {}
```