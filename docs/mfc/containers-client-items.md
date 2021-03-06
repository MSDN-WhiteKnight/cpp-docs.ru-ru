---
title: Контейнеры. Клиентские элементы
ms.date: 11/04/2016
helpviewer_keywords:
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
ms.openlocfilehash: 0c7f4a63cb9a31b52be2d3574ddad29313df6a4d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298286"
---
# <a name="containers-client-items"></a>Контейнеры. Клиентские элементы

В этой статье объясняются клиентские элементы и из классов, что приложения должны наследовать его клиентские элементы.

Клиентские элементы являются элементами данных, принадлежащих другого приложения, которые могут быть содержащиеся в или ссылается документ приложения контейнера OLE. Внедренные элементы клиента, данные которого содержится в документе; те, данные которых хранятся в другом месте, ссылается документе-контейнере связаны.

Класс документа в приложении OLE является производным от класса [COleDocument](../mfc/reference/coledocument-class.md) , а не из `CDocument`. `COleDocument` Класс наследует от `CDocument` все функциональные возможности, необходимые для использования архитектуры document/view, на какие MFC основаны приложения. `COleDocument` также определяет интерфейс, который обрабатывает документ как коллекция `CDocItem` объектов. Несколько `COleDocument` функций-членов предоставляются для добавления, получения и удаления элементов этой коллекции.

Каждый контейнер должен быть производным по крайней мере один класс из `COleClientItem`. Объекты этого класса представляют элементы, внедренные или связанные, в документе OLE. Эти объекты существуют в течение жизненного цикла документа, содержащего их, если они не удалены из документа.

`CDocItem` является базовым классом для `COleClientItem` и `COleServerItem`. Объекты классов, производных от этих двух выступают в качестве посредников между объекта OLE и клиентские и серверные приложения, соответственно. Каждый раз, в документ добавляется новый элемент OLE платформы MFC добавляет новый объект приложения клиента `COleClientItem`-производный класс документа коллекцию `CDocItem` объектов.

## <a name="see-also"></a>См. также

[Контейнеры](../mfc/containers.md)<br/>
[Контейнеры. Составные файлы](../mfc/containers-compound-files.md)<br/>
[Контейнеры. Проблемы пользовательского интерфейса](../mfc/containers-user-interface-issues.md)<br/>
[Контейнеры. Расширенные возможности](../mfc/containers-advanced-features.md)<br/>
[Класс COleClientItem](../mfc/reference/coleclientitem-class.md)<br/>
[Класс COleServerItem](../mfc/reference/coleserveritem-class.md)
