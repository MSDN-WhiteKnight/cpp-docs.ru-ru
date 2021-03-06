---
title: Схемы сообщений (MFC)
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.messages
helpviewer_keywords:
- message maps [MFC], MFC
- Windows messages [MFC], message maps
- messages [MFC], Windows
- MFC, messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
ms.openlocfilehash: 91b7f21d92b2f899895b008b3fab8b541aec9963
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57300106"
---
# <a name="message-maps-mfc"></a>Схемы сообщений (MFC)

Ссылки в этом разделе перечислены все [макросы сопоставления сообщений](../../mfc/reference/message-map-macros-mfc.md) и все [CWnd](../../mfc/reference/cwnd-class.md) прототипы функции записей карты, а также соответствующий член:

|Категория|Описание|
|--------------|-----------------|
|ON\_команда обработчик сообщений|Обрабатывает `WM_COMMAND` сообщения, создаваемые меню выбора пользователя или клавиши доступа.|
|[Обработчики для уведомляющих сообщений дочернего окна](../../mfc/reference/child-window-notification-message-handlers.md)|Обработка уведомляющих сообщений из дочерних окон.|
|[Обработчики сообщений WM_](../../mfc/reference/handlers-for-wm-messages.md)|Обрабатывать `WM_` сообщения, такие как `WM_PAINT`.|
|[Обработчики пользовательских сообщений](../../mfc/reference/user-defined-handlers.md)|Обрабатывайте определяемые пользователем сообщения.|

(Описание терминологии и соглашения, используемые в этом справочнике, см. в разделе [Практическое использование перекрестной ссылки схемы сообщений](../../mfc/reference/how-to-use-the-message-map-cross-reference.md).)

Поскольку Windows с операционной системой, ориентированное на сообщения, большая часть программирования для среды Windows включает в себя обработку сообщений. Происходит каждый раз, щелкните событие нажатия клавиши, мыши, сообщение отправляется в приложение, которое затем необходимо обработать событие.

Библиотеки Microsoft Foundation Class предоставляет модель программирования, оптимизированный для программирования на основе сообщений. В этой модели «схемы сообщений» позволяют указать, какие функции будут обрабатывать различные сообщения для определенного класса. Схемы сообщений содержат один или несколько макросов, которые указывают, какие сообщения будут обрабатываться какие функции. Например, сообщений карты, содержащего `ON_COMMAND` макрос может выглядеть следующим образом:

[!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]

`ON_COMMAND` Макрос используется для обработки сообщения команды, создаваемые меню, кнопки и сочетания клавиш. [Макросы](../../mfc/reference/message-map-macros-mfc.md) доступны для сопоставления следующее:

## <a name="windows-messages"></a>Сообщения Windows

- Уведомления элементов управления

- Определяемые пользователем сообщения

## <a name="command-messages"></a>Сообщения команды

- Зарегистрированные определяемые пользователем сообщения

- Извещений об обновлении пользовательского интерфейса

## <a name="ranges-of-messages"></a>Диапазоны сообщений

- Команды

- Обновление обработчика сообщений

- Уведомления элементов управления

Несмотря на то, что макросы схемы сообщений имеет важное значение, обычно не придется использовать их напрямую. Дело в окне «Свойства» автоматически создает записей карты в исходные файлы при использовании должен быть сопоставлен функции обработки сообщений и сообщений. Каждый раз, когда вы хотите изменить или добавить запись схемы сообщений, можно использовать окно свойств.

> [!NOTE]
>  Окно свойств не поддерживает диапазонов схем сообщений. Эти записи схемы сообщений необходимо написать самостоятельно.

Тем не менее схемы сообщений являются важной частью библиотеки Microsoft Foundation Class. Необходимо понимать, что они делают и документация, предоставленная для них.

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
