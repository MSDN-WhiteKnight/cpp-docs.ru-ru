---
title: Стили элемента управления "Ползунок"
ms.date: 11/04/2016
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
ms.openlocfilehash: c6765445552826b71cca278c1fbbc66e500cb75a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296858"
---
# <a name="slider-control-styles"></a>Стили элемента управления "Ползунок"

Элементы управления "ползунок" ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) может иметь вертикальную или горизонтальную ориентацию. Они могут иметь деления для обеих сторон, как стороны или ни одного. Они также могут использоваться для указания диапазона последовательных значений. Эти свойства служат стили элемента управления "ползунок", которые вы указываете при создании элемента управления slider.

Стили TBS_HORZ и TBS_VERT определяют ориентацию элемента управления "ползунок". Если вы не укажете ориентацию, элемент управления "ползунок" ориентирован горизонтально.

Стиль TBS_AUTOTICKS создает элемент управления "ползунок", который имеет деления для каждого фрагмента в своем диапазоне значений. Эти проверки делений добавляются автоматически при вызове [SetRange](../mfc/reference/csliderctrl-class.md#setrange) функция-член. Если вы не укажете TBS_AUTOTICKS, можно использовать функции-члены, такие как [SetTic](../mfc/reference/csliderctrl-class.md#settic) и [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq), чтобы указать расположение меток делений. Чтобы создать элемент управления "ползунок", не содержит меток делений, можно использовать стиль TBS_NOTICKS.

Можно отобразить деления на один или оба границы элемента управления "ползунок". Для горизонтального ползунка элементов управления можно указать стиль TBS_BOTTOM или TBS_TOP. Для вертикального ползунка элементов управления можно указать стиль TBS_RIGHT или TBS_LEFT. (TBS_BOTTOM и TBS_RIGHT являются параметрами по умолчанию). Для делений на обеих сторонах элемента управления "ползунок" в любой ориентации укажите стиль TBS_BOTH.

Элемент управления "ползунок" можно отобразить диапазон выбора только в том случае, если указать стиль TBS_ENABLESELRANGE при ее создании. Если элемент управления "ползунок" имеет этот стиль, деления на начальное и конечное положение диапазона выделения представляются в милливаттах треугольники (а не по вертикали дефисами), и выделяется диапазона выделения. Например Выбор диапазоны могут пригодиться при простое приложение планирования. Пользователь может выбрать диапазон делений, соответствующий часов в день для определения начала собрания.

По умолчанию длина ползунок элемента управления "ползунок" изменяется при изменении выделения диапазона. Если элемент управления "ползунок" имеет стиль TBS_FIXEDLENGTH, длина ползунок остается неизменным даже при изменении диапазона выделения. Элемент управления "ползунок", который имеет стиль TBS_NOTHUMB не включают ползунок.

## <a name="see-also"></a>См. также

[Использование CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
