---
title: Набор записей (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, snapshots
- recordsets, creating
- dynamic recordsets
- forward-only recordsets
- recordsets, dynasets
- ODBC recordsets, CRecordset objects
- ODBC recordsets
- recordsets, about recordsets
- snapshots, ODBC recordsets
- dynasets
ms.assetid: 333337c5-575e-4d26-b5f6-47166ad7874d
ms.openlocfilehash: d16087722752b7bbdabd37410908c7ea2ae18ceb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435260"
---
# <a name="recordset-odbc"></a>Набор записей (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

Объект [CRecordset](../../mfc/reference/crecordset-class.md) представляет набор записей, выбранных из источника данных. Записи можно из:

- Таблица.

- Запрос.

- Хранимая процедура, которая обращается к одной или нескольких таблиц.

Пример набора записей, на основе таблицы — «all customers», которая обращается к таблице клиентов. Пример запроса — «все счета конкретного лица.» Пример набора записей, в зависимости от хранимой процедуры (иногда называется предопределенного запроса) — «all неоплаченные счета» которого вызывает хранимую процедуру в базе данных серверной части. Набор записей можно объединить два или несколько таблиц из одного источника данных, но не с таблицами из разных источников данных.

> [!NOTE]
>  Сведения о создании производных классов записей с помощью мастеров, см. в разделе [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md) и [Поддержка баз данных, мастер приложений MFC](../../mfc/reference/database-support-mfc-application-wizard.md).

> [!NOTE]
>  Некоторые драйверы ODBC поддерживают представления базы данных. В этом смысле представление — это запрос, первоначально созданных с помощью SQL `CREATE VIEW` инструкции. Мастера в настоящее время не поддерживает представления, но можно писать код для поддержки самостоятельно.

##  <a name="_core_recordset_capabilities"></a> Возможности наборов записей

Все объекты наборов записей обладают следующими возможностями:

- Если источник данных не только для чтения, можно указать, что набор записей быть [обновляемых](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), [добавление](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), или только для чтения. Если набор записей является обновляемым, можно выбрать либо пессимистическая или оптимистическая [блокировки](../../data/odbc/recordset-locking-records-odbc.md) методы, предоставленные драйвер предоставляет соответствующий режим поддерживается. Если источник данных доступен только для чтения, набор записей будет доступен только для чтения.

- Вы можете вызов функций-членов для [прокрутки](../../data/odbc/recordset-scrolling-odbc.md) через выбранные записи.

- Вы можете [фильтра](../../data/odbc/recordset-filtering-records-odbc.md) записи выбранных записей.

- Вы можете [сортировки](../../data/odbc/recordset-sorting-records-odbc.md) записи в возрастающем или убывающем порядке, на основе одного или нескольких столбцов.

- Вы можете [параметризовать](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) выбранные во время выполнения набор записей.

##  <a name="_core_snapshots_and_dynasets"></a> Моментальные снимки и динамических подмножеств данных

Существует два основных типа наборов записей: [моментальные снимки](../../data/odbc/snapshot.md) и [динамических подмножеств данных](../../data/odbc/dynaset.md). Оба поддерживаются классом `CRecordset`. Каждый использует общие характеристики всех наборов записей, но каждый также расширяет функциональные возможности специализированные своему. Моментальные снимки предоставляют статическое представление данных и полезны для отчетов и других ситуациях, в которых требуется получить представление данных на определенный момент времени. Динамических подмножеств данных полезны в тех случаях, когда нужно получать обновления, сделанные другими пользователями должен отображаться в наборе записей без выполнения запроса или обновления набора записей. Моментальные снимки и динамических подмножеств данных может быть обновляемым или только для чтения. Отражают записи, добавленные или удаленные другими пользователями, вызовите метод [метод CRecordset::Requery](../../mfc/reference/crecordset-class.md#requery).

`CRecordset` также поддерживает два типа наборов записей: динамические наборы записей и последовательным. Динамические наборы записей похожи на динамических подмножеств данных; Тем не менее динамические наборы записей отражают все записи добавлены или удалены без вызова `CRecordset::Requery`. По этой причине динамические наборы записей, обычно предъявляют серьезные, с учетом времени обработки на СУБД и многие драйверы ODBC не поддерживают их. Напротив с последовательным предоставляют наиболее эффективный метод доступа к данным для наборов записей, не требуют обновления или обратной прокрутки. Например можно использовать набор записей только вперед для переноса данных из одного источника данных в другую, где требуется только для перемещения по данным в прямом направлении. Чтобы использовать набор записей только вперед, необходимо выполнить оба из следующих:

- Передайте параметр `CRecordset::forwardOnly` как *nOpenType* параметр [откройте](../../mfc/reference/crecordset-class.md#open) функция-член.

- Укажите `CRecordset::readOnly` в *dwOptions* параметр `Open`.

    > [!NOTE]
    >  Сведения о требованиях к драйверам ODBC для поддержки динамических подмножеств данных, см. в разделе [ODBC](../../data/odbc/odbc-basics.md). Список драйверов ODBC, поставляемых в эту версию Visual C++, а также сведения о приобретении дополнительных драйверов см. в разделе [список драйверов ODBC](../../data/odbc/odbc-driver-list.md).

##  <a name="_core_your_recordsets"></a> Работа с наборами записей

Для каждого отдельных таблиц, представление или хранимую процедуру, необходимо получить доступ, обычно определяется класс, производный от `CRecordset`. (Исключением является объединение базы данных, в котором один набор записей представляет столбцы из нескольких таблиц.) При наследовании класса набора записей, включить механизм полями записей (RFX) exchange или механизма обмена (Bulk RFX) массового полями записей, которые похожи на механизм обмена (окон DDX) данных диалогового окна. RFX и Bulk RFX позволяют упростить передачу данных из источника данных в набор записей. Кроме того RFX передает данные из набора записей в источнике данных. Дополнительные сведения см. в разделе [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md) и [набор записей: получение записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Объект набора записей предоставляет доступ для всех выбранных записях. Прокрутите записи с помощью `CRecordset` функций-членов, таких как `MoveNext` и `MovePrev`. В то же время представляет объект набора записей только один из выбранных записей текущей записи. Можно проверить поля текущей записи, объявив переменные-члены класса, которые соответствуют столбцам таблицы или записи, являющиеся результатом запроса к базе данных набора записей. Сведения о членах данных набора записей, см. в разделе [набор записей: архитектура (ODBC)](../../data/odbc/recordset-architecture-odbc.md).

В следующих разделах описаны сведения об использовании объекта набора записей. Разделы, перечислены в функциональные категории и порядке для разрешения последовательное чтение.

### <a name="topics-about-the-mechanics-of-opening-reading-and-closing-recordsets"></a>Разделы, посвященные механизм открытие, чтение и закрытие наборов записей

- [Набор записей. Архитектура (ODBC)](../../data/odbc/recordset-architecture-odbc.md)

- [Набор записей. Объявление класса таблицы (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)

- [Набор записей. Создание и закрытие наборов записей (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)

- [Набор записей. Прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)

- [Набор записей. Закладки и абсолютное позиционирование (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)

- [Набор записей. Фильтрация записей (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)

- [Набор записей. Сортировка записей (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)

- [Набор записей. Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

### <a name="topics-about-the-mechanics-of-modifying-recordsets"></a>Разделы, посвященные изменение наборов записей

- [Набор записей. Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)

- [Набор записей. Блокировка (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)

- [Набор записей. Выполнение обновления наборов записей (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)

### <a name="topics-about-somewhat-more-advanced-techniques"></a>Разделы, посвященные немного более сложные приемы

- [Набор записей. Объединение (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)

- [Набор записей. Объявление класса для предопределенного запроса (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)

- [Набор записей. Динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)

- [Набор записей. Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

- [Набор записей. Работа с большими элементами данных (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)

- [Набор записей. Определение сумм и других статистических результатов (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)

### <a name="topics-about-how-recordsets-work"></a>Разделы, посвященные работе с наборами записей

- [Набор записей. Порядок выборки записей в наборе (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)

- [Набор записей. Порядок обновления записей в наборе (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)

## <a name="see-also"></a>См. также

[Интерфейс ODBC](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Потребление MFC ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Транзакция (ODBC)](../../data/odbc/transaction-odbc.md)