---
title: __shiftright128
ms.date: 11/04/2016
f1_keywords:
- __shiftright128
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
ms.openlocfilehash: 8c35625efa9ddc4cf5de3900c6e3e37047b2aa10
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51332157"
---
# <a name="shiftright128"></a>__shiftright128

**Блок, относящийся только к системам Microsoft**

Сдвигает 128-разрядную величину, представленную в виде двух 64-разрядныхвеличин `HighPart``LowPart`и , `Shift` вправо на количество разрядов, указанное в  и возвращает младшие 64 разряда результата.

## <a name="syntax"></a>Синтаксис

```
unsigned __int64 __shiftright128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

#### <a name="parameters"></a>Параметры

*Значение подверсии*<br/>
[in] Младшие 64 разряда 128-разрядной величины для сдвига.

*HighPart*<br/>
[in] Старшие 64 разряда 128-разрядной величины для сдвига.

*SHIFT*<br/>
[in] Количество битов для сдвига.

## <a name="return-value"></a>Возвращаемое значение

Младшие 64 разряда результата.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__shiftright128`|X64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Это значение `Shift` всегда берется по модулю 64, и, например, при вызове `__shiftright128(0, 1, 64)`, функция будет сдвигать вправо старшую часть `0` разрядов и возвращать младшую часть `0`, а не `1`, как в противном случае можно было ожидать.

## <a name="example"></a>Пример

Например, см. в разделе [__shiftleft128](../intrinsics/shiftleft128.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__shiftleft128](../intrinsics/shiftleft128.md)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)