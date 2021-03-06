---
title: Указание страниц свойств (ATL)
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPages
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
ms.openlocfilehash: d738759dfba50f26b788ee1b0761baf8bc4b00ab
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287149"
---
# <a name="specifying-property-pages"></a>Указание страниц свойств

При создании элемента управления ActiveX, часто требуется связать его с помощью страниц свойств, которые могут использоваться для задания свойств элемента управления. Контроль использования контейнеров с помощью `ISpecifyPropertyPages` интерфейс, чтобы узнать, какие страницы свойств можно использовать для задания свойств элемента управления. Необходимо реализовать этот интерфейс для вашего элемента управления.

Для реализации `ISpecifyPropertyPages` с использованием библиотеки ATL, выполните следующие действия:

1. Наследование класса из [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md).

1. Добавьте запись для `ISpecifyPropertyPages` для вашего класса COM карты.

1. Добавить [PROP_PAGE](reference/property-map-macros.md#prop_page) запись, чтобы в схеме сопоставления свойств для каждой страницы, связанный с элементом управления.

> [!NOTE]
> При создании стандартного элемента управления с помощью [мастер элементов управления ATL](../atl/reference/atl-control-wizard.md), будет достаточно для добавления записей PROP_PAGE в схеме сопоставления свойств. Мастер создает необходимый код для других шагов.

Затрачивать контейнеров будет отображаться на страницах свойств, указанный в том же порядке, как записи PROP_PAGE в сопоставлении свойств. Как правило следует помещать записи страницы стандартных свойств после операции для настраиваемых страниц в сопоставлении свойств, таким образом, чтобы пользователи, см. на страницах, определенных в элемент управления сначала.

## <a name="example"></a>Пример

Следующий класс календаря управления использует `ISpecifyPropertyPages` интерфейс сообщить контейнеры, которые можно задать его свойства с помощью страницы дат и акций цвета.

[!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]

## <a name="see-also"></a>См. также

[Страницы свойств](../atl/atl-com-property-pages.md)<br/>
[Пример ATLPages](../visual-cpp-samples.md)
