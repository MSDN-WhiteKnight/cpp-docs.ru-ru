---
title: Класс CMemoryException
ms.date: 11/04/2016
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
ms.openlocfilehash: 11be0eba080085c507ed718ea23219ca1c93aeba
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294750"
---
# <a name="cmemoryexception-class"></a>Класс CMemoryException

Представляет условие исключения вне памяти.

## <a name="syntax"></a>Синтаксис

```
class CMemoryException : public CSimpleException
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMemoryException::CMemoryException](#cmemoryexception)|Создает объект `CMemoryException`.|

## <a name="remarks"></a>Примечания

Без дальнейшего уточнения невозможна и не требуется. Автоматически возникают исключения памяти **новый**. Если вы пишете собственные функции памяти, с помощью `malloc`, для примера, то вы несете ответственность за создание исключений в памяти.

Дополнительные сведения о `CMemoryException`, см. в статье [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CMemoryException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="cmemoryexception"></a>  CMemoryException::CMemoryException

Создает объект `CMemoryException`.

```
CMemoryException();
```

### <a name="remarks"></a>Примечания

Не используйте этот конструктор напрямую, но вместо этого вызовите глобальную функцию [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). этой глобальной функции может быть успешным в ситуации out of memory, так как он создает объект исключения из ранее выделенной памяти. Дополнительные сведения об обработке исключений см. в статье [исключения](../exception-handling-in-mfc.md).

## <a name="see-also"></a>См. также

[Класс CException](cexception-class.md)<br/>
[Диаграмма иерархии](../hierarchy-chart.md)
