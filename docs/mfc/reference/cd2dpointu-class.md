---
title: Класс CD2DPointU
ms.date: 11/04/2016
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
ms.openlocfilehash: d66793abbb83015891df348eef8384e5c97baf2c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281126"
---
# <a name="cd2dpointu-class"></a>Класс CD2DPointU

Программа-оболочка для `D2D1_POINT_2U`.

## <a name="syntax"></a>Синтаксис

```
class CD2DPointU : public D2D1_POINT_2U;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CD2DPointU::CD2DPointU](#cd2dpointu)|Перегружен. Создает `CD2DPointU` из объекта `D2D1_POINT_2U` объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[CD2DPointU::operator CPoint](#operator_cpoint)|Преобразует `CD2DPointU` для `CPoint` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="cd2dpointu"></a>  CD2DPointU::CD2DPointU

Создает объект CD2DPointU из CPoint объекта.

```
CD2DPointU(const CPoint& pt);
CD2DPointU(const D2D1_POINT_2U& pt);
  CD2DPointU(const D2D1_POINT_2U* pt);
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```

### <a name="parameters"></a>Параметры

*pt*<br/>
Исходная точка

*uX*<br/>
Источник X

*uY*<br/>
Источник Y

##  <a name="operator_cpoint"></a>  CD2DPointU::operator CPoint

Преобразует CD2DPointU CPoint.

```
operator CPoint();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение точки D2D.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
