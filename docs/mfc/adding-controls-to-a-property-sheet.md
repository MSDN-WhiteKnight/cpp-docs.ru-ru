---
title: Добавление элементов управления на вкладку свойств
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
ms.openlocfilehash: 07b384b2db36ae59d4de8b99d9c07396ce793979
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296310"
---
# <a name="adding-controls-to-a-property-sheet"></a>Добавление элементов управления на вкладку свойств

По умолчанию страницу свойств выделяет область окна для страницы свойств, индекс вкладки и кнопки ОК, Отмена и применить. (Немодальный лист свойств не поддерживает ОК, Отмена и применить кнопки.) Можно добавить другие элементы управления в лист свойств. Например можно добавить в окно предварительного просмотра справа от области страницы свойств, чтобы показать пользователю, как будет выглядеть текущие параметры, если применяется к внешнему объекту.

Можно добавить элементы управления в диалоговом окне страницы свойств в `OnCreate` обработчика. Размещении дополнительные элементы управления обычно требуется увеличение размера диалоговое окно страницы свойств. После вызова базового класса **CPropertySheet::OnCreate**, вызовите [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) для получения, ширину и высоту окна листа свойств, выделенных на данный момент, разверните прямоугольника измерения и вызова [Функции MoveWindow](../mfc/reference/cwnd-class.md#movewindow) для изменения размера окна листа свойств.

## <a name="see-also"></a>См. также

[Страницы свойств](../mfc/property-sheets-mfc.md)<br/>
[Класс CPropertyPage](../mfc/reference/cpropertypage-class.md)<br/>
[Класс CPropertySheet](../mfc/reference/cpropertysheet-class.md)
