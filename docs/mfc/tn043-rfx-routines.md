---
title: 'TN043: Процедуры RFX'
ms.date: 06/28/2018
f1_keywords:
- RFX
helpviewer_keywords:
- RFX (record field exchange), architecture
- TN043
- RFX (record field exchange)
ms.assetid: f552d0c1-2c83-4389-b472-42c9940aa713
ms.openlocfilehash: 18820c7d17ddea355490ee32679d5d690ec3533e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294490"
---
# <a name="tn043-rfx-routines"></a>TN043: Процедуры RFX

> [!NOTE]
> Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.

Эта заметка описывается архитектура полями записей (RFX) exchange. Кроме того, описывается, как написать **RFX_** процедуры.

## <a name="overview-of-record-field-exchange"></a>Общие сведения о обмен полями записи

Все функции поле набора записей выполняются с кодом C++. Никаких специальных ресурсов или магических макросов не требуется. Сердцем механизм является виртуальная функция, должен переопределяться в каждом классе производный набор записей. Она всегда представлена в такой форме:

```cpp
void CMySet::DoFieldExchange(CFieldExchange* pFX)
{
    //{{AFX_FIELD_MAP(CMySet)
        <recordset exchange field type call>
        <recordset exchange function call>
    //}}AFX_FIELD_MAP
}
```

Комментарии специального формата AFX позволяют мастеру ClassWizard искать и редактировать код в рамках данной функции. Код, который не совместим с ClassWizard, должен располагаться за пределами этих комментариев специального формата.

В приведенном выше примере \<recordset_exchange_field_type_call > имеет вид:

```cpp
pFX->SetFieldType(CFieldExchange::outputColumn);
```

и \<recordset_exchange_function_call > имеет вид:

```cpp
RFX_Custom(pFX, "Col2", m_Col2);
```

Большинство **RFX_** функции имеют три аргументы, как показано выше, но некоторые (например `RFX_Text` и `RFX_Binary`) имеют дополнительные необязательные аргументы.

Более одного **RFX_** могут быть включены в каждом `DoDataExchange` функции.

См. в разделе «afxdb.h» для получения списка всех записей поле exchange подпрограммы с MFC.

Вызовы поля набора записей — это способ регистрации участки памяти (как правило, члены данных) для хранения данных поля `CMySet` класса.

## <a name="notes"></a>Примечания

Функции поле набора записей, предназначены для работы только с `CRecordset` классы. Они не являются обычно используются любые другие классы MFC.

Начальные значения данных задаются в обычном конструкторе C++, обычно в блоке между комментариями `//{{AFX_FIELD_INIT(CMylSet)` и `//}}AFX_FIELD_INIT`.

Каждый **RFX_** функции должны поддерживать различные операции, в диапазоне от возврата "грязного" состояния поля для архивирования поля в процессе подготовки для редактирования поля.

Каждая функция, которая вызывает `DoFieldExchange` (например `SetFieldNull`, `IsFieldDirty`), свой собственный инициализации вокруг вызова `DoFieldExchange`.

## <a name="how-does-it-work"></a>Как это работает

Необходимо принять во внимание следующие для использования обмен полями записей. Тем не менее зная, как это работает в фоновом поможет вам создать собственную процедуру exchange.

`DoFieldExchange` Функция-член является очень похоже на `Serialize` функция-член — он отвечает за получения или задания данных из внешней формы (в этом вариантов столбцах из результата запроса ODBC) и из нее данные-члены в класс. *PFX* параметр контекста для этого обмена данными и аналогичен *CArchive* параметр `CObject::Serialize`. *PFX* ( `CFieldExchange` объекта) содержит операции индикатора, который аналогичен, но обобщением *CArchive* флаг направления. Функции RFX может потребоваться поддерживают следующие операции:

- `BindParam` — Указывает, где ODBC должен получать данные параметра

- `BindFieldToColumn` — Указать, где ODBC необходимо извлечь/депозита outputColumn данных

- `Fixup` — Задайте `CString/CByteArray` длины, установить бит допустимость значений NULL

- `MarkForAddNew` — Марк "грязной", если значение было изменено с момента вызова AddNew

- `MarkForUpdate` — Марк "грязной", если значение было изменено с момента вызова редактирования

- `Name` — Добавление имен полей для поля, помеченные как "грязные"

- `NameValue` — Добавьте "\<имя столбца > =» для поля, помеченные как" грязные "

- `Value` — Добавьте «» следует разделитель, такие как «,» или ""

- `SetFieldDirty` — Набор статуса битовое "грязных" (т. е. измененной) поле

- `SetFieldNull` — Бита состояние, указывающее, значение null для поля

- `IsFieldDirty` — Возвращаемое значение бит "грязного" состояния

- `IsFieldNull` — Возвращает значение бита в состоянии null

- `IsFieldNullable` — Возвращает значение TRUE, если поле может содержать значения NULL

- `StoreField` — Значение поля архив

- `LoadField` — Перезагрузить архивной значение поля

- `GetFieldInfoValue` — Получить общие сведения о поле

- `GetFieldInfoOrdinal` — Получить общие сведения о поле

## <a name="user-extensions"></a>Пользовательские расширения

Существует несколько способов для расширения механизма RFX по умолчанию. Можно

- Добавить новые типы данных.  Пример:

    ```cpp
    CBookmark
    ```

- Добавьте новые процедуры exchange (RFX_).

    ```cpp
    void AFXAPI RFX_Bigint(CFieldExchange* pFX,
        const char *szName,
        BIGINT& value);
    ```

- У `DoFieldExchange` функция-член условно включают дополнительные вызовы RFX или других допустимых инструкций C++.

    ```cpp
    while (posExtraFields != NULL)
    {
        RFX_Text(pFX,
        m_listName.GetNext(posExtraFields),
        m_listValue.GetNext(posExtraValues));
    }
    ```

> [!NOTE]
> Такой код не может редактировать ClassWizard и должны использоваться только за пределами комментарии специальный формат.

## <a name="writing-a-custom-rfx"></a>Написание пользовательских RFX

Для написания собственной функции Custom RFX, рекомендуется скопировать существующей функции RFX и изменить его с собственными целями. Выбрав правой RFX для копирования можно облегчить вашу работу гораздо. Некоторые функции RFX имеют некоторые уникальные свойства, которые следует учитывать при выборе которого выполняется копирование.

`RFX_Long` и `RFX_Int`: Это самый простой функции RFX. Значение данных отсутствуют любые специальные Интерпретация, а размер данных является фиксированным.

`RFX_Single` и `RFX_Double`: Подобно RFX_Long и RFX_Int выше, эти функции очень простой и можно широко использовать реализации по умолчанию. Они хранятся в dbflt.cpp вместо dbrfx.cpp, тем не менее, чтобы включить загрузку среды выполнения с плавающей запятой библиотеки точки только в том случае, если они явно ссылку.

`RFX_Text` и `RFX_Binary`: Эти две функции предварительного выделения статический буфер для хранения сведений строки или двоичного файла и необходимо зарегистрировать эти буферы ODBC SQLBindCol вместо регистрации & значение. По этой причине эти две функции имеют много кода особым случаем.

`RFX_Date`: ODBC возвращает сведения о дате и времени в свои собственные TIMESTAMP_STRUCT структуры данных. Эта функция динамически выделяет TIMESTAMP_STRUCT как «прокси» для отправки и получения данных даты-времени. Различные операции необходимо перенести данные даты и времени между C++ `CTime` объекта и TIMESTAMP_STRUCT прокси-сервера. Это значительно усложняет эту функцию, но это хороший пример того, как использовать прокси-сервер для передачи данных.

`RFX_LongBinary`: Это только библиотеки классов функции RFX, использует ли привязка к столбцу для получения и отправки данных. Эта функция не обрабатывает операцию BindFieldToColumn и вместо этого во время операции исправления, выделяет память для хранения входящих данных SQL_LONGVARCHAR или SQL_LONGVARBINARY, а затем выполняет SQLGetData вызов для получения значения в выделенной памяти. При подготовке к отправки значений данных обратно в источник данных (например, имя и значение операций), эта функция использует функциональность DATA_AT_EXEC ODBC. См. в разделе [технические 45 Примечание](../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) Дополнительные сведения о работе с SQL_LONGVARBINARY и SQL_LONGVARCHARs.

При написании собственных **RFX_** функции, часто можно использовать `CFieldExchange::Default` для реализации данной операции. Рассмотрим реализацию по умолчанию для операции в вопросе. Если он выполняет операции пришлось бы написать вашей **RFX_** функции, вы можете делегировать `CFieldExchange::Default`. Вы можете увидеть примеры вызова `CFieldExchange::Default` в dbrfx.cpp

Очень важно для вызова `IsFieldType` в начале функции RFX и возврат сразу в том случае, если она возвращает значение FALSE. Этот механизм хранит операции параметр выполнение на *outputColumns*и наоборот (например вызов `BindParam` на *outputColumn*). Кроме того `IsFieldType` автоматически следит за количество *outputColumns* (*m_nFields*) и params (*m_nParams*).

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
