---
title: Меню "Файл" в приложении базы данных MFC
ms.date: 11/04/2016
helpviewer_keywords:
- File menu
- database applications [MFC], File menu commands
ms.assetid: 92dafb75-c1b3-4860-80a0-87a83bfc36f2
ms.openlocfilehash: 6c9a195a81423417809b65b5edce32027071ad2e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279124"
---
# <a name="file-menu-in-an-mfc-database-application"></a>Меню "Файл" в приложении базы данных MFC

Если вы создаете приложение базы данных MFC и не использовать сериализацию, как следует интерпретировать открытия, закрытия, сохранить и сохраните как команды в меню "файл" пока не существует правил стиля для этого вопроса, Вот несколько советов:

- Полностью исключите команды откройте меню «файл».

- Интерпретировать команду «Открыть» как «открыть базу данных» и показать пользователю список источников данных, которые распознает приложение.

- Интерпретировать команду «Открыть» как, возможно, «открыть профиль». Сохранить открытым для открытия сериализованный файл, но использовать файл для хранения сериализованного документа, содержащего сведения о «профиль пользователя», например персональные настройки пользователя, включая его или ее идентификатор входа (при необходимости, за исключением пароля) и источника данных он или она наиболее недавно работал в группе.

Мастер приложений MFC поддерживает создание приложения с помощью команды меню файла не связанных с документом. Выберите **представление без поддержки файлов базы данных** параметр **база данных поддерживает** страницы.

Для интерпретации команды меню Файл особым образом, необходимо переопределить один или несколько обработчиков команд, главным образом в вашей `CWinApp`-производного класса. Например, если вы полностью переопределить `OnFileOpen` (который реализует `ID_FILE_OPEN` команду) для обозначения «открыть базу данных:»

- Не вызывайте базовый класс версию `OnFileOpen`, так как нужно полностью заменить реализацией по умолчанию команды.

- Используйте обработчик для отображения диалоговое окно со списком источников данных. Может отображать такие диалоговое окно, вызвав `CDatabase::OpenEx` или `CDatabase::Open` с параметром **NULL**. Откроется диалоговое окно с ODBC, который отображает все доступные источники данных на компьютере пользователя.

- Так как приложения баз данных обычно не сохранять документ целиком, можно удалить сохранения и сохраните в виде реализации, если вы не используете сериализованного документа для хранения сведений профиля. В противном случае можно создать команды «Сохранить», как, например, «зафиксировать транзакцию.» См. в разделе [технические 22 Примечание](../mfc/tn022-standard-commands-implementation.md) Дополнительные сведения о переопределении этих команд.

## <a name="see-also"></a>См. также

[Сериализация. Vs сериализации. Ввод/вывод баз данных](../mfc/serialization-serialization-vs-database-input-output.md)
