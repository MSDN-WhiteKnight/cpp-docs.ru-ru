---
title: Класс CInvalidArgException
ms.date: 11/04/2016
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
ms.openlocfilehash: d2df9b482fe95ad0a13a85a51037a4cbbc28d057
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260196"
---
# <a name="cinvalidargexception-class"></a>Класс CInvalidArgException

Этот класс представляет условие исключения, связанного с недопустимым аргументом.

## <a name="syntax"></a>Синтаксис

```
class CInvalidArgException : public CSimpleException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CInvalidArgException::CInvalidArgException](#cinvalidargexception)|Конструктор.|

## <a name="remarks"></a>Примечания

Объект `CInvalidArgException` объект представляет условие исключения недопустимого аргумента.

Дополнительные сведения об обработке исключений см. в разделе [класса CException](../../mfc/reference/cexception-class.md) раздела и [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CInvalidArgException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="cinvalidargexception"></a>  CInvalidArgException::CInvalidArgException

Конструктор.

```
CInvalidArgException();
```

### <a name="remarks"></a>Примечания

Не используйте этот конструктор напрямую. Вызовите глобальную функцию **AfxThrowInvalidArgException**.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CSimpleException](../../mfc/reference/csimpleexception-class.md)
