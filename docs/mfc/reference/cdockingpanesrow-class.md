---
title: Класс CDockingPanesRow
ms.date: 10/18/2018
f1_keywords:
- CDockingPanesRow
- AFXDOCKINGPANESROW/CDockingPanesRow
- AFXDOCKINGPANESROW/CDockingPanesRow::AddPane
- AFXDOCKINGPANESROW/CDockingPanesRow::AddPaneFromRow
- AFXDOCKINGPANESROW/CDockingPanesRow::ArrangePanes
- AFXDOCKINGPANESROW/CDockingPanesRow::CalcFixedLayout
- AFXDOCKINGPANESROW/CDockingPanesRow::Create
- AFXDOCKINGPANESROW/CDockingPanesRow::ExpandStretchedPanes
- AFXDOCKINGPANESROW/CDockingPanesRow::ExpandStretchedPanesRect
- AFXDOCKINGPANESROW/CDockingPanesRow::FixupVirtualRects
- AFXDOCKINGPANESROW/CDockingPanesRow::GetAvailableLength
- AFXDOCKINGPANESROW/CDockingPanesRow::GetAvailableSpace
- AFXDOCKINGPANESROW/CDockingPanesRow::GetClientRect
- AFXDOCKINGPANESROW/CDockingPanesRow::GetDockSite
- AFXDOCKINGPANESROW/CDockingPanesRow::GetExtraSpace
- AFXDOCKINGPANESROW/CDockingPanesRow::GetGroupFromPane
- AFXDOCKINGPANESROW/CDockingPanesRow::GetID
- AFXDOCKINGPANESROW/CDockingPanesRow::GetMaxPaneSize
- AFXDOCKINGPANESROW/CDockingPanesRow::GetPaneCount
- AFXDOCKINGPANESROW/CDockingPanesRow::GetPaneList
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowAlignment
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowHeight
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowOffset
- AFXDOCKINGPANESROW/CDockingPanesRow::GetVisibleCount
- AFXDOCKINGPANESROW/CDockingPanesRow::GetWindowRect
- AFXDOCKINGPANESROW/CDockingPanesRow::HasPane
- AFXDOCKINGPANESROW/CDockingPanesRow::IsEmpty
- AFXDOCKINGPANESROW/CDockingPanesRow::IsExclusiveRow
- AFXDOCKINGPANESROW/CDockingPanesRow::IsHorizontal
- AFXDOCKINGPANESROW/CDockingPanesRow::IsVisible
- AFXDOCKINGPANESROW/CDockingPanesRow::Move
- AFXDOCKINGPANESROW/CDockingPanesRow::MovePane
- AFXDOCKINGPANESROW/CDockingPanesRow::OnResizePane
- AFXDOCKINGPANESROW/CDockingPanesRow::RedrawAll
- AFXDOCKINGPANESROW/CDockingPanesRow::RemovePane
- AFXDOCKINGPANESROW/CDockingPanesRow::ReplacePane
- AFXDOCKINGPANESROW/CDockingPanesRow::RepositionPanes
- AFXDOCKINGPANESROW/CDockingPanesRow::Resize
- AFXDOCKINGPANESROW/CDockingPanesRow::ResizeByPaneDivider
- AFXDOCKINGPANESROW/CDockingPanesRow::ScreenToClient
- AFXDOCKINGPANESROW/CDockingPanesRow::SetExtra
- AFXDOCKINGPANESROW/CDockingPanesRow::ShowDockSiteRow
- AFXDOCKINGPANESROW/CDockingPanesRow::ShowPane
- AFXDOCKINGPANESROW/CDockingPanesRow::UpdateVisibleState
helpviewer_keywords:
- CDockingPanesRow [MFC], AddPane
- CDockingPanesRow [MFC], AddPaneFromRow
- CDockingPanesRow [MFC], ArrangePanes
- CDockingPanesRow [MFC], CalcFixedLayout
- CDockingPanesRow [MFC], Create
- CDockingPanesRow [MFC], ExpandStretchedPanes
- CDockingPanesRow [MFC], ExpandStretchedPanesRect
- CDockingPanesRow [MFC], FixupVirtualRects
- CDockingPanesRow [MFC], GetAvailableLength
- CDockingPanesRow [MFC], GetAvailableSpace
- CDockingPanesRow [MFC], GetClientRect
- CDockingPanesRow [MFC], GetDockSite
- CDockingPanesRow [MFC], GetExtraSpace
- CDockingPanesRow [MFC], GetGroupFromPane
- CDockingPanesRow [MFC], GetID
- CDockingPanesRow [MFC], GetMaxPaneSize
- CDockingPanesRow [MFC], GetPaneCount
- CDockingPanesRow [MFC], GetPaneList
- CDockingPanesRow [MFC], GetRowAlignment
- CDockingPanesRow [MFC], GetRowHeight
- CDockingPanesRow [MFC], GetRowOffset
- CDockingPanesRow [MFC], GetVisibleCount
- CDockingPanesRow [MFC], GetWindowRect
- CDockingPanesRow [MFC], HasPane
- CDockingPanesRow [MFC], IsEmpty
- CDockingPanesRow [MFC], IsExclusiveRow
- CDockingPanesRow [MFC], IsHorizontal
- CDockingPanesRow [MFC], IsVisible
- CDockingPanesRow [MFC], Move
- CDockingPanesRow [MFC], MovePane
- CDockingPanesRow [MFC], OnResizePane
- CDockingPanesRow [MFC], RedrawAll
- CDockingPanesRow [MFC], RemovePane
- CDockingPanesRow [MFC], ReplacePane
- CDockingPanesRow [MFC], RepositionPanes
- CDockingPanesRow [MFC], Resize
- CDockingPanesRow [MFC], ResizeByPaneDivider
- CDockingPanesRow [MFC], ScreenToClient
- CDockingPanesRow [MFC], SetExtra
- CDockingPanesRow [MFC], ShowDockSiteRow
- CDockingPanesRow [MFC], ShowPane
- CDockingPanesRow [MFC], UpdateVisibleState
ms.assetid: e7a17832-0ebb-4bce-b799-cec9b60f76fe
ms.openlocfilehash: e5720fa2ff8e85092b246002b7961ce3830ee7e3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57277993"
---
# <a name="cdockingpanesrow-class"></a>Класс CDockingPanesRow

Управляет списком областей, которые находятся в той же горизонтальной или вертикальной строке (столбце) сайта закрепления.

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CDockingPanesRow : public CObject
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CDockingPanesRow::CDockingPanesRow`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CDockingPanesRow::AddPane](#addpane)||
|[CDockingPanesRow::AddPaneFromRow](#addpanefromrow)||
|[CDockingPanesRow::ArrangePanes](#arrangepanes)|Упорядочивает панели в строке в соответствии с заданными параметрами полей и интервалов.|
|[CDockingPanesRow::CalcFixedLayout](#calcfixedlayout)||
|[CDockingPanesRow::Create](#create)||
|[CDockingPanesRow::ExpandStretchedPanes](#expandstretchedpanes)||
|[CDockingPanesRow::ExpandStretchedPanesRect](#expandstretchedpanesrect)||
|[CDockingPanesRow::FixupVirtualRects](#fixupvirtualrects)||
|[CDockingPanesRow::GetAvailableLength](#getavailablelength)||
|[CDockingPanesRow::GetAvailableSpace](#getavailablespace)||
|[CDockingPanesRow::GetClientRect](#getclientrect)||
|[CDockingPanesRow::GetDockSite](#getdocksite)||
|[CDockingPanesRow::GetExtraSpace](#getextraspace)||
|[CDockingPanesRow::GetGroupFromPane](#getgroupfrompane)||
|[CDockingPanesRow::GetID](#getid)||
|[CDockingPanesRow::GetMaxPaneSize](#getmaxpanesize)||
|[CDockingPanesRow::GetPaneCount](#getpanecount)||
|[CDockingPanesRow::GetPaneList](#getpanelist)||
|[CDockingPanesRow::GetRowAlignment](#getrowalignment)||
|[CDockingPanesRow::GetRowHeight](#getrowheight)||
|[CDockingPanesRow::GetRowOffset](#getrowoffset)||
|[CDockingPanesRow::GetVisibleCount](#getvisiblecount)||
|[CDockingPanesRow::GetWindowRect](#getwindowrect)||
|[CDockingPanesRow::HasPane](#haspane)||
|[CDockingPanesRow::IsEmpty](#isempty)||
|[CDockingPanesRow::IsExclusiveRow](#isexclusiverow)||
|[CDockingPanesRow::IsHorizontal](#ishorizontal)||
|[CDockingPanesRow::IsVisible](#isvisible)||
|[CDockingPanesRow::Move](#move)||
|[CDockingPanesRow::MovePane](#movepane)||
|[CDockingPanesRow::OnResizePane](#onresizepane)||
|[CDockingPanesRow::RedrawAll](#redrawall)||
|[CDockingPanesRow::RemovePane](#removepane)||
|[CDockingPanesRow::ReplacePane](#replacepane)||
|[CDockingPanesRow::RepositionPanes](#repositionpanes)||
|[CDockingPanesRow::Resize](#resize)||
|[CDockingPanesRow::ResizeByPaneDivider](#resizebypanedivider)||
|[CDockingPanesRow::ScreenToClient](#screentoclient)||
|[CDockingPanesRow::SetExtra](#setextra)||
|[CDockingPanesRow::ShowDockSiteRow](#showdocksiterow)||
|[CDockingPanesRow::ShowPane](#showpane)||
|[CDockingPanesRow::UpdateVisibleState](#updatevisiblestate)||

## <a name="remarks"></a>Примечания

Объекты класса `CDockingPanesRow` создаются внутренним образом объектами сайта закрепления.

## <a name="example"></a>Пример

В этом примере демонстрируется получение объекта `CDockingPanesRow` из объекта `CMFCAutoHideBar`.

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cdockingpanesrow-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxDockingPanesRow.h

##  <a name="addpane"></a>  CDockingPanesRow::AddPane

```
virtual void AddPane(
    CPane* pControlBar,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL,
    BOOL bAddLast = FALSE);
```

### <a name="parameters"></a>Параметры

[in] *pControlBar*<br/>

[in] *dockMethod*<br/>

[in] *lpRect*<br/>

[in] *bAddLast*<br/>

### <a name="remarks"></a>Примечания

##  <a name="addpanefromrow"></a>  CDockingPanesRow::AddPaneFromRow

```
virtual void AddPaneFromRow(
    CPane* pControlBar,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Параметры

[in] *pControlBar*<br/>

[in] *dockMethod*<br/>

### <a name="remarks"></a>Примечания

##  <a name="arrangepanes"></a>  CDockingPanesRow::ArrangePanes

Упорядочивает закрепления панели в строке в соответствии с заданного предела и интервал между параметрами.

```
virtual void ArrangePanes(
    int nMargin,
    int nSpacing);
```

### <a name="parameters"></a>Параметры

*nMargin*<br/>
[in] Задает смещение, в пикселях области первый от верхнего левого угла строки.

*nSpacing*<br/>
[in] Задает расстояние в пикселях между областями.

### <a name="remarks"></a>Примечания

Этот метод используется для размещения панелей в строке, где будет закреплен. После вызова этого метода необходимо вызвать `CDockingPanesRow::FixupVirtualRects(FALSE, NULL)`.

##  <a name="calcfixedlayout"></a>  CDockingPanesRow::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Параметры

[in] *bStretch*<br/>

[in] *bHorz*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="cdockingpanesrow"></a>  CDockingPanesRow::CDockingPanesRow

```
CDockingPanesRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nHeight);
```

### <a name="parameters"></a>Параметры

[in] *pParentDockBar*<br/>

[in] *nOffset*<br/>

[in] *nHeight*<br/>

### <a name="remarks"></a>Примечания

##  <a name="create"></a>  CDockingPanesRow::Create

```
virtual BOOL Create();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="expandstretchedpanes"></a>  CDockingPanesRow::ExpandStretchedPanes

```
void ExpandStretchedPanes();
```

### <a name="remarks"></a>Примечания

##  <a name="expandstretchedpanesrect"></a>  CDockingPanesRow::ExpandStretchedPanesRect

```
void ExpandStretchedPanesRect();
```

### <a name="remarks"></a>Примечания

##  <a name="fixupvirtualrects"></a>  CDockingPanesRow::FixupVirtualRects

```
void FixupVirtualRects(
    bool bMoveBackToVirtualRect,
    CPane* pBarToExclude = NULL);
```

### <a name="parameters"></a>Параметры

[in] *bMoveBackToVirtualRect*<br/>

[in] *pBarToExclude*<br/>

### <a name="remarks"></a>Примечания

##  <a name="getavailablelength"></a>  CDockingPanesRow::GetAvailableLength

```
virtual int GetAvailableLength(BOOL bUseVirtualRect = FALSE) const;
```

### <a name="parameters"></a>Параметры

[in] *bUseVirtualRect*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getavailablespace"></a>  CDockingPanesRow::GetAvailableSpace

```
virtual void GetAvailableSpace(CRect& rect);
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

### <a name="remarks"></a>Примечания

##  <a name="getclientrect"></a>  CDockingPanesRow::GetClientRect

```
void GetClientRect(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

### <a name="remarks"></a>Примечания

##  <a name="getdocksite"></a>  CDockingPanesRow::GetDockSite

```
CDockSite* GetDockSite() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getextraspace"></a>  CDockingPanesRow::GetExtraSpace

```
int GetExtraSpace() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getgroupfrompane"></a>  CDockingPanesRow::GetGroupFromPane

```
void GetGroupFromPane(
    CPane* pBar,
    CObList& lst);
```

### <a name="parameters"></a>Параметры

[in] *pBar*<br/>

[in] *lst*<br/>

### <a name="remarks"></a>Примечания

##  <a name="getid"></a>  CDockingPanesRow::GetID

```
int GetID() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getmaxpanesize"></a>  CDockingPanesRow::GetMaxPaneSize

```
int GetMaxPaneSize(BOOL bSkipHiddenBars = TRUE) const;
```

### <a name="parameters"></a>Параметры

[in] *bSkipHiddenBars*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getpanecount"></a>  CDockingPanesRow::GetPaneCount

```
int GetPaneCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getpanelist"></a>  CDockingPanesRow::GetPaneList

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getrowalignment"></a>  CDockingPanesRow::GetRowAlignment

```
DWORD GetRowAlignment() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getrowheight"></a>  CDockingPanesRow::GetRowHeight

```
int GetRowHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getrowoffset"></a>  CDockingPanesRow::GetRowOffset

```
int GetRowOffset() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getvisiblecount"></a>  CDockingPanesRow::GetVisibleCount

```
virtual int GetVisibleCount();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getwindowrect"></a>  CDockingPanesRow::GetWindowRect

```
void GetWindowRect(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

### <a name="remarks"></a>Примечания

##  <a name="haspane"></a>  CDockingPanesRow::HasPane

```
BOOL HasPane(CBasePane* pControlBar);
```

### <a name="parameters"></a>Параметры

[in] *pControlBar*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="isempty"></a>  CDockingPanesRow::IsEmpty

```
virtual BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="isexclusiverow"></a>  CDockingPanesRow::IsExclusiveRow

```
virtual BOOL IsExclusiveRow() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ishorizontal"></a>  CDockingPanesRow::IsHorizontal

```
bool IsHorizontal() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="isvisible"></a>  CDockingPanesRow::IsVisible

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="move"></a>  CDockingPanesRow::Move

```
virtual void Move(int nOffset);
```

### <a name="parameters"></a>Параметры

[in] *nOffset*<br/>

### <a name="remarks"></a>Примечания

##  <a name="movepane"></a>  CDockingPanesRow::MovePane

```
void MovePane(
    CPane* pControlBar,
    CPoint ptOffset,
    BOOL bSwapControlBars,
    HDWP& hdwp);

void MovePane(
    CPane* pControlBar,
    CRect rectTarget,
    HDWP& hdwp);

void MovePane(
    CPane* pControlBar,
    int nOffset,
    bool bForward,
    HDWP& hdwp);

void MovePane(
    CPane* pControlBar,
    int nAbsolutOffset,
    HDWP& hdwp);
```

### <a name="parameters"></a>Параметры

[in] *pControlBar*<br/>

[in] *ptOffset*<br/>

[in] *bSwapControlBars*<br/>

[in] *hdwp*<br/>

[in] *rectTarget*<br/>

[in] *nOffset*<br/>

[in] *bForward*<br/>

[in] *nAbsolutOffset*<br/>

### <a name="remarks"></a>Примечания

##  <a name="onresizepane"></a>  CDockingPanesRow::OnResizePane

```
virtual void OnResizePane(CBasePane* pControlBar);
```

### <a name="parameters"></a>Параметры

[in] *pControlBar*<br/>

### <a name="remarks"></a>Примечания

##  <a name="redrawall"></a>  CDockingPanesRow::RedrawAll

```
void RedrawAll();
```

### <a name="remarks"></a>Примечания

##  <a name="removepane"></a>  CDockingPanesRow::RemovePane

```
virtual void RemovePane(CPane* pControlBar);
```

### <a name="parameters"></a>Параметры

[in] *pControlBar*<br/>

### <a name="remarks"></a>Примечания

##  <a name="replacepane"></a>  CDockingPanesRow::ReplacePane

```
virtual BOOL ReplacePane(
    CPane* pBarOld,
    CPane* pBarNew);
```

### <a name="parameters"></a>Параметры

[in] *pBarOld*<br/>

[in] *pBarNew*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="repositionpanes"></a>  CDockingPanesRow::RepositionPanes

```
virtual void RepositionPanes(
    CRect& rectNewParentBarArea,
    UINT nSide = (UINT)-1,
    BOOL bExpand = FALSE,
    int nOffset = 0);
```

### <a name="parameters"></a>Параметры

[in] *rectNewParentBarArea*<br/>

[in] *nSide*<br/>

[in] *bExpand*<br/>

[in] *nOffset*<br/>

### <a name="remarks"></a>Примечания

##  <a name="resize"></a>  CDockingPanesRow::Resize

```
virtual int Resize(int nOffset);
```

### <a name="parameters"></a>Параметры

[in] *nOffset*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="resizebypanedivider"></a>  CDockingPanesRow::ResizeByPaneDivider

```
virtual int ResizeByPaneDivider(int /*ignored*/);
```

### <a name="parameters"></a>Параметры

[in] *игнорируется*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="screentoclient"></a>  CDockingPanesRow::ScreenToClient

```
void ScreenToClient(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setextra"></a>  CDockingPanesRow::SetExtra

```
void SetExtra(
    int nExtraSpace,
    AFX_ROW_ALIGNMENT rowExtraAlign);
```

### <a name="parameters"></a>Параметры

[in] *nExtraSpace*<br/>

[in] *rowExtraAlign*<br/>

### <a name="remarks"></a>Примечания

##  <a name="showdocksiterow"></a>  CDockingPanesRow::ShowDockSiteRow

```
virtual void ShowDockSiteRow(
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Параметры

[in] *bShow*<br/>

[in] *bDelay*<br/>

### <a name="remarks"></a>Примечания

##  <a name="showpane"></a>  CDockingPanesRow::ShowPane

```
virtual BOOL ShowPane(
    CPane* pControlBar,
    BOOL bShow,
    BOOL bDelay = FALSE);
```

### <a name="parameters"></a>Параметры

[in] *pControlBar*<br/>

[in] *bShow*<br/>

[in] *bDelay*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="updatevisiblestate"></a>  CDockingPanesRow::UpdateVisibleState

```
virtual void UpdateVisibleState(BOOL bDelay);
```

### <a name="parameters"></a>Параметры

[in] *bDelay*<br/>

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Класс CDockSite](../../mfc/reference/cdocksite-class.md)<br/>
[Класс CPane](../../mfc/reference/cpane-class.md)
