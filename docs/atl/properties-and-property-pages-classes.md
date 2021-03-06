---
title: Свойства и классы страницы свойств (ATL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vc.atl.properties
helpviewer_keywords:
- property pages, classes
- properties [ATL], classes
- properties [ATL]
ms.assetid: 31616f98-69f8-48b2-8d58-b8e7d1c2b2d8
ms.openlocfilehash: f5d318cecc527d0c41124ccf14326ea308007b1d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290473"
---
# <a name="properties-and-property-pages-classes"></a>Свойства и классы страниц свойств

Следующие классы поддерживают свойства и страницы свойств:

- [CComDispatchDriver](../atl/reference/atl-typedefs.md#ccomdispatchdriver) извлекает или задает свойства объекта с помощью `IDispatch` указатель.

- [CStockPropImpl](../atl/reference/cstockpropimpl-class.md) реализует стандартных свойств, поддерживаемых ATL.

- [IPerPropertyBrowsingImpl](../atl/reference/iperpropertybrowsingimpl-class.md) обращается к сведениям на страницах свойств объекта.

- [IPersistPropertyBagImpl](../atl/reference/ipersistpropertybagimpl-class.md) хранит свойства объекта в контейнер свойств, предоставляемых клиентом.

- [IPropertyPageImpl](../atl/reference/ipropertypageimpl-class.md) управляет заданной страницы свойств в окне свойств.

- [IPropertyPage2Impl](../atl/reference/ipropertypage2impl-class.md) аналогичен `IPropertyPageImpl`, но также позволяет клиенту выбора конкретного свойства в окне свойств.

- [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md) получает CLSID для страниц свойств, поддерживаемых объектом.

## <a name="related-articles"></a>Связанные статьи

[Учебник по ATL](../atl/active-template-library-atl-tutorial.md)

[Страницы свойств COM в ATL](../atl/atl-com-property-pages.md)

## <a name="see-also"></a>См. также

[Общие сведения о классе](../atl/atl-class-overview.md)<br/>
[Макросы сопоставления свойств](../atl/reference/property-map-macros.md)
