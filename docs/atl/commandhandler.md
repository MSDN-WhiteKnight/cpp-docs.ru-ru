---
title: CommandHandler
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CommandHandler
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
ms.openlocfilehash: c8ae2ae3b68b01c00ce1c6441fa9a3150d4c334b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285065"
---
# <a name="commandhandler"></a>CommandHandler

`CommandHandler` функция, определяемая параметром третий параметр макроса COMMAND_HANDLER в схему сообщения.

## <a name="syntax"></a>Синтаксис

```cpp
LRESULT CommandHandler(
    WORD wNotifyCode,
    WORD wID,
    HWND hWndCtl,
    BOOL& bHandled);
```

#### <a name="parameters"></a>Параметры

*wNotifyCode*<br/>
Код уведомления.

*wID*<br/>
Идентификатор пункта меню, элемент управления или сочетаний клавиш.

*hWndCtl*<br/>
Дескриптор окна элемента управления.

*bHandled*<br/>
Карта наборов сообщений *bHandled* значение TRUE перед `CommandHandler` вызывается. Если `CommandHandler` не полностью обрабатывает сообщение, она должна задать *bHandled* значение false, чтобы указать, должна дальнейшей обработки сообщения.

## <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщения. 0 в случае успеха.

## <a name="remarks"></a>Примечания

Пример использования этого обработчика сообщений в схеме сообщений, см. в разделе [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler).

## <a name="see-also"></a>См. также

[Реализация окна](../atl/implementing-a-window.md)<br/>
[Схемы сообщений](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/desktop/controls/wm-notify)
