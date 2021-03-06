---
title: fegetexceptflag
ms.date: 04/05/2018
apiname:
- fegetexceptflag
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fegetexceptflag
- fenv/fegetexceptflag
helpviewer_keywords:
- fegetexceptflag function
ms.assetid: 2d28f0ca-70c9-4cff-be8b-3d876eacde71
ms.openlocfilehash: 43259001bd05bb7df9e2e1636c174018dcdaef3c
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522653"
---
# <a name="fegetexceptflag"></a>fegetexceptflag

Сохраняет текущее состояние указанных флагов исключений с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
int fegetexceptflag(
   fexcept_t* pstatus,
   int excepts
);
```

### <a name="parameters"></a>Параметры

*pstatus*<br/>
Указатель на **fexcept_t** объект, содержащий текущие значения флагов исключений, указанных по *кроме*.

*Кроме*<br/>
Флаги исключений с плавающей запятой для хранения в *pstatus*.

## <a name="return-value"></a>Возвращаемое значение

При успешном выполнении возвращается 0. В противном случае возвращается ненулевое значение.

## <a name="remarks"></a>Примечания

**Fegetexceptflag** функция сохраняет текущее состояние флагов состояния исключения с плавающей запятой, заданные *кроме* в **fexcept_t** объекта, на который указывает *pstatus*.  *pstatus* должен указывать на допустимый **fexcept_t** объекта или последующее поведение не определено. **Fegetexceptflag** функция поддерживает макросы исключений, определенные в \<fenv.h >:

|Макрос исключения|Описание|
|---------------------|-----------------|
|FE_DIVBYZERO|При выполнении предыдущей операции с плавающей запятой произошла ошибка сингулярности или полюса, в результате чего было получено бесконечное значение.|
|FE_INEXACT|Функция принудительно округлила сохраненный результат ранее выполненной операции с плавающей запятой.|
|FE_INVALID|Ошибка домена в ранее выполненной операции с плавающей запятой.|
|FE_OVERFLOW|Ошибка диапазона. Ранее выполненная операция с плавающей запятой возвратила слишком большое значение, которое не удается представить.|
|FE_UNDERFLOW|Ранее выполненная операция с плавающей запятой возвратила слишком малое значение, которое не удается представить с полной точностью. Создано денормализованное значение.|
|FE_ALLEXCEPT|Побитовая операция ИЛИ для всех поддерживаемых исключений с плавающей запятой.|

*Кроме* аргумент может иметь ноль, один макросы поддерживаемых исключений с плавающей запятой, а также побитовой операции или двух или нескольких макросов. Действие любого другого значения аргумента не определено.

Чтобы использовать эту функцию, необходимо отключить оптимизацию вычислений с плавающей запятой, которая может препятствовать доступу. Для этого следует использовать директиву `#pragma fenv_access(on)` перед вызовом. Дополнительные сведения см. в разделе [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Требования

|Функция|Заголовок C|Заголовок C++|
|--------------|--------------|------------------|
|**fegetexceptflag**|\<fenv.h>|\<cfenv>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
