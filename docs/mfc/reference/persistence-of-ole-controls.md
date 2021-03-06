---
title: Сохраняемость элементов управления OLE
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.ole
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
ms.openlocfilehash: b8bcba63c8e09873fe7f30e4fd07d652850be1f3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299651"
---
# <a name="persistence-of-ole-controls"></a>Сохраняемость элементов управления OLE

Одна из возможностей элементов управления OLE является свойством сохраняемости (или сериализации), который позволяет элементу управления OLE для чтения или записи значения свойств в и из файла или потока. Приложения-контейнера можно использовать сериализацию для хранения значений свойств элемента управления, даже в том случае, если приложение уничтожила элемента управления. Значения свойств элемента управления OLE могут считываться из файла или потока при создании нового экземпляра элемента управления создается в дальнейшем.

### <a name="persistence-of-ole-controls"></a>Сохраняемость элементов управления OLE

|||
|-|-|
|[PX_Blob](#px_blob)|Меняет местами свойства элемента управления, в котором хранятся данные больших двоичных объектов (BLOB).|
|[PX_Bool](#px_bool)|Меняет местами свойства элемента управления типа **BOOL**.|
|[PX_Color](#px_color)|Меняет местами свойство цвета элемента управления.|
|[PX_Currency](#px_currency)|Меняет местами свойства элемента управления типа **CY**.|
|[PX_DataPath](#px_datapath)|Меняет местами свойства элемента управления типа `CDataPathProperty`.|
|[PX_Double](#px_double)|Меняет местами свойства элемента управления типа **двойные**.|
|[PX_Font](#px_font)|Меняет местами свойства шрифта элемента управления.|
|[PX_Float](#px_float)|Меняет местами свойства элемента управления типа **float**.|
|[PX_IUnknown](#px_iunknown)|Меняет местами неопределенного типа свойства элемента управления.|
|[PX_Long](#px_long)|Меняет местами свойства элемента управления типа **long**.|
|[PX_Picture](#px_picture)|Меняет местами свойства изображения элемента управления.|
|[PX_Short](#px_short)|Меняет местами свойства элемента управления типа **короткие**.|
|[PX_ULong](#px_ulong)|Меняет местами свойства элемента управления типа **ULONG**.|
|[PX_UShort](#px_ushort)|Меняет местами свойства элемента управления типа **USHORT**.|
|[PXstring](#px_string)|Меняет местами символ строковое свойство элемента управления.|
|[PX_VBXFontConvert](#px_vbxfontconvert)|Меняет местами свойства, связанные со шрифтами VBX элемента управления в свойстве шрифта элемента управления OLE.|

Кроме того `AfxOleTypeMatchGuid` глобальной функции предоставляется для проверки на соответствие между TYPEDESC и заданного GUID.

##  <a name="px_blob"></a>  PX_Blob

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойство, которое сохраняет данные больших двоичных объектов (BLOB).

```
BOOL PX_Blob(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    HGLOBAL& hBlob,
    HGLOBAL hBlobDefault = NULL);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*hBlob*<br/>
Ссылка на переменную, в котором хранится свойство (обычно переменную-член класса).

*hBlobDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства будет считывать или записью в переменную ссылается *hBlob*, соответствующим образом. Эта переменная должна инициализироваться в NULL перед вызовом изначально `PX_Blob` в первый раз (как правило, это можно сделать в конструкторе элемента управления). Если *hBlobDefault* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса инициализации или сериализации элемента управления.

Маркеры *hBlob* и *hBlobDefault* ссылаться на блок памяти, который содержит следующее:

- Значение типа DWORD, которая содержит длину в байтах, двоичных данных ниже, а затем сразу же

- Блок памяти, содержащей сами двоичные данные.

Обратите внимание, что `PX_Blob` будет выделять память, с помощью Windows [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) API, при загрузке свойств тип большого двоичного ОБЪЕКТА. Вы несете ответственность за освобождение этой памяти. Таким образом, деструктор класса элемента управления должны вызывать [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree) любому свойству типа BLOB дескрипторы для освобождения вверх память, выделенную в элемент управления.

##  <a name="px_bool"></a>  PX_Bool

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойство типа BOOL.

```
BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue);

BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue,
    BOOL bDefault);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*bValue*<br/>
Ссылка на переменную, в котором хранится свойство (обычно переменную-член класса).

*bПо умолчанию*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства будет считывать или записью в переменную ссылается *bValue*, соответствующим образом. Если *bПо умолчанию* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса сериализации элемента управления.

##  <a name="px_color"></a>  PX_Color

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойство типа OLE_COLOR.

```
BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue,
    OLE_COLOR clrDefault);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*clrValue*<br/>
Ссылка на переменную, в котором хранится свойство (обычно переменную-член класса).

*clrDefault*<br/>
Значение по умолчанию для свойства, определяемые разработчиком элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства будет считывать или записью в переменную ссылается *clrValue*, соответствующим образом. Если *clrDefault* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса сериализации элемента управления.

##  <a name="px_currency"></a>  PX_Currency

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойство типа **валюты**.

```
BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue);

BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue,
    CY cyDefault);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*cyValue*<br/>
Ссылка на переменную, в котором хранится свойство (обычно переменную-член класса).

*cyDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства будет считывать или записью в переменную ссылается *cyValue*, соответствующим образом. Если *cyDefault* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса сериализации элемента управления.

##  <a name="px_datapath"></a>  PX_DataPath

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойство пути данных типа [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md).

```
BOOL PX_DataPath(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CDataPathProperty& dataPathProperty);

BOOL PX_DataPath(
    CPropExchange* pPX,
    CDataPathProperty& dataPathProperty);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*dataPathProperty*<br/>
Ссылка на переменную, в котором хранится свойство (обычно переменную-член класса).

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Свойства пути данных реализовать асинхронный элемент управления свойства. Значение свойства будет считывать или записью в переменную ссылается *dataPathProperty*, соответствующим образом.

##  <a name="px_double"></a>  PX_Double

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойство типа **двойные**.

```
BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue);

BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue,
    double doubleDefault);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*doubleValue*<br/>
Ссылка на переменную, в котором хранится свойство (обычно переменную-член класса).

*doubleDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства является чтения или записи в переменную ссылается *doubleValue*, соответствующим образом. Если *doubleDefault* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса сериализации элемента управления.

##  <a name="px_font"></a>  PX_Font

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойство тип шрифта.

```
BOOL PX_Font(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC FAR* pFontDesc = NULL,
    LPFONTDISP pFontDispAmbient = NULL);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*шрифт*<br/>
Ссылку на `CFontHolder` , содержащий свойства шрифта.

*pFontDesc*<br/>
Указатель на `FONTDESC` структуру, содержащую значения, используемые при инициализации состояние по умолчанию свойства шрифта, в случае, когда *pFontDispAmbient* имеет значение NULL.

*pFontDispAmbient*<br/>
Указатель на `IFontDisp` интерфейс шрифта для использования в инициализации состояния по умолчанию свойства шрифта.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства является чтения или записи к `font`, `CFontHolder` ссылки, при необходимости. Если *pFontDesc* и *pFontDispAmbient* указаны, они используются для инициализации значения этого свойства по умолчанию, при необходимости. Эти значения используются в том случае, если по какой-либо причине происходит сбой процесса сериализации элемента управления. Как правило, можно передать NULL в качестве *pFontDesc* и внешнее значение, возвращенное `COleControl::AmbientFont` для *pFontDispAmbient*. Обратите внимание, что возвращаемый объект шрифта `COleControl::AmbientFont` должен освобождаться с помощью вызова `IFontDisp::Release` функция-член.

##  <a name="px_float"></a>  PX_Float

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойство типа **float**.

```
BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue);

BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue,
    float floatDefault);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*floatValue*<br/>
Ссылка на переменную, в котором хранится свойство (обычно переменную-член класса).

*floatDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства является чтения или записи в переменную ссылается *floatValue*, соответствующим образом. Если *floatDefault* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса сериализации элемента управления.

##  <a name="px_iunknown"></a>  PX_IUnknown

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойство, представленное объектом с `IUnknown`-производным интерфейсом.

```
BOOL PX_IUnknown(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    LPUNKNOWN& pUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault = NULL);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*pUnk*<br/>
Ссылка на переменную, содержащую интерфейс объекта, который представляет значение свойства.

*IID*<br/>
Идентификатор интерфейса, указывающий, какой интерфейс объект свойства, используемые элементом управления.

*pUnkDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства является чтения или записи в переменную ссылается *pUnk*, соответствующим образом. Если *pUnkDefault* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса сериализации элемента управления.

##  <a name="px_long"></a>  PX_Long

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойство типа **long**.

```
BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue);

BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue,
    long lDefault);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*lValue*<br/>
Ссылка на переменную, в котором хранится свойство (обычно переменную-член класса).

*lDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства является чтения или записи в переменную ссылается *lValue*, соответствующим образом. Если *lDefault* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса сериализации элемента управления.

##  <a name="px_picture"></a>  PX_Picture

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойства изображения элемента управления.

```
BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict);

BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict,
    CPictureHolder& pictDefault);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*PICT*<br/>
Ссылка на [CPictureHolder](../../mfc/reference/cpictureholder-class.md) объекта, где хранится свойство (обычно переменную-член класса).

*pictDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства является чтения или записи в переменную ссылается *pict*, соответствующим образом. Если *pictDefault* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса сериализации элемента управления.

##  <a name="px_short"></a>  PX_Short

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойство типа **короткие**.

```
BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue);

BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue,
    short sDefault);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*sValue*<br/>
Ссылка на переменную, в котором хранится свойство (обычно переменную-член класса).

*sDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства является чтения или записи в переменную ссылается *sValue*, соответствующим образом. Если *sDefault* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса сериализации элемента управления.

##  <a name="px_ulong"></a>  PX_ULong

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойство типа **ULONG**.

```
BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue);

BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue,
    long ulDefault);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*ulValue*<br/>
Ссылка на переменную, в котором хранится свойство (обычно переменную-член класса).

*ulDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства является чтения или записи в переменную ссылается *ulValue*, соответствующим образом. Если *ulDefault* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса сериализации элемента управления.

##  <a name="px_ushort"></a>  PX_UShort

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойство типа **unsigned short**.

```
BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue);

BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue,
    USHORT usDefault);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*usValue*<br/>
Ссылка на переменную, в котором хранится свойство (обычно переменную-член класса).

*usDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства является чтения или записи в переменную ссылается *usValue*, соответствующим образом. Если *usDefault* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса сериализации элемента управления.

##  <a name="px_string"></a>  PXstring

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для сериализации или инициализировать свойства строки символов.

```
BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue);

BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue,
    CString strDefault);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*pszPropName*<br/>
Имя свойства при обмене.

*strValue*<br/>
Ссылка на переменную, в котором хранится свойство (обычно переменную-член класса).

*strDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Значение свойства является чтения или записи в переменную ссылается *strValue*, соответствующим образом. Если *strDefault* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой процесса сериализации элемента управления.

##  <a name="px_vbxfontconvert"></a>  PX_VBXFontConvert

Вызывайте эту функцию в пределах элемента управления `DoPropExchange` функция-член для инициализации свойства шрифта путем преобразования свойства, связанные со шрифтами VBX элемента управления.

```
BOOL PX_VBXFontConvert(
    CPropExchange* pPX,
    CFontHolder& font);
```

### <a name="parameters"></a>Параметры

*pPX*<br/>
Указатель на [CPropExchange](../../mfc/reference/cpropexchange-class.md) объекта (обычно передается в качестве параметра `DoPropExchange`).

*шрифт*<br/>
Свойства шрифта элемента управления OLE, который будет содержать преобразованные свойства VBX связанные со шрифтами.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Эта функция должна использоваться только с элементом управления OLE, который разработан как прямой заменой для элемента управления VBX. Если среда разработки Visual Basic преобразует форму, содержащую элемент управления VBX для использования соответствующего замена элемента управления OLE, он вызывает элемент управления `IDataObject::SetData` функцию, передавая набор свойств, содержащий данные свойства VBX элемента управления. Эта операция, в свою очередь, вызывает элемент управления `DoPropExchange` вызываемая функция. `DoPropExchange` можно вызвать `PX_VBXFontConvert` для преобразования свойства, связанные со шрифтами VBX элемента управления (например, «FontName,» «FontSize,» и т. д) в соответствующих компонентов свойства шрифта элемента управления OLE.

`PX_VBXFontConvert` должен вызываться только когда элемент управления фактически преобразуется из VBX формы приложения. Пример:

[!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
