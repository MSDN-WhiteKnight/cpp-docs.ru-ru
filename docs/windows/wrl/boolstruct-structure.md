---
title: BoolStruct - структура
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
- internal/Microsoft::WRL::Details::BoolStruct::Member
helpviewer_keywords:
- Microsoft::WRL::Details::BoolStruct structure
- Microsoft::WRL::Details::BoolStruct::Member data member
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
ms.openlocfilehash: cdec425e317585abbd9730447e2c4fbb19b8250a
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336727"
---
# <a name="boolstruct-structure"></a>BoolStruct - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>Примечания

`BoolStruct` Структура определяет ли `ComPtr` управление временем существования объектов интерфейса. `BoolStruct` используется внутренним образом [BoolType()](comptr-class.md#operator-microsoft-wrl-details-booltype) оператор.

## <a name="members"></a>Участники

### <a name="public-data-members"></a>Открытые члены данных

Имя                          | Описание
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[BoolStruct::Member](#member) | Указывает, что [ComPtr](comptr-class.md) является, или не, управление временем существования объектов интерфейса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BoolStruct`

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="member"></a>BoolStruct::Member

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
int Member;
```

### <a name="remarks"></a>Примечания

Указывает, что [ComPtr](comptr-class.md) является, или не, управление временем существования объектов интерфейса.
