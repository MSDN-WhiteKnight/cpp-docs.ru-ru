---
title: Предопределенные символы ATL
ms.date: 02/14/2019
helpviewer_keywords:
- symbols [C++], ATL predefined
- ATL symbols
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
ms.openlocfilehash: 16991746c5c858310466f7eebd91a8478d2dcc5c
ms.sourcegitcommit: f127b08f114b8d6cab6b684febcb6f2ae0e055ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2019
ms.locfileid: "56954852"
---
# <a name="atl-predefined-symbols"></a>Предопределенные символы ATL

Эти символы определяются в файлах заголовков ATL, но они поддерживают стандартные функции приложения Windows и действия. Эти символы используются главным образом с диалоговыми окнами.

При работе с элементами управления и диалоговых окон в [редактор диалоговых окон](../windows/dialog-editor.md), эти символы будут отображаться в **свойства** окно, связанное с помощью стандартных элементов управления. Например если в диалоговом окне есть **отменить** кнопку, что команда будет связана с символом IDCANCEL в [окно "Свойства"](/visualstudio/ide/reference/properties-window).

|||
|-|-|
|IDABORT|(элемент управления) Диалоговое окно, кнопка прерывания|
|IDC_STATIC|(элемент управления) Статический элемент управления|
|IDCANCEL|(элемент управления) Диалоговое окно, кнопку "Отмена"|
|IDIGNORE|(элемент управления) Диалоговое окно, кнопка Пропустить|
|IDNO|(элемент управления) Диалоговое окно, кнопка "Нет"|
|IDOK|(элемент управления) Диалоговое окно, кнопка "ОК"|
|IDR_ACCELERATOR1|(ресурс) Таблица сочетаний клавиш|
|IDRETRY|(элемент управления) Диалоговое окно, кнопка повтора|
|IDS_PROJNAME|(строка) Имя текущего приложения|
|IDYES|(элемент управления) Диалоговое окно, кнопка «Да»|

## <a name="requirements"></a>Требования

ATL

## <a name="see-also"></a>См. также

[Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)<br/>
[Предопределенные символы MFC](../windows/mfc-predefined-symbols.md)<br/>
[Предопределенные символы Win32](../windows/win32-predefined-symbols.md)<br/>