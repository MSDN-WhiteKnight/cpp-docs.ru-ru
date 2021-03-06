---
title: Использование полей обратного вызова элемента выбора даты и времени
ms.date: 11/04/2016
f1_keywords:
- DTN_FORMATQUERY
- DTN_FORMAT
helpviewer_keywords:
- DateTimePicker control [MFC], callback fields
- callback fields in CDateTimeCtrl class [MFC]
- CDateTimeCtrl class [MFC], callback fields
- CDateTimeCtrl class [MFC], handling DTN_FORMAT and DTN_FORMATQ
- DTN_FORMATQUERY notification [MFC]
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
ms.openlocfilehash: 874f73df3dda3a720d4346ae3fb0136c662221db
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299404"
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>Использование полей обратного вызова элемента выбора даты и времени

Кроме стандартные символы форматирования, которые определяют поля выбора даты и времени можно настроить выходные данные, указав определенные части строка настраиваемого формата в качестве полей обратного вызова. Чтобы объявить поле обратного вызова, включите в один или несколько символов «X» (88 код ASCII) в любом месте строки формата. Например, следующая строка «"сегодня —: «yy» / «Мм» и «ДД» (день «X»)" «заставляет элемент управления выбора даты и времени для отображения текущего значения в виде года, следуют месяца, даты и, наконец, день года.

> [!NOTE]
>  Количество символов x в обратном вызове поле не соответствует количеству символов, которые будут отображаться.

Может различать несколько полей обратного вызова в настраиваемую строку путем повтора символа «X». Таким образом, строка формата «XXddddMMMdd "," yyyXXX» содержит два поля уникальный обратного вызова, «XX» и «XXX».

> [!NOTE]
>  Поля обратного вызова, рассматриваются как действительные поля, поэтому приложение должно быть готово для обработки сообщений уведомления DTN_WMKEYDOWN.

Реализация полей обратного вызова в элементе управления выбора даты и времени состоит из трех частей:

- Инициализация строку пользовательского формата

- Обработка dtn_formatquery-уведомление

- Обработка dtn_format-уведомление

## <a name="initializing-the-custom-format-string"></a>Инициализация строку пользовательского формата

Инициализирует строку пользовательского вызовом `CDateTimeCtrl::SetFormat`. Дополнительные сведения см. в разделе [с помощью строки настраиваемых форматов даты и времени средства выбора](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md). Чаще всего для настройки строки настраиваемого формата, используется в `OnInitDialog` функции содержащего классов диалоговых окон или `OnInitialUpdate` функция содержащего класса представления.

## <a name="handling-the-dtnformatquery-notification"></a>Обработка dtn_formatquery-уведомление

Если элемент управления выполняет синтаксический анализ строки формата, а также достигает поле обратного вызова, приложение отправляет DTN_FORMAT и DTN_FORMATQUERY сообщений уведомления. Строка поля обратного вызова входит в состав уведомления, чтобы можно было определить, какое поле обратного вызова выполняется запрос.

Dtn_formatquery-уведомление отправляется для получения максимально допустимый размер в пикселях строки, который будет отображаться в текущее поле обратного вызова.

Чтобы правильно вычислить это значение, необходимо вычислить высоту и ширину строки, должен быть замещен поле, в шрифтом отображения элемента управления. Вычисления строки легко осуществляется с помощью вызова [GetTextExtentPoint32](/windows/desktop/api/wingdi/nf-wingdi-gettextextentpoint32a) функции Win32. После определения размера, передайте значение в приложение и выйдите из функции обработчика.

Ниже приведен один способ указания размер строки обратного вызова:

[!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]

После вычисления размера текущего поля обратного вызова, необходимо указать значение для поля. Это делается в обработчике dtn_format-уведомление.

## <a name="handling-the-dtnformat-notification"></a>Обработка dtn_format-уведомление

Dtn_format-уведомление используется приложением для запроса символьная строка, будут заменены. В следующем примере показано одно из возможных способов:

[!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]

> [!NOTE]
>  Указатель на **NMDATETIMEFORMAT** найден структуры путем приведения первый параметр обработчика уведомлений к нужному типу.

## <a name="see-also"></a>См. также

[Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
