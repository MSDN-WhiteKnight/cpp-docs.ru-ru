---
title: Move - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
ms.openlocfilehash: 1a03216197462090f38d3bc2065fe227f0667919
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54337663"
---
# <a name="move-function"></a>Move - функция

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
inline typename RemoveReference<T>::Type&& Move(
   _Inout_ T&& arg
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип аргумента.

*arg*<br/>
Аргумент для перемещения.

## <a name="return-value"></a>Возвращаемое значение

Параметр *arg* после ссылка или rvalue атрибутами, если таковые имеются, будут удалены.

## <a name="remarks"></a>Примечания

Перемещает указанный аргумент из одного расположения в другое.

Дополнительные сведения см. в разделе **семантику перемещения** раздел [декларатор ссылки Rvalue: & &](../../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)