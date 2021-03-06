---
title: Команды меню (C++)
ms.date: 02/15/2019
helpviewer_keywords:
- menu items, properties
- keyboard shortcuts [C++], menu association
- commands [C++], associating menu commands with accelerator keys
- menu commands [C++], associating with keyboard shortcuts
- status bars [C++], associating menu items
- menus [C++], status bar text
- access keys [C++], checking
- menus [C++], shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics [C++], adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics [C++], uniqueness checking
- Check Mnemonics command
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
ms.openlocfilehash: 9f91973fdf2d5a45c631f24d3eed41482a91a834
ms.sourcegitcommit: 24592ba0a38c7c996ffd3d55fe1024231a59ccc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2019
ms.locfileid: "56336609"
---
# <a name="menu-commands-c"></a>Команды меню (C++)

Приведенные ниже сведения организованные в соответствии со **меню** свойства, которые отображаются в [окно "Свойства"](/visualstudio/ide/reference/properties-window) при выборе команды меню. Они перечислены в алфавитном порядке несмотря на то что **свойства** окно также позволяет просматривать эти свойства по категориям.

|Свойство.|Описание:|
|--------------|-----------------|
|**Break**|Допустимо одно из следующих значений.<br /><br />- **Нет** (по умолчанию): Без разрыва.<br />- **Столбец**: Для статических меню это значение помещает команду меню в новой строке. В контекстных меню при этом значении команда меню помещается в новый столбец без разделительной линии между столбцами. Установка этого свойства влияет на внешний вид меню только во время выполнения. В редакторе внешний вид меню не меняется.<br />- **Панель**: Совпадение с кодом **столбец** за исключением контекстных меню, это значение новый столбец отделяется от старого вертикальной линией. Задание этого свойства влияет на внешний вид меню только во время выполнения, не в **меню** редактора.|
|**Подпись**|Текст, представляющий команду меню (имя меню). Чтобы указать одну из букв названия команды меню как входящую в сочетание клавиш, поместите перед ней знак амперсанда (&).|
|**Помечено**|Если **True**, команда меню изначально установлен. Тип: **Bool**. По умолчанию: **False**.|
|**Включено**|Если задано значение **False**, пункт меню отключен.|
|**Grayed (Серым цветом)**|Если **True**, команда меню изначально выделена серым цветом и неактивной. Тип: **Bool**. По умолчанию: **False**.|
|**Справка**|Выравнивает пункт меню по правому краю. Например, команда меню **Справка** всегда находится справа во всех приложениях Windows. Если задано это свойство пункта меню, данный пункт будет отображаться прижатым к правому краю и в самом конце меню. Применяется к элементам верхнего уровня. По умолчанию: **False**.|
|**ID**|Этот символ определяется в файле заголовка. Тип: **Символ**, **целое число**, или **строка в кавычках**. Можно использовать любой символ, который обычно доступен в любом редакторе, даже если [окно свойств](/visualstudio/ide/reference/properties-window) не содержит раскрывающийся список для выбора этого символа.|
|**Контекстное меню**|Если **True**, команда меню является всплывающим меню. Тип: **Bool**. По умолчанию: **Значение true,** для меню верхнего уровня в меню панели; в противном случае **False**.|
|**Запрашивать**|Содержит текст, отображаемый в строке состояния, при выделении этой команды меню. Текст помещается в таблицу строк с тем же идентификатором, что и команда меню. Это свойство доступно для любого типа проекта, но во время выполнения проявляются особенности, зависящие от MFC.|
|**Right to Left Justify (Выравнивание справа налево)**|Выравнивание команды меню по правому краю в строке меню во время выполнения. Тип: **Bool**. По умолчанию: **False**.|
|**Right to Left Order (Справа налево)**|Отображение команд меню справа налево в тех случаях, когда интерфейс локализован для языка с направлением чтения справа налево, например, иврита или арабского языка.|
|**Separator**|Если **True**, команда меню является разделителем. Тип: **Bool**. По умолчанию: **False**.|

## <a name="associate-menu-commands"></a>Сопоставления команд меню

В некоторых ситуациях может потребоваться, чтобы программную команду можно было вызывать с помощью команды меню и сочетания клавиш. Идентичные команд с помощью **меню** редактор, чтобы назначить один и тот же идентификатор ресурса команде меню и записи в таблице сочетаний клавиш приложения. Затем необходимо изменить [Заголовок](../windows/menu-command-properties.md) команды меню, чтобы в нем отображалось название сочетания клавиш.

### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>Сопоставление команды меню с сочетанием клавиш

1. В редакторе **меню** выберите нужную команду меню.

1. В [окне свойств](/visualstudio/ide/reference/properties-window)добавьте название сочетания клавиш в свойство **Заголовок** .

   - Сразу после заголовка меню введите escape-последовательность для табуляции (\t), чтобы все сочетания клавиш в меню были выровнены по левому краю.

   - Введите имя клавиши-модификатора (**Ctrl**, **Alt**, или **Shift**) следуют знак плюс (**+**) и имя, букву, или символ дополнительной клавиши.

   Например, чтобы назначить **Ctrl**+**O** для **откройте** команды **файл** меню изменить команды меню  **Заголовок** , чтобы он выглядел следующим образом:

   ```
   &Open...\tCtrl+O
   ```

   Команды меню в **меню** редактор будет обновлена с учетом нового названия, при вводе.

1. [Создайте запись в таблице сочетаний клавиш](../windows/adding-an-entry-to-an-accelerator-table.md) с помощью редактора **сочетаний клавиш** и назначьте ему тот же идентификатор ресурса, что и команде меню. Рекомендуется выбирать сочетания, которые легче запомнить.

### <a name="to-associate-a-menu-command-with-a-status-bar-text-string-in-mfc-applications"></a>Должен быть сопоставлен текстовую строку в приложениях MFC в строке состояния команды меню

Приложение MFC может отображать описательный текст для каждой из команд меню, которые может выбрать пользователь. Отображать описательный текст, необходимо назначить строку текста для каждой команды меню, используя **Prompt** свойство в **свойства** окна. Если в [таблице строк](../windows/string-editor.md) имеется строка, идентификатор которой совпадает с идентификатором команды, приложение MFC автоматически отобразит этот строковый ресурс в строке состояния выполняющегося приложения в момент, когда пользователь наведет указатель мыши на пункт меню.

1. В редакторе **меню** выберите команду меню.

1. В [окне "Свойства"](/visualstudio/ide/reference/properties-window)в поле **Prompt** (Подсказка) введите нужный текст для строки состояния.

> [!NOTE]
> Этот набор шагов требуется MFC.

### <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>Назначение клавиши доступа (сочетания клавиш) команде меню

В проекте C++ можно назначить ключ доступа (назначенную, который позволяет пользователю выбрать в меню с помощью клавиатуры) меню и команд меню.

Введите знак амперсанда (`&`) перед буквой в имени меню или имя команды, чтобы указать эту букву как клавиша доступа. Например «& файл» наборы **Alt**+**F** сочетания клавиш для **файл** меню в приложениях, написанных для Microsoft Windows.

   Буква, с которой связана клавиша доступа, обычно наглядно обозначена в элементе меню. Как правило, буква, следующая за символом амперсанда, отображается как подчеркнутая (везде в рамках одной ОС).

   > [!NOTE]
   > Чтобы убедиться в том, что клавиши доступа не повторяются в рамках одного меню, щелкните меню правой кнопкой мыши и выберите в контекстном меню команду **Проверить назначенные клавиши** .

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор меню](../windows/menu-editor.md)<br/>
[Строки (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>