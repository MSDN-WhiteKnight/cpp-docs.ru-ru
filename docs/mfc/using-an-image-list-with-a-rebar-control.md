---
title: Использование списка изображений с элементом управления главной панели
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], rebar controls
- rebar controls [MFC], image lists
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
ms.openlocfilehash: fa5307c201850fc42439c79a1c638a0707379913
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285403"
---
# <a name="using-an-image-list-with-a-rebar-control"></a>Использование списка изображений с элементом управления главной панели

Каждой зоны главной панели может содержать, помимо прочего, изображение из списка связанных изображений. Ниже описаны шаги, необходимые для отображения изображения в зону главной панели.

### <a name="to-display-images-in-a-rebar-band"></a>Для отображения изображений в зону главной панели

1. Присоединение к списку изображений объекта элемента управления "Главная панель" с помощью вызова [SetImageList](../mfc/reference/crebarctrl-class.md#setimagelist), передача указателя в существующий список изображений.

1. Изменить **REBARBANDINFO** структуру для назначения изображения зону главной панели:

   - Задайте *fMask* члена `RBBIM_IMAGE`, с помощью побитового оператора OR для включения дополнительных флагов при необходимости.

   - Задайте *iImage* члена списком индекс изображения изображения для отображения.

1. Инициализируйте все оставшиеся элементы данных, такие как размер, текст и дескриптор содержащиеся дочерние окна, введите необходимые сведения.

1. Вставить новый диапазон (с изображением) с помощью вызова [CReBarCtrl::InsertBand](../mfc/reference/crebarctrl-class.md#insertband), передав **REBARBANDINFO** структуры.

В следующем примере предполагается, что существующего объекта списка изображений с двумя образами был подключен к объект элемента управления "Главная панель" (`m_wndReBar`). Новый зону главной панели (определяется `rbi`), содержащий первый образ, добавляется с помощью вызова `InsertBand`:

[!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/cpp/using-an-image-list-with-a-rebar-control_1.cpp)]

## <a name="see-also"></a>См. также

[Использование CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
