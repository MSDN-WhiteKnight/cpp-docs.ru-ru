---
title: Класс task_canceled
ms.date: 11/04/2016
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
ms.openlocfilehash: caef1c62ff09ffb76f74d4a1453e9d59dcb7d45b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265500"
---
# <a name="taskcanceled-class"></a>Класс task_canceled

Этот класс описывает исключение, которое создается уровнем задач PPL для принудительной отмены текущей задачи. Он также создается методом `get()` метод [задачи](/visualstudio/extensibility/debugger/task-class-internal-members), для отмененной задачи.

## <a name="syntax"></a>Синтаксис

```
class task_canceled : public std::exception;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[task_canceled](#ctor)|Перегружен. Создает объект `task_canceled`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`task_canceled`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> task_canceled

Создает объект `task_canceled`.

```
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
