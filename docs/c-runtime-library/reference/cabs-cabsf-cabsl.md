---
title: cabs, cabsf, cabsl
ms.date: 11/04/2016
apiname:
- cabs
- cabsf
- cabsl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- cabs
- cabsf
- cabsl
- complex/cabs
- complex/cabsf
- complex/cabsl
helpviewer_keywords:
- cabs function
- cabsf function
- cabsl function
ms.assetid: 6b8eb453-cc8f-4972-bebf-351cbdfdfc15
ms.openlocfilehash: cfa437a5d248a83568032d4c9ef8d4f938074dfe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623969"
---
# <a name="cabs-cabsf-cabsl"></a>cabs, cabsf, cabsl

Извлекает абсолютное значение комплексного числа.

## <a name="syntax"></a>Синтаксис

```C
double cabs(
   _Dcomplex z
);
float cabs(
   _Fcomplex z
);  // C++ only
long double cabs(
   _Lcomplex z
);  // C++ only
float cabsf(
   _Fcomplex z
);
long double cabsl(
   _Lcomplex z
);
```

### <a name="parameters"></a>Параметры

*z*<br/>
Комплексное число.

## <a name="return-value"></a>Возвращаемое значение

Абсолютное значение *z*.

## <a name="remarks"></a>Примечания

Так как C++ допускает перегрузку, можно вызывать перегрузки **cabs** , принимающих **_Fcomplex** или **_Lcomplex** и возвращают **float** или **long** **двойные** значения. В программе на языке C **cabs** всегда принимает **_Dcomplex** значения и возвращает **двойные** значение.

## <a name="requirements"></a>Требования

|Подпрограмма|Заголовок C|Заголовок C++|
|-------------|--------------|------------------|
|**cabs**, **cabsf**, **cabsl**|\<complex.h>|\<ccomplex>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
