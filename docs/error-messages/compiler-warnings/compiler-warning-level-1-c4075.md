---
title: Предупреждение компилятора (уровень 1) C4075
ms.date: 11/04/2016
f1_keywords:
- C4075
helpviewer_keywords:
- C4075
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
ms.openlocfilehash: f739e0363cc08d31bd26b063ef13658a392398bd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486389"
---
# <a name="compiler-warning-level-1-c4075"></a>Предупреждение компилятора (уровень 1) C4075

инициализаторы в неопознанной области инициализации

Директива [#pragma init_seg](../../preprocessor/init-seg.md) использует неизвестное имя раздела. Компилятор игнорирует команду **pragma** .

В следующем примере возникает ошибка C4075.

```
// C4075.cpp
// compile with: /W1
#pragma init_seg("mysegg")   // C4075

// try..
// #pragma init_seg(user)

int main() {
}
```