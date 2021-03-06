---
title: Транзакция. Влияние транзакций на обновления (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
ms.openlocfilehash: 68ff6970243b36b56ab206b16bb2c3608cef71e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437860"
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>Транзакция. Влияние транзакций на обновления (ODBC)

Обновляет [источника данных](../../data/odbc/data-source-odbc.md) осуществляется в процессе транзакций при помощи буфера редактирования (тот же метод использовать вне транзакции). Элементами данных полей в наборе записей служат в качестве буфера, содержащего текущую запись набора записей резервную копию которой временно во время редактирования `AddNew` или `Edit`. Во время `Delete` операции, текущую запись без резервного копирования в рамках транзакции. Дополнительные сведения о буфере редактирования и каким образом обновляет хранилище текущей записи, см. в разделе [набор записей: принцип наборы записей обновления записей (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

> [!NOTE]
>  Если вы реализовали выборка строк, нельзя вызывать `AddNew`, `Edit`, или `Delete`. Вместо этого необходимо написать свои собственные функции для выполнения обновления в источнике данных. Дополнительные сведения о массовой выборке строк см. в разделе [набор записей: получение записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Во время выполнения транзакций `AddNew`, `Edit`, и `Delete` может быть зафиксирована или выполнен откат операции. Последствия `CommitTrans` и `Rollback` может привести к текущей записи не будет сохранена в буфере. Чтобы убедиться, что текущей записи восстановления, важно понять, каким образом `CommitTrans` и `Rollback` функции-члены `CDatabase` работают с функциями обновления класса `CRecordset`.

##  <a name="_core_how_committrans_affects_updates"></a> Влияние CommitTrans обновление

В следующей таблице описаны последствия `CommitTrans` на транзакциях.

### <a name="how-committrans-affects-updates"></a>Влияние CommitTrans обновление

|Операция|Состояние источника данных|
|---------------|---------------------------|
|`AddNew` и `Update`, а затем `CommitTrans`|Новые записи добавляются к источнику данных.|
|`AddNew` (без `Update`), а затем `CommitTrans`|Новая запись будет потеряно. Запись не добавлена к источнику данных.|
|`Edit` и `Update`, а затем `CommitTrans`|Изменения, зафиксированные для источника данных.|
|`Edit` (без `Update`), а затем `CommitTrans`|Вносить изменения в запись, будут потеряны. Запись остается без изменений в источнике данных.|
|`Delete` Затем `CommitTrans`|Записи, удаленные из источника данных.|

##  <a name="_core_how_rollback_affects_updates"></a> Влияние отката транзакции

В следующей таблице описаны последствия `Rollback` на транзакциях.

### <a name="how-rollback-affects-transactions"></a>Влияние отката транзакции

|Операция|Состояние текущей записи|Кроме того, необходимо|Состояние источника данных|
|---------------|------------------------------|-------------------|---------------------------|
|`AddNew` и `Update`, затем `Rollback`|Чтобы освободить место для новой записи временно сохраняется содержимое текущей записи. Новая запись вводится в буфере. После `Update` вызывается текущего запись восстанавливается в буфере.||Добавление к источнику данных, произведенные `Update` отменяется.|
|`AddNew` (без `Update`), затем `Rollback`|Чтобы освободить место для новой записи временно сохраняется содержимое текущей записи. Изменить буфер содержит новую запись.|Вызовите `AddNew` еще раз, чтобы восстановить пустой новой записи в буфере. Или позвоните `Move`(0), чтобы восстановить старые значения в буфере.|Так как `Update` не был вызван, не вносит изменения, сделанные в источнике данных.|
|`Edit` и `Update`, затем `Rollback`|Временно сохраняется неизмененная версия текущей записи. Изменений в содержимое в буфере. После `Update` вызове неизмененная версия записи по-прежнему временно сохраняется.|*Динамический набор*: прокрутка текущей записи восстановление неизмененной версии записи в буфере.<br /><br /> *Моментальный снимок*: вызовите `Requery` для обновления набора записей из источника данных.|Изменения в источник данных, произведенные `Update` отменяются.|
|`Edit` (без `Update`), затем `Rollback`|Временно сохраняется неизмененная версия текущей записи. Изменений в содержимое в буфере.|Вызовите `Edit` снова для восстановления неизмененной версии записи в буфере.|Так как `Update` не был вызван, не вносит изменения, сделанные в источнике данных.|
|`Delete` Затем `Rollback`|Удаляется содержимое текущей записи.|Вызовите `Requery` для восстановления текущей записи из источника данных.|Удаление данных из источника данных в обратном порядке.|

## <a name="see-also"></a>См. также

[Транзакция (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[Транзакция (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[Транзакция. Выполнение транзакции в наборе записей (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)<br/>
[Класс CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)