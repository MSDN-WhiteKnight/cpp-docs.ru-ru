---
title: Класс CD2DSizeU
ms.date: 11/04/2016
f1_keywords:
- CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::IsNull
helpviewer_keywords:
- CD2DSizeU [MFC], CD2DSizeU
- CD2DSizeU [MFC], IsNull
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
ms.openlocfilehash: f6b0bc12933100c6f2401f4f4cb9e1fae52dda65
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278656"
---
# <a name="cd2dsizeu-class"></a>Класс CD2DSizeU

Оболочка для D2D1_SIZE_U.

## <a name="syntax"></a>Синтаксис

```
class CD2DSizeU : public D2D1_SIZE_U;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DSizeU::CD2DSizeU](#cd2dsizeu)|Перегружен. Создает `CD2DSizeU` объекта из `D2D1_SIZE_U` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CD2DSizeU::IsNull](#isnull)|Возвращает **логическое** значение, указывающее, является ли выражение содержит недопустимые данные (NULL).|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CD2DSizeU::operator CSize](#operator_csize)|Преобразует `CD2DSizeU` для `CSize` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_SIZE_U`

[CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="cd2dsizeu"></a>  CD2DSizeU::CD2DSizeU

Создает объект CD2DSizeU из CSize объекта.

```
CD2DSizeU(const CSize& size);
CD2DSizeU(const D2D1_SIZE_U& size);
  CD2DSizeU(const D2D1_SIZE_U* size);

CD2DSizeU(
    UINT32 cx = 0,
    UINT32 cy = 0);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Размер источника

*cx*<br/>
исходная ширина

*CY*<br/>
Исходная высота

##  <a name="isnull"></a>  CD2DSizeU::IsNull

Возвращает логическое значение, указывающее, является ли выражение содержит недопустимые данные (Null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если ширина и высота являются пустыми; в противном случае — значение FALSE.

##  <a name="operator_csize"></a>  CD2DSizeU::operator CSize

Преобразует CD2DSizeU CSize.

```
operator CSize();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение размера D2D.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
