---
title: Создание простого объекта-получателя
ms.date: 11/06/2018
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
ms.openlocfilehash: 4346bca99d3744657072a4940776934e3c03e9de
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326645"
---
# <a name="creating-a-simple-consumer"></a>Создание простого объекта-получателя

Используйте **мастер проектов ATL** и **Мастер потребителя ATL OLE DB** для создания объекта-получателя шаблонов OLE DB.

## <a name="to-create-a-console-application-for-an-ole-db-consumer"></a>Создание консольного приложения для объекта-получателя OLE DB

1. В меню **Файл** последовательно выберите пункты **Создать**и **Проект**.

   Откроется диалоговое окно **Новый проект** .

1. В **типы проектов** панели щелкните **установленные** > **Visual C++** > **Windows Desktop** папке а затем нажмите кнопку **мастер создания классических приложений Windows** значок в **шаблоны** области. В **имя** введите имя проекта, например, *MyCons*.

1. Нажмите кнопку **ОК**.

   **Проект приложения Windows** откроется мастер.

1. На **параметры приложения** выберите **консольное приложение**, а затем выберите **добавить общие файлы заголовков для ATL**.

1. Нажмите кнопку **ОК** закрыть мастер и создать проект.

Затем используйте **Мастер потребителя ATL OLE DB** Добавление объекта потребителя OLE DB.

## <a name="to-create-a-consumer-with-the-atl-ole-db-consumer-wizard"></a>Чтобы создать объект-получатель с помощью мастера потребителя ATL OLE DB

1. В **обозревателе решений**, щелкните правой кнопкой мыши `MyCons` проекта.

1. В контекстном меню, щелкните **добавить**, а затем нажмите кнопку **новый элемент**.

   Откроется диалоговое окно **Добавление нового элемента**.

1. В **категории** панели щелкните **установленные** > **Visual C++** > **ATL**, нажмите кнопку **Потребителя OLEDB библиотеки ATL** значок в **шаблоны** области, а затем щелкните **добавить**.

   **Мастер потребителя ATL OLEDB** отображается.

1. Нажмите кнопку **источника данных** кнопки.

   **Свойства канала передачи данных** откроется диалоговое окно.

1. В **свойства канала передачи данных** диалоговом окне сделайте следующее:

   1. На **поставщика** вкладке укажите поставщика OLE DB.

   1. На **подключения** вкладке, укажите необходимые сведения, такие как имя сервера, имя пользователя и пароль для источника данных и базы данных на сервере.

      > [!NOTE]
      > Существует проблема безопасности с **Разрешить сохранение пароля** особенностью **свойства канала передачи данных** диалоговое окно. В **введите данные для входа сервер**, существует два переключателя: **встроенные средства безопасности Windows NT используйте** и **использовать указанные имя пользователя и пароль**.

      > [!NOTE]
      > При выборе **использовать указанные имя пользователя и пароль**, имеется возможность сохранения пароля (с помощью **Разрешить сохранение пароля** флажок), однако этот параметр не является безопасным. Рекомендуется выбрать **встроенные средства безопасности Windows NT используйте**; этот параметр использует Windows NT, чтобы подтвердить свою личность.

      > [!NOTE]
      > Если нельзя использовать Windows встроенная система безопасности NT, следует использовать приложения среднего уровня запрашивает у пользователя пароль или сохранить пароль в расположении с механизмами безопасности для обеспечения его безопасности (а не в исходном коде).

   1. После выбора поставщика и другие параметры, нажмите кнопку **проверить подключение** для проверки значений, заданных на предыдущих страницах диалогового окна. Если **результатов** поле отчеты `Test connection succeeded`, нажмите кнопку **ОК** для создания такой связи данных.

   **Выбор объектов базы данных** откроется диалоговое окно.

1. Выберите таблицу, представление или хранимую процедуру с помощью элемента управления дерева. В этом примере выберите `Products` таблицу `Northwind` базы данных.

1. Нажмите кнопку **ОК**. Вы вернетесь на **Мастер потребителя ATL OLE DB**.

1. Имена для завершения работы мастера `Class` и **h-файл** на основе имени таблицы, представления или хранимой процедуры, которые вы выбрали. Эти имена можно изменить, если требуется.

1. Очистить **атрибуты** флажок, чтобы мастер создавал код потребителя, используя [классы шаблонов OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md) вместо значения по умолчанию [атрибуты потребителя OLE DB](../../windows/ole-db-consumer-attributes.md).

1. В разделе **тип**выберите **команда**.

   Мастер создает [CCommand](../../data/oledb/ccommand-class.md)-основе потребителей, если выбрать **команда** или [CTable](../../data/oledb/ctable-class.md)-основе потребителей, если выбрать **таблицы**. Именем класса таблицы или команды после выбора объекта, но можно изменить имя.

1. В разделе **поддержки**, оставьте **изменение**, **вставить**, и **удалить** флажки.

   Выберите **изменение**, **вставить**, и **удалить** флажки для поддержки изменения, вставки и удаления записей в наборе строк. Дополнительные сведения о записи данных в данных хранения, см. в разделе [обновление наборов строк](../../data/oledb/updating-rowsets.md).

1. Нажмите кнопку **Готово** для создания потребителя.

Мастер создает класс команд и класс записей пользователя, как показано в [классы внедренных](../../data/oledb/consumer-wizard-generated-classes.md). Класс команд будет иметь имя, введенное в `Class` поле в мастере (в этом случае `CProducts`), и класс записей пользователя будет иметь имя в формате "*ClassName*метод доступа» (в этом случае `CProductsAccessor`).

> [!NOTE]
> Мастер помещает следующую строку в `Products.h`:

```cpp
#error Security Issue: The connection string may contain a password
```

> [!NOTE]
> Эта строка предотвращает компиляцию и напоминает о необходимости проверить строку подключения для жестко пароли. После проверки строки подключения, можно удалить эту строку кода.

## <a name="see-also"></a>См. также

[Создание объекта-получателя OLE DB с помощью мастера](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
