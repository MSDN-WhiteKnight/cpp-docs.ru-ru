---
title: NotifyHandler
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- NotifyHandler
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
ms.openlocfilehash: 204309c334a8f5cd5be702bba016678537d66211
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275705"
---
# <a name="notifyhandler"></a>NotifyHandler

Имя функции, заданных третий параметр макроса NOTIFY_HANDLER в схему сообщения.

## <a name="syntax"></a>Синтаксис

```cpp
LRESULT NotifyHandler(
    int idCtrl,
    LPNMHDR pnmh,
    BOOL& bHandled);
```

#### <a name="parameters"></a>Параметры

*idCtrl*<br/>
Идентификатор элемента управления, отправляющего сообщения.

*pnmh*<br/>
Адрес [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr) структуру, содержащую код уведомления и Дополнительные сведения. Для некоторых сообщений уведомлений, этот параметр указывает на структуру большего размера, имеет `NMHDR` структуру, что ее первого элемента.

*bHandled*<br/>
Карта наборов сообщений *bHandled* значение TRUE перед *NotifyHandler* вызывается. Если *NotifyHandler* не полностью обрабатывает сообщение, она должна задать *bHandled* для **FALSE** для указания сообщения требуется дополнительная обработка.

## <a name="return-value"></a>Возвращаемое значение

Результат обработки сообщения. 0 в случае успеха.

## <a name="remarks"></a>Примечания

Пример использования этого обработчика сообщений в схеме сообщений, см. в разделе [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).

## <a name="see-also"></a>См. также

[Реализация окна](../atl/implementing-a-window.md)<br/>
[Схемы сообщений](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/desktop/controls/wm-notify)
