---
title: Операторы предварительной обработки файлов makefile
ms.date: 06/14/2018
helpviewer_keywords:
- operators [C++], makefile preprocessing
- EXIST operator
- preprocessing NMAKE makefile operators
- NMAKE program, operators
- DEFINED operator
- makefiles, preprocessing operators
ms.assetid: a46e4d39-afdb-43c1-ac3b-025d33e6ebdb
ms.openlocfilehash: a78abd3c71d6fec2b77dbb2c2e7b40f8f703626b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650844"
---
# <a name="makefile-preprocessing-operators"></a>Операторы предварительной обработки файлов makefile

В выражениях предварительной обработки файлов makefile могут использоваться операторы, выполняющие действия с константными значениями, кодами завершения команд, строками, макросами и путями файловой системы. Для оценки выражения препроцессор сначала разворачивает макросы и выполняет команды, а затем выполняет операции. Операции оцениваются в порядке явного объединения в скобках, а затем в порядке приоритета операторов. Результатом является константное значение.

**ОПРЕДЕЛЕННЫЕ** оператор — это логический оператор, применяемый к имени макроса. Выражение **DEFINED (**_имя макроса_**)** имеет значение true если *имя макроса* определено, даже если он не имеет присвоенного значения. **ОПРЕДЕЛЕННЫЕ** в сочетании с **! Если** или **! ELSE IF** эквивалентен **! IFDEF** или **! ELSE IFDEF**. Тем не менее, в отличие от этих директив **ОПРЕДЕЛЕННЫЕ** можно использовать в сложных выражений.

**EXIST** оператор — это логический оператор, применяемый к пути файловой системы. **EXIST (**_путь_**)** имеет значение true если *путь* существует. В результате **EXIST** может использоваться в двоичные выражения. Если *путь* содержит пробелы, заключите его в двойные кавычки.

Для сравнения двух строк используйте равенство (**==**) или оператор неравенства (**! =**) оператор. Строки заключаются в двойные кавычки.

Целочисленные константы могут использовать унарные операторы для числового отрицания (**-**), одно дополнение (**~**) и логического отрицания (**!**).

В выражениях могут использоваться следующие операторы. Операторы с одинаковым приоритетом объединяются в группы, которые перечисляются в порядке убывания приоритета. Унарные операторы связываются с операндом справа. Бинарные операторы одинакового приоритета связывают операнды слева направо.

|Оператор|Описание|
|--------------|-----------------|
|**ОПРЕДЕЛЕННЫЕ (** *имя макроса* **)**|Возвращает логическое значение для текущего состояния определения *имя макроса*.|
|**EXIST (** *путь* **)**|Возвращает логическое значение для существования файла в *путь*.|
|||
|**\!**|Унарное логическое НЕ.|
|**~**|Унарное дополнение до единицы.|
|**-**|Унарное отрицание.|
|||
|**&#42;**|Умножение.|
|**/**|Деление.|
|**%**|Модуль (остаток от деления).|
|||
|**+**|Сложение.|
|**-**|Вычитание.|
|||
|**\<\<**|Побитовое смещение влево.|
|**>>**|Побитовое смещение вправо.|
|||
|**\<=**|Меньше или равно.|
|**>=**|Больше или равно.|
|**\<**|Меньше.|
|**>**|Больше.|
|||
|**==**|Равенство.|
|**\!=**|Неравенство.|
|||
|**&**|Побитовое И.|
|**^**|Побитовое исключающее ИЛИ.|
|**&#124;**|Побитовое ИЛИ.|
|||
|**&&**|Логическое И.|
|||
|**&#124;&#124;**|Логическое ИЛИ.|

> [!NOTE]
> Оператор побитового исключающего или (**^**) совпадает со значением escape-символом и должен экранироваться (как **^^**) при использовании в выражении.

## <a name="see-also"></a>См. также

- [Выражения в предобработке файлов Makefile](../build/expressions-in-makefile-preprocessing.md)