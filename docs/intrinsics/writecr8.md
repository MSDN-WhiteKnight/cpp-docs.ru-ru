---
title: __writecr8
ms.date: 11/04/2016
f1_keywords:
- _writecr8
helpviewer_keywords:
- _writecr8 intrinsic
ms.assetid: 6f8bd632-dddb-4335-971e-1acee24aa2b9
ms.openlocfilehash: 1a7b31ed7e370c4dd3fee9e5a205be6e34ba560b
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51325788"
---
# <a name="writecr8"></a>__writecr8

**Блок, относящийся только к системам Microsoft**

Записывает значение `Data` CR8 регистр.

## <a name="syntax"></a>Синтаксис

```
void writecr8(
   unsigned __int64 Data
);
```

#### <a name="parameters"></a>Параметры

*Данные*<br/>
[in] Значение для записи в CR8 регистр.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__writecr8`|X64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта встроенная функция доступна только в режиме ядра и процедура доступна только как встроенная.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)