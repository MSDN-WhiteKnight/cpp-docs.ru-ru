---
title: Класс ISessionPropertiesImpl
ms.date: 11/04/2016
f1_keywords:
- ISessionPropertiesImpl
- ISessionPropertiesImpl::GetProperties
- ISessionPropertiesImpl.GetProperties
- GetProperties
- ISessionPropertiesImpl.SetProperties
- SetProperties
- ISessionPropertiesImpl::SetProperties
helpviewer_keywords:
- ISessionPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
ms.openlocfilehash: a6b2abc97a44117c0fdd7c08c61de7ba900d1115
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556313"
---
# <a name="isessionpropertiesimpl-class"></a>Класс ISessionPropertiesImpl

Предоставляет реализацию [ISessionProperties](https://docs.microsoft.com/previous-versions/windows/desktop/ms713721(v=vs.85)) интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ISessionPropertiesImpl :
   public ISessionProperties, 
   public CUtlProps<PropClass>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `ISessionPropertiesImpl`.

*PropClass*<br/>
Класс определяемые пользователем свойства, который по умолчанию используется *T*.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="interface-methods"></a>Методы интерфейса

|||
|-|-|
|[GetProperties](#getproperties)|Возвращает список свойств в группе свойств сеанса, в настоящее время заданы в сеансе.|
|[SetProperties](#setproperties)|Задает свойства в группе свойств сеанса.|

## <a name="remarks"></a>Примечания

Обязательный интерфейс для сеансов. Этот класс реализует свойства сеанса, вызвав статические функции, определенной на [сопоставление набора свойств](../../data/oledb/begin-propset-map.md). Сопоставление набора свойств должен быть указан в классе сеанса.

## <a name="getproperties"></a> ISessionPropertiesImpl::GetProperties

Возвращает список свойств в `DBPROPSET_SESSION` группу свойств, заданных в настоящее время на сеанс.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetProperties)(ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>Параметры

См. в разделе [ISessionProperties::GetProperties](https://docs.microsoft.com/previous-versions/windows/desktop/ms723643(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="setproperties"></a> ISessionPropertiesImpl::SetProperties

Задает свойства в `DBPROPSET_SESSION` группу свойств.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Параметры

См. в разделе [ISessionProperties::SetProperties](https://docs.microsoft.com/previous-versions/windows/desktop/ms714405(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)