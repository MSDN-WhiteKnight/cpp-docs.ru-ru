---
title: Некритичная ошибка ML A2006
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2006
helpviewer_keywords:
- A2006
ms.assetid: b8a8f096-95df-42b5-85ed-d2530560a84c
ms.openlocfilehash: 80283bde4dff36e32d276c998f6797b6eeed8160
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490068"
---
# <a name="ml-nonfatal-error-a2006"></a>Некритичная ошибка ML A2006

**Неопределенный символ: идентификатор**

Была предпринята попытка использовать символ, который не был определен.

Мог произойти одно из следующих:

- Символ не определен.

- Поле не является членом указанной структуры.

- Символ был определен во включаемом файле, который не был включен.

- Внешний символ был использован без [EXTERN](../../assembler/masm/extern-masm.md) или [EXTERNDEF](../../assembler/masm/externdef.md) директива.

- Было неправильно указано имя символа.

- Ссылка на метку локальный код за пределами его области.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>