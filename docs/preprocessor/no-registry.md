---
title: no_registry
ms.date: 10/18/2018
f1_keywords:
- no_registry
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
ms.openlocfilehash: bd101f5ca1776518ff4c5092da99134110bbb0b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503029"
---
# <a name="noregistry"></a>no_registry

**no_registry** указывает компилятору не искать в реестре библиотеки типов, импортированные с `#import`.

## <a name="syntax"></a>Синтаксис

```
#import filename no_registry
```

### <a name="parameters"></a>Параметры

*filename*<br/>
Библиотека типов.

## <a name="remarks"></a>Примечания

Если указанная библиотека типов не найден в каталогах включения, компиляция завершается ошибкой, даже если библиотека типов находится в реестре.  **no_registry** распространяет на другие библиотеки типов, неявно импортированные с использованием `auto_search`.

Компилятор никогда не ищет в реестре библиотеки типов, указанные по имени файла и переданные непосредственно в директиву `#import`.

При `auto_search` указано, дополнительный `#import`s будет создана с **no_registry** задание начального `#import` (если начального `#import` директиву **no_registry** , `auto_search`-созданный `#import` также **no_registry**.)

**no_registry** полезно, если вы хотите импортировать кросс-библиотеках типов без риска, что компилятор найдет более старой версии файла в реестре. **no_registry** также полезен, если библиотека типов не зарегистрирована.

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)