---
title: Установка режима объекта CStatusBarCtrl
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
ms.openlocfilehash: a6d1a0edb356f9737aa287809dd8bca4146c1854
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287938"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>Установка режима объекта CStatusBarCtrl

Существует два режима для `CStatusBarCtrl` объект: простые и непростые. В большинстве случаев ваш элемент управления строки состояния будет иметь один или несколько частей, а также текст и возможно значок или значки. Это называется непростые режим. Дополнительные сведения об этом режиме см. в разделе [инициализация частей объекта CStatusBarCtrl](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).

Тем не менее существуют случаи, когда необходима только для отображения одной строки текста. В этом случае для потребностей достаточно простой режим. Чтобы изменить режим `CStatusBarCtrl` объекта на simple, вызвать [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) функция-член. Когда элемент управления строки состояния в простом режиме, задать текст, вызвав `SetText` передача 255 в качестве значения для функции-члена *nPane* параметра.

Можно использовать [IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple) функцию, чтобы определить, какой режим `CStatusBarCtrl` объект.

> [!NOTE]
>  Если объект строки состояния, изменяется из непростой равным simple, или наоборот, немедленно перерисовке окна и, если применимо, автоматически восстанавливаются все определенные части.

## <a name="see-also"></a>См. также

[Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
