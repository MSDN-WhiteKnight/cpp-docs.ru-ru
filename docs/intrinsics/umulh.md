---
title: __umulh
ms.date: 11/04/2016
f1_keywords:
- __umulh
helpviewer_keywords:
- __umulh intrinsic
ms.assetid: d241b53a-e6f7-4af1-9f6e-84e149158f03
ms.openlocfilehash: 6a0d427f32e275725177b10f01565e6947760f09
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328553"
---
# <a name="umulh"></a>__umulh

**Блок, относящийся только к системам Microsoft**

Вернуть старшие 64 разряда произведения двух 64-разрядных целых чисел без знака.

## <a name="syntax"></a>Синтаксис

```
unsigned __int64 __umulh(
   unsigned __int64 a,
   unsigned __int64 b
);
```

#### <a name="parameters"></a>Параметры

*a*<br/>
[in] Первое число для перемножения.

*b*<br/>
[in] Второе число для перемножения.

## <a name="return-value"></a>Возвращаемое значение

Старшие 64 разряда 128-разрядного результата умножения.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__umulh`|X64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эти процедуры доступны только как встроенные объекты.

## <a name="example"></a>Пример

```
// umulh.cpp
// processor: X64
#include <cstdio>
#include <intrin.h>

int main()
{
    unsigned __int64 i = 0x10;
    unsigned __int64 j = 0xFEDCBA9876543210;
    unsigned __int64 k = i * j; // k has the low 64 bits
                                // of the product.
    unsigned __int64 result;
    result = __umulh(i, j); // result has the high 64 bits
                            // of the product.
    printf_s("0x%I64x * 0x%I64x = 0x%I64x%I64x \n", i, j, result, k);
    return 0;
}
```

```Output
0x10 * 0xfedcba9876543210 = 0xfedcba98765432100
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)