---
title: AsyncStatusInternal - перечисление
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
ms.openlocfilehash: b38d58603eafeaa76c79873bbf375b4a3b405cdb
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336687"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal - перечисление

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
enum AsyncStatusInternal;
```

## <a name="remarks"></a>Примечания

Задает сопоставление между внутренними перечислениями состояний асинхронных операций и перечислением `Windows::Foundation::AsyncStatus`.

## <a name="members"></a>Участники

`_Created`<br/>
Эквивалентно `::Windows::Foundation::AsyncStatus::Created`.

`_Started`<br/>
Эквивалентно `::Windows::Foundation::AsyncStatus::Started`.

`_Completed`<br/>
Эквивалентно `::Windows::Foundation::AsyncStatus::Completed`.

`_Cancelled`<br/>
Эквивалентно `::Windows::Foundation::AsyncStatus::Cancelled`.

`_Error`<br/>
Эквивалентно `::Windows::Foundation::AsyncStatus::Error`.

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)