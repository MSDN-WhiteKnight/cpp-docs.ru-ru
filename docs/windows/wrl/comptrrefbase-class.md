---
title: ComPtrRefBase - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
- client/Microsoft::WRL::Details::ComPtrRefBase::ptr_
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRefBase class
- Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable** operator
- Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown** operator
- Microsoft::WRL::Details::ComPtrRefBase::ptr_ data member
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
ms.openlocfilehash: df4e2aa1ce650fd5b1f04baf2f7c4cd2fb4cff93
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336800"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase - класс

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Объект [ComPtr\<T >](comptr-class.md) тип или тип, производный от него, а не просто интерфейс, представленный `ComPtr`.

## <a name="remarks"></a>Примечания

Представляет базовый класс для [ComPtrRef](comptrref-class.md) класса.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя            | Описание
--------------- | -------------------------------------------------
`InterfaceType` | Синоним для типа параметра-шаблона *T*.

### <a name="public-operators"></a>Открытые операторы

Имя                                                                       | Описание:
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[ComPtrRefBase::operator IInspectable**](#operator-iinspectable-star-star) | Приводит текущие [ptr_](#ptr) данные-член в указатель к a указатель to `IInspectable` интерфейс.
[ComPtrRefBase::operator IUnknown **](#operator-iunknown-star-star)         | Приводит текущие [ptr_](#ptr) данные-член в указатель к a указатель to `IUnknown` интерфейс.

### <a name="protected-data-members"></a>Защищенные члены данных

name                        | Описание
--------------------------- | ----------------------------------------------------------------
[ComPtrRefBase::ptr_](#ptr) | Указатель на тип, заданный текущим параметром шаблона.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ComPtrRefBase`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="operator-iinspectable-star-star"></a>ComPtrRefBase::operator IInspectable\* \* оператор

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>Примечания

Приводит текущие [ptr_](#ptr) данные-член в указатель к a указатель to `IInspectable` интерфейс.

Ошибка создается в том случае, если текущий `ComPtrRefBase` не является производным от `IInspectable`.

Это приведение доступна только если `__WRL_CLASSIC_COM__` определен.

## <a name="operator-iunknown-star-star"></a>Оператор ComPtrRefBase::operator IUnknown **

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>Примечания

Приводит текущие [ptr_](#ptr) данные-член в указатель к a указатель to `IUnknown` интерфейс.

Ошибка создается в том случае, если текущий `ComPtrRefBase` не является производным от `IUnknown`.

## <a name="ptr"></a>ComPtrRefBase::ptr_

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
T* ptr_;
```

### <a name="remarks"></a>Примечания

Указатель на тип, заданный текущим параметром шаблона. `ptr_` является элементом защищенных данных.
