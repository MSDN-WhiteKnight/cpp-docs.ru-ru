---
title: _com_ptr_t::GetInterfacePtr
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetInterfacePtr
helpviewer_keywords:
- GetInterfacePtr method [C++]
ms.assetid: 55e3e2c7-c939-48b5-a905-4b9cbefeea7e
ms.openlocfilehash: dba5b5e2fcebf87ef196e2f33adedf88cc42b559
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326177"
---
# <a name="comptrtgetinterfaceptr"></a>_com_ptr_t::GetInterfacePtr

**Блок, относящийся только к системам Microsoft**

Возвращает инкапсулированный указатель на интерфейс.

## <a name="syntax"></a>Синтаксис

```
Interface* GetInterfacePtr( ) const throw( );
Interface*& GetInterfacePtr() throw();
```

## <a name="remarks"></a>Примечания

Возвращает инкапсулированный указатель на интерфейс, который может быть равно NULL.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Класс _com_ptr_t](../cpp/com-ptr-t-class.md)