---
title: Макроподстановка
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
ms.openlocfilehash: 8daaa55418839fa969cf3a31efa092fcf21487e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616090"
---
# <a name="macro-substitution"></a>Макроподстановка

Когда *имя макроса* вызывается, каждое вхождение *string1* в своем определении строка заменяется *string2*.

## <a name="syntax"></a>Синтаксис

```
$(macroname:string1=string2)
```

## <a name="remarks"></a>Примечания

Макроподстановка чувствительно к регистру и буквально; *string1* и *string2* нельзя вызывать макросы. Подстановка не изменяет исходное определение. Можно заменить текст в любой предопределенный макрос, за исключением [ $$@ ](../build/filename-macros.md).

Пробелы или вкладки перед двоеточием; любой после двоеточия, интерпретируется как литерал. Если *string2* имеет значение null, все вхождения *string1* удаляются из строки определения макроса.

## <a name="see-also"></a>См. также

[Использование макроса NMAKE](../build/using-an-nmake-macro.md)