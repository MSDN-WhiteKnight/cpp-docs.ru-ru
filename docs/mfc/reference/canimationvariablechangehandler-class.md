---
title: Класс CAnimationVariableChangeHandler
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
ms.openlocfilehash: 92189ce5ea76811496d4462aa4254bbd03ebb219
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57257609"
---
# <a name="canimationvariablechangehandler-class"></a>Класс CAnimationVariableChangeHandler

Реализует обратный вызов, используемый API анимации при изменении значения переменной анимации.

## <a name="syntax"></a>Синтаксис

```
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|Создает объект `CAnimationVariableChangeHandler`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CreateInstance`|Создает экземпляр класса `CAnimationVariableChangeHandler` объекта.|
|[CAnimationVariableChangeHandler::OnValueChanged](#onvaluechanged)|Вызывается при изменении значения переменной анимации. (Переопределяет `CUIAnimationVariableChangeHandlerBase::OnValueChanged`.)|
|[CAnimationVariableChangeHandler::SetAnimationController](#setanimationcontroller)|Содержит указатель на контроллер анимации для маршрутизации события.|

## <a name="remarks"></a>Примечания

Этот обработчик событий создается и передается `IUIAnimationVariable::SetVariableChangeHandler` при вызове метода `CAnimationVariable::EnableValueChangedEvent` или `CAnimationBaseObject::EnableValueChangedEvent` (что позволяет это событие для всех переменных анимации, инкапсулированных в объект анимации).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CUIAnimationCallbackBase`

`CUIAnimationVariableChangeHandlerBase`

`CAnimationVariableChangeHandler`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="onvaluechanged"></a>  CAnimationVariableChangeHandler::OnValueChanged

Вызывается при изменении значения переменной анимации.

```
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```

### <a name="parameters"></a>Параметры

*раскадровки*<br/>
Раскадровки, который выполняет анимацию переменной.

*Переменная*<br/>
Переменная анимации, которая была обновлена.

*новое значение*<br/>
Новое значение.

*значение previousValue*<br/>
Предыдущее значение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращается значение S_OK. В противном случае он возвращает код ошибки HRESULT.

##  <a name="setanimationcontroller"></a>  CAnimationVariableChangeHandler::SetAnimationController

Содержит указатель на контроллер анимации для маршрутизации события.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Параметры

*pAnimationController*<br/>
Указатель на контроллер анимации, который будет получать события.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
