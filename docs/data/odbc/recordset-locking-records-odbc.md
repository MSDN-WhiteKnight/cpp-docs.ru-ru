---
title: 'Набор записей: блокировка (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- locks [C++], recordsets
- optimistic locking
- pessimistic locking in ODBC
- recordsets [C++], locking records
- optimistic locking, ODBC
- ODBC recordsets [C++], locking records
- data [C++], locking
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
ms.openlocfilehash: 08d7ca1db474a5735ccaabaa7d7d87b359730bb5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438705"
---
# <a name="recordset-locking-records-odbc"></a>Набор записей: блокировка (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

Содержание раздела:

- [Типы блокировки записи](#_core_record.2d.locking_modes).

- [Как блокировать записи в наборе записей во время обновления](#_core_locking_records_in_your_recordset).

При использовании набора записей для обновления записи в источнике данных, приложение может выполнить блокировку записи, ни один другой пользователь может обновить запись, в то же время. Состояние записи обновлены двумя пользователями в то же время остается неопределенным, если система может гарантировать, что два пользователя не удается обновить запись одновременно.

> [!NOTE]
>  Этот раздел относится к объектам, производным от `CRecordset` в какой строке массовой выборка не был реализован. Если вы реализовали выборка строк, некоторые данные не применяется. Например, нельзя вызывать `Edit` и `Update` функций-членов. Дополнительные сведения о массовой выборке строк см. в разделе [набор записей: получение записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="_core_record.2d.locking_modes"></a> Режимы блокировки записей

Классы баз данных предоставляют два [режимы блокировки записей](../../mfc/reference/crecordset-class.md#setlockingmode):

- Оптимистическая блокировка (по умолчанию)

- Пессимистическая блокировка

Обновление записи происходит в три этапа:

1. Операция начинается с вызова [изменить](../../mfc/reference/crecordset-class.md#edit) функция-член.

1. Изменить соответствующие поля текущей записи.

1. Операция завершена и обычно выполняется обновление — путем вызова [обновление](../../mfc/reference/crecordset-class.md#update) функция-член.

Оптимистическая блокировка блокирует запись в источнике данных только во время `Update` вызова. Если вы используете оптимистической блокировки в многопользовательской среде, то приложение должно обрабатывать `Update` условие сбоя. Запись пессимистической блокировки блокируется, как только вы вызываете `Edit` и не освобождает его только после вызова `Update` (ошибки обозначаются с помощью `CDBException` механизм, не через значение FALSE, возвращаемый `Update`). Пессимистическая блокировка имеет потенциальные проблемы с производительностью для других пользователей, так как одновременный доступ к той же записи придется ждать завершения приложения `Update` процесса.

##  <a name="_core_locking_records_in_your_recordset"></a> Блокировка записей в наборе записей

Если вы хотите изменить объект набора записей [режим блокировки](#_core_record.2d.locking_modes) по умолчанию, необходимо изменить режим, перед вызовом метода `Edit`.

#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>Чтобы изменить текущий режим блокировки для набора записей

1. Вызовите [SetLockingMode](../../mfc/reference/crecordset-class.md#setlockingmode) функция-член, указав `CRecordset::pessimistic` или `CRecordset::optimistic`.

Новый режим блокировки остается в силе до внесения изменений или закрыто набор записей.

> [!NOTE]
>  Относительно небольшое количество драйверов ODBC в настоящее время поддерживает пессимистической блокировки.

## <a name="see-also"></a>См. также

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Набор записей. Объединение (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)<br/>
[Набор записей. Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)