---
title: Использование хранимых процедур
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, Visual C++
- stored procedures, about stored procedures
- OLE DB provider templates, stored procedures
- stored procedures, OLE DB
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
ms.openlocfilehash: 2c0c1c71103384439d0b7b94f942e1b5a6d9e651
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536163"
---
# <a name="using-stored-procedures"></a>Использование хранимых процедур

Хранимая процедура представляет собой исполняемый объект, из базы данных. Вызов хранимой процедуры похож на вызов команды SQL. Использование хранимых процедур в источнике данных (вместо выполнения или подготовки инструкции в клиентском приложении) дает определенные преимущества, включая более высокой производительности, снижение сетевых издержек и повышение согласованности и точности.

Хранимая процедура может иметь любое количество (включая ноль) входных или выходных параметров и передавать возвращаемое значение. Вы можете либо жестко значения параметров, как значения определенных данных, или используйте маркер параметра (вопросительный знак "?").

> [!NOTE]
>  SQL Server со средой CLR, хранимые процедуры, созданные с помощью Visual C++, которые должны быть скомпилированы с `/clr:safe` параметр компилятора.

Поставщик OLE DB для SQL Server (SQLOLEDB) поддерживает следующие механизмы, используемые хранимыми процедурами для возвращения данных:

- Каждый **ВЫБЕРИТЕ** инструкция в процедуре формирует результирующий набор.

- Процедура может возвращать данные через выходные параметры.

- Процедура может иметь целочисленный код возврата.

> [!NOTE]
> Нельзя использовать хранимые процедуры с поставщиком OLE DB для Jet, так как этот поставщик не поддерживает хранимые процедуры; в строках запроса, допустимы только константы.

## <a name="see-also"></a>См. также

[Работа с шаблонами объекта-получателя OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)