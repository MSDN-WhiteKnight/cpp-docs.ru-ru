---
title: InterfaceListHelper - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceListHelper
helpviewer_keywords:
- InterfaceListHelper structure
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
ms.openlocfilehash: c29a44249b432a7e0c15164307e95c51ae8b0536
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336488"
---
# <a name="interfacelisthelper-structure"></a>InterfaceListHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename T0,
    typename T1 = Nil,
    typename T2 = Nil,
    typename T3 = Nil,
    typename T4 = Nil,
    typename T5 = Nil,
    typename T6 = Nil,
    typename T7 = Nil,
    typename T8 = Nil,
    typename T9 = Nil
>
struct InterfaceListHelper;

template <typename T0>
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;
```

### <a name="parameters"></a>Параметры

*T0*<br/>
Параметр шаблона, 0, который обязателен.

*T1*<br/>
Параметр шаблона, 1, который по умолчанию не определен.

*T2*<br/>
Параметр шаблона, 2, который по умолчанию не определен. Третий параметр шаблона.

*T3*<br/>
Параметр шаблона, 3, который по умолчанию не определен.

*T4*<br/>
Параметр шаблона, 4, который по умолчанию не определен.

*T5*<br/>
Параметр шаблона, 5, который по умолчанию не определен.

*T6*<br/>
Параметр шаблона, 6, которая по умолчанию не определен.

*T7*<br/>
Параметр шаблона, 7, который по умолчанию не определен.

*T8*<br/>
Параметр шаблона, 8, который по умолчанию не определен.

*T9*<br/>
Параметр шаблона, 9, который по умолчанию не определен.

## <a name="remarks"></a>Примечания

Строит `InterfaceList` типа путем рекурсивного применения аргументов параметра указанного шаблона.

**InterfaceListHelper** шаблон использует параметр шаблона *T0* определить первый элемент данных в `InterfaceList` структуры, а затем рекурсивно применяется  **InterfaceListHelper** шаблона для всех остальных параметров шаблона. **InterfaceListHelper** останавливается, когда нет оставшихся параметров шаблона.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание:|
|----------|-----------------|
|`TypeT`|Синоним для типа InterfaceList.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`InterfaceListHelper`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)