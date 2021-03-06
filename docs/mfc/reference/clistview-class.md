---
title: Класс CListView
ms.date: 11/04/2016
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
helpviewer_keywords:
- CListView [MFC], CListView
- CListView [MFC], GetListCtrl
- CListView [MFC], RemoveImageList
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
ms.openlocfilehash: 4507c2a640296c2d2619b1da7a0ebae2bc6ef401
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291291"
---
# <a name="clistview-class"></a>Класс CListView

Упрощает использование элемента управления списком и [CListCtrl](../../mfc/reference/clistctrl-class.md), который инкапсулирует список функциональность в архитектуру представления документов MFC.

## <a name="syntax"></a>Синтаксис

```
class CListView : public CCtrlView
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CListView::CListView](#clistview)|Создает объект `CListView`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CListView::GetListCtrl](#getlistctrl)|Возвращает элемент управления списка, связанный с представлением.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание:|
|----------|-----------------|
|[CListView::RemoveImageList](#removeimagelist)|Удаляет список указанное изображение в представлении списка.|

## <a name="remarks"></a>Примечания

Дополнительные сведения об этой архитектуре см. в обзоре, для [CView](../../mfc/reference/cview-class.md) класс и перекрестные ссылки, указанных там.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CListView`

## <a name="requirements"></a>Требования

**Заголовок:** afxcview.h

##  <a name="clistview"></a>  CListView::CListView

Создает объект `CListView`.

```
CListView();
```

##  <a name="getlistctrl"></a>  CListView::GetListCtrl

Вызов этой функции-члена для получения ссылки на элемент управления списка, связанный с представлением.

```
CListCtrl& GetListCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент управления списка, связанный с представлением.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]

##  <a name="removeimagelist"></a>  CListView::RemoveImageList

Удаляет список указанное изображение в представлении списка.

```
void RemoveImageList(int nImageList);
```

### <a name="parameters"></a>Параметры

*nImageList*<br/>
Отсчитываемый от нуля индекс изображения, которое требуется удалить.

## <a name="see-also"></a>См. также

[Пример MFC ROWLIST](../../visual-cpp-samples.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CCtrlView](../../mfc/reference/cctrlview-class.md)
