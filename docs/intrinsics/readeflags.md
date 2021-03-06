---
title: __readeflags
ms.date: 11/04/2016
f1_keywords:
- __readeflags
helpviewer_keywords:
- __readeflags intrinsic
ms.assetid: f9d2f4d8-c428-491f-b8de-04d0566b2b6b
ms.openlocfilehash: e5294180904d0d7ca3bbd1de75e45e058a33c88f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594276"
---
# <a name="readeflags"></a>__readeflags

Считывает состояние программы и управления (EFLAGS) регистров.

## <a name="syntax"></a>Синтаксис

```
unsigned     int __readeflags(void);
unsigned __int64 __readeflags(void);
```

## <a name="return-value"></a>Возвращаемое значение

Значение регистра EFLAGS. Возвращаемое значение — 32 бита, много времени, на 32-разрядной платформе и 64 бита много времени, на 64-разрядной платформе.

## <a name="remarks"></a>Примечания

Эти процедуры доступны только как встроенные функции.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__readeflags`|x86, x64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__writeeflags](../intrinsics/writeeflags.md)