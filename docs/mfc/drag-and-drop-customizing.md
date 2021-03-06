---
title: 'Путем перетаскивания: Настройка'
ms.date: 11/04/2016
helpviewer_keywords:
- drag and drop [MFC], implementing in non-OLE applications
- drag and drop [MFC], customizing behavior
- drag and  [MFC], COleDataSource object
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], customizing behavior
ms.assetid: 03369d3e-46bf-4140-b58c-d0c9657cf38a
ms.openlocfilehash: b4749f8d45c962f8b9217e4c6367538d3e6a3608
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262601"
---
# <a name="drag-and-drop-customizing"></a>Путем перетаскивания: Настройка

Реализация по умолчанию функции и перетаскивать достаточно для большинства приложений. Однако некоторым приложениям может понадобиться изменить это стандартное поведение. Здесь объясняются действия, необходимые изменить эти значения по умолчанию. Кроме того этот метод можно использовать для установки приложений, которые не поддерживают составные документы в качестве источников перетаскивания.

Если вы настраиваете стандартное поведение и перетаскивания OLE, или имеется приложение, отличных от OLE, необходимо создать `COleDataSource` объект для хранения данных. Когда пользователь начинает операцию перетаскивания и вставки, код должен вызывать `DoDragDrop` функции из этого объекта, а не от других классов, которые поддерживают операции перетаскивания и вставки.

При необходимости можно создать `COleDropSource` объект для управления раскрывающегося и переопределить некоторые из ее функций, в зависимости от типа вы хотите изменить поведение. Этот объект источника перетаскивания затем передается `COleDataSource::DoDragDrop` для изменения поведения по умолчанию для этих функций. Эти разные параметры позволяют значительную гибкость в поддержке операций перетаскивания и вставки в приложении. Дополнительные сведения об источниках данных см. в статье [объекты данных и источники данных (OLE)](../mfc/data-objects-and-data-sources-ole.md).

Вы можете переопределить следующие функции для настройки операций перетаскивания и вставки:

|Переопределение|Для настройки|
|--------------|------------------|
|`OnBeginDrag`|Как начала перетаскивания после вызова метода `DoDragDrop`.|
|`GiveFeedback`|Визуальной обратной связи, таких как внешний вид курсора, для различных результатов.|
|`QueryContinueDrag`|Завершение операции перетаскивания и вставки. Эта функция позволяет проверить модификатор ключевых состояний во время операции перетаскивания.|

## <a name="see-also"></a>См. также

[Перетаскивание (OLE)](../mfc/drag-and-drop-ole.md)<br/>
[Класс COleDropSource](../mfc/reference/coledropsource-class.md)<br/>
[Класс COleDataSource](../mfc/reference/coledatasource-class.md)
