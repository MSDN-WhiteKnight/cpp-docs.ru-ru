---
title: Структура space_info
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::space_info
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
ms.openlocfilehash: b6998f4ac7ced2d85063186edbd47227b6d24ca5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559137"
---
# <a name="spaceinfo-structure"></a>Структура space_info

Содержит сведения о томе.

## <a name="syntax"></a>Синтаксис

```cpp
struct space_info
{
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
};
```

## <a name="members"></a>Участники

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|`unsigned long long capacity`|Представляет общее число байтов, которое может представлять том.|
|`unsigned long long free`|Представляет число байтов, не используемых для представления данных в томе.|
|`unsigned long long available`|Представляет число байтов, доступных для представления данных в томе.|

## <a name="requirements"></a>Требования

**Заголовок:** \<filesystem >

**Пространство имен:** std::experimental::filesystem

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md)<br/>
