---
title: Класс auto_partitioner
ms.date: 11/04/2016
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
ms.openlocfilehash: 9e4701c39512613bd7525c2cc0e3d24a57e7689d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644929"
---
# <a name="autopartitioner-class"></a>Класс auto_partitioner

Класс `auto_partitioner` представляет метод, который алгоритмы `parallel_for`, `parallel_for_each` и `parallel_transform` используют по умолчанию для разделения обрабатываемого диапазона. Этот метод разделения использует как перенос диапазона для распределения нагрузки, так и отмену по итерациям.

## <a name="syntax"></a>Синтаксис

```
class auto_partitioner;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[auto_partitioner](#ctor)|Создает объект `auto_partitioner`.|
|[~ auto_partitioner деструктор](#dtor)|Уничтожает объект `auto_partitioner`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`auto_partitioner`

## <a name="requirements"></a>Требования

**Заголовок:** ppl.h

**Пространство имен:** concurrency

##  <a name="dtor"></a> ~ auto_partitioner

Уничтожает объект `auto_partitioner`.

```
~auto_partitioner();
```

##  <a name="ctor"></a> auto_partitioner

Создает объект `auto_partitioner`.

```
auto_partitioner();
```

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
