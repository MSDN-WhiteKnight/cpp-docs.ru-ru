---
title: Некритичная ошибка ML A2096
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2096
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
ms.openlocfilehash: e6b31afeff801e7128b5a76576e9eaa3398f68e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676282"
---
# <a name="ml-nonfatal-error-a2096"></a>Некритичная ошибка ML A2096

**Сегмент, группы или ожидается регистр**

Сегмент или группы ожидался, но не найден.

Одной из следующих причин:

- Левый операнд, указанный с сегментом переопределить оператор (**:**) не сегмент register (CS, DS, SS, ES, FS или GS), имя группы, имя сегмента или выражение сегмента.

- [Предположим, ЧТО](../../assembler/masm/assume.md) директива передан регистр без адрес допустимый сегмент, регистр, группы или специальную **НЕСТРУКТУРИРОВАННЫЙ** группы.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>