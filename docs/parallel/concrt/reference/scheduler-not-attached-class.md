---
title: Класс scheduler_not_attached
ms.date: 11/04/2016
f1_keywords:
- scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached::scheduler_not_attached
helpviewer_keywords:
- scheduler_not_attached class
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
ms.openlocfilehash: be8a04c7cf6ef5aa4d6070e92df14e643395ef00
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262269"
---
# <a name="schedulernotattached-class"></a>Класс scheduler_not_attached

Этот класс описывает исключение, создаваемое при выполнении операции, при которой планировщик должен был присоединен к текущему контексту, а он не присоединен.

## <a name="syntax"></a>Синтаксис

```
class scheduler_not_attached : public std::exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[scheduler_not_attached](#ctor)|Перегружен. Создает объект `scheduler_not_attached`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`scheduler_not_attached`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> scheduler_not_attached

Создает объект `scheduler_not_attached`.

```
explicit _CRTIMP scheduler_not_attached(_In_z_ const char* _Message) throw();

scheduler_not_attached() throw();
```

### <a name="parameters"></a>Параметры

*_Message*<br/>
Описательное сообщение об ошибке.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс Scheduler](scheduler-class.md)
