---
title: Неустранимая ошибка C1071
ms.date: 11/04/2016
f1_keywords:
- C1071
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
ms.openlocfilehash: 8fe6b0f3bb1253f72c97f29070ba81cdbdf80508
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506708"
---
# <a name="fatal-error-c1071"></a>Неустранимая ошибка C1071

непредвиденное обнаружение конца файла в комментарии

Компилятор достигнут конец файла при просмотре комментария.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Отсутствует признак конца комментария (* /).

1. Отсутствует символ перевода строки после комментария в последней строке исходного файла.

Следующий пример приводит к возникновению ошибки C1071:

```
// C1071.cpp
int main() {
}

/* this comment is fine */
/* forgot the closing tag        // C1071
```