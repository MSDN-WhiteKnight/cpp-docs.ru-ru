---
title: Обработка уведомляющих сообщений элемента управления "Вкладка"
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
ms.openlocfilehash: 4be9074f3e7d7ce4321402d27fc26283a52436e9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267307"
---
# <a name="processing-tab-control-notification-messages"></a>Обработка уведомляющих сообщений элемента управления "Вкладка"

При щелчке вкладки или кнопок, вкладок ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) отправляет сообщения уведомления своему родительскому окну. Обрабатывайте эти сообщения, если требуется сделать что-нибудь в ответе. Например при щелчке вкладки, может потребоваться предустановку данных элемента управления на странице перед его отображением.

Обработка сообщения WM_NOTIFY из вкладок в классе представления или диалогового окна. Используйте окно свойств для создания [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) функцию обработчика с оператором switch зависимости от того, какие сообщения уведомления обрабатывается. Список уведомлений, набор вкладок можно отправить своему родительскому окну, см. в разделе **уведомления** раздел [ссылки на элемент управления вкладки](/windows/desktop/controls/tab-control-reference) в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Использование CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
