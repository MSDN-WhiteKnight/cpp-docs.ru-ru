---
title: Обновление пользовательского интерфейса для представлений записей (доступ к данным MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
ms.openlocfilehash: 914a262560a10ba4085e0605a0c9f677d7a447fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630403"
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>Обновление пользовательского интерфейса для представлений записей (доступ к данным MFC)

`CRecordView` предоставляет обработчики обновления пользовательского интерфейса по умолчанию для команд перехода. Эти обработчики автоматически включают и отключают объекты пользовательского интерфейса — пункты меню и кнопки панели инструментов. Мастер приложений предоставляет стандартные меню и, если выбрать **Закрепляемая панель инструментов** набор кнопок панели инструментов для команд, параметров. Если создан класс представления записей с помощью `CRecordView`, можно добавлять подобные объекты пользовательского интерфейса в приложение.

### <a name="to-create-menu-resources-with-the-menu-editor"></a>Создание ресурсов меню с помощью редактора меню

1. Сверяясь со сведениями об использовании [редактор меню](../windows/menu-editor.md), создайте собственное меню с аналогичными четырьмя командами.

#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>Создание кнопок панели инструментов с помощью графического редактора

1. Сверяясь со сведениями об использовании [редактор панелей инструментов](../windows/toolbar-editor.md), отредактируйте ресурс панели инструментов, чтобы добавить кнопки панели инструментов для команд перехода.

## <a name="see-also"></a>См. также

[Поддержка навигации в представлении записей](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)<br/>
[Использование представления записей](../data/using-a-record-view-mfc-data-access.md)