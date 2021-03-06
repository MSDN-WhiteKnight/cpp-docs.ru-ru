---
title: Настройка элемента заголовка&#39;вида
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
ms.openlocfilehash: 081260bd5c1cf6335d398a4fd773c9590dbc8030
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268841"
---
# <a name="customizing-the-header-item39s-appearance"></a>Настройка элемента заголовка&#39;вида

Установив *dwStyle* параметр при создании элемента управления заголовка ([CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create)), можно определить внешний вид и поведение заголовка элементы или заголовка самого элемента управления.

Вот примеры стилей, которые можно задать и их назначение:

- Чтобы сделать элемент заголовка выглядеть кнопка, используйте **HDS_BUTTONS** стиля.

   Этот стиль следует используйте, если вы хотите выполнять действия в ответ на щелчок мышью на элементе заголовка, например для сортировки данных по одному из столбцов, как в Microsoft Outlook.

- Чтобы предоставить элементы заголовка в виде «отслеживание» при прохождении курсора мыши над ними, используйте **HDS_HOTTRACK** стиля.

   Отслеживание отображает структуру 3D, когда указатель находится над элементом, в противном случае — значение неструктурированный панели.

- Чтобы указать, что элемент управления заголовка должны быть скрыты, используйте **HDS_HIDDEN** стиля.

   **HDS_HIDDEN** стиль указывает, что элемент управления заголовка предназначен для использования в качестве контейнера данных и не визуальному элементу управления. Этот стиль не скрывает элемент управления автоматически, но вместо этого влияет на поведение `CHeaderCtrl::Layout`. Значение, возвращаемое в *cy* членом `WINDOWPOS` структуры будут равны нулю, указывающее, что элемент управления не должен отображаться для пользователя.

Дополнительные сведения об этих свойствах см. в разделе [элементы](/windows/desktop/Controls/header-controls) в пакете Windows SDK. Сведения о добавлении элементов к элементу управления заголовка, см. в разделе [Добавление элементов управления заголовка](../mfc/adding-items-to-the-header-control.md).

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
