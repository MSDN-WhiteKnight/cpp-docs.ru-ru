---
title: Предупреждение командной строки D9026
ms.date: 11/04/2016
f1_keywords:
- D9026
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
ms.openlocfilehash: 3fd8d442dfabaf2f03d8b564c9fdfb1537f6ff28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599437"
---
# <a name="command-line-warning-d9026"></a>Предупреждение командной строки D9026

параметры применяются ко всей командной строке

Параметр был указан в команде, после определения имени файла. Параметр был применен к файлу, расположенному перед ним.

Например в команде

```
CL verdi.c /G5 puccini.c
```

файл VERDI.c компилируется с параметром/G5, а не по умолчанию/G4.

Это поведение отличается от некоторых предыдущих версий, в которых применяется только для тех параметров, перед именем файла, приводит к VERDI.c с помощью/G4 и PUCCINI.c компилируемого с помощью/G5.