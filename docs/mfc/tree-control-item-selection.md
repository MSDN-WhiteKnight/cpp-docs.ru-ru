---
title: Выбор элемента древовидного элемента управления
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
ms.openlocfilehash: a88a2c8ea5b935bbcb1f40b705337ff676d8b8a5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264122"
---
# <a name="tree-control-item-selection"></a>Выбор элемента древовидного элемента управления

При изменении выбора от одного элемента к другому, дерево ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) отправляет [TVN_SELCHANGING](/windows/desktop/Controls/tvn-selchanging) и [TVN_SELCHANGED](/windows/desktop/Controls/tvn-selchanged) сообщений уведомления. Оба уведомления содержат значение, указывающее, находится ли изменение в результате щелчка кнопкой мыши или нажатие клавиши. Уведомления также содержат сведения о элемент, который приобретает все выделения и элемент, который теряет выделение. Эти сведения можно использовать для задания атрибутов элемента, которые зависят от состояния выбора элемента. Возвращение **TRUE** в ответ на `TVN_SELCHANGING` предотвращает изменение; Выбор возвращение **FALSE** разрешает изменение.

Выбор приложения можно изменить путем вызова [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) функция-член.

## <a name="see-also"></a>См. также

[Использование CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
