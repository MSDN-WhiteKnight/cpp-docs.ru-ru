---
title: Стандартные команды
ms.date: 11/04/2016
helpviewer_keywords:
- File menu
- identifiers [MFC], command IDs
- command IDs, standard commands
- OLE commands
- commands [MFC], standard
- standard command IDs
- Window menu commands
- standard commands
- View menu commands
- Edit menu standard commands
- Help [MFC], menus
- programmer-defined IDs [MFC]
ms.assetid: 88cf3ab4-79b3-4ac6-9365-8ac561036fbf
ms.openlocfilehash: 987023322e38584d10901c1ab1fe20ac46926bd2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272091"
---
# <a name="standard-commands"></a>Стандартные команды

Платформа framework определяет много сообщений стандартную команду. Идентификаторы для этих команд обычно имеют вид:

**ID_** *источника*_*элемента*

где *источника* обычно является имя меню и *элемент* представляет собой элемент меню. Например идентификатор для новой команды в меню "файл" — ID_FILE_NEW. Стандартные идентификаторы команд отображаются полужирным шрифтом в документации. Определяемые программистом идентификаторы отображаются шрифтом, который отличается от окружающего текста.

Ниже приведен список некоторых из наиболее важных команд, поддерживаемых:

*Файл команд меню*<br/>
Новые открыть, закрыть, сохранить, сохранить как, параметры страницы, параметры печати, печать, предварительный просмотр печати, выхода и недавно использовавшихся файлов.

*Изменение команды меню*<br/>
Снимите флажок, снимите все, копирования, вырезания, поиска, вставки, повторите, Replace, все содержимое, отката или повтора.

*Команды меню "Вид"*<br/>
Панель инструментов и строки состояния.

*Команды меню "Окно"*<br/>
Новые, упорядочить, вызывать каскадные действия, плитку по горизонтали, плитку по вертикали и разделение.

*Команды меню "Справка"*<br/>
Индекс, с помощью справки и примерно.

*Команды OLE (меню "Правка")*<br/>
Вставить новый объект, изменить ссылки, связать, Специальная вставка и *typename* объекта (команд).

Платформа предоставляет различные уровни поддержки для этих команд. Некоторые команды поддерживаются только в качестве идентификаторов определенных команд, хотя две другие поддерживаются с помощью тщательного реализаций. Например платформа реализует команду «Открыть» в меню "файл", создавая объект документа, отображение открытое окно и открытия и чтения файла. Напротив вы должны реализовать команды в меню "Правка", так как команды, например ID_EDIT_COPY зависит от характера данных при копировании.

Дополнительные сведения о поддерживаемых командах и уровень реализации, см. в разделе [технические 22 Примечание](../mfc/tn022-standard-commands-implementation.md). Стандартные команды определены в файле AFXRES. З.

## <a name="see-also"></a>См. также

[Объекты пользовательского интерфейса и идентификаторы команд](../mfc/user-interface-objects-and-command-ids.md)
