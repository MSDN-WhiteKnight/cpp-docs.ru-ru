---
title: __svm_vmsave
ms.date: 11/04/2016
f1_keywords:
- __svm_vmsave
helpviewer_keywords:
- VMSAVE instruction
- __svm_vmsave intrinsic
ms.assetid: 617a60bd-8514-4ba1-8066-bcf4dd481030
ms.openlocfilehash: 2ffc68b13d09d15d90670fa135a2cac9d9a1d52f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556621"
---
# <a name="svmvmsave"></a>__svm_vmsave

**Блок, относящийся только к системам Microsoft**

Содержит набор состояния процессора в блок управления указанной виртуальной машины (VMCB).

## <a name="syntax"></a>Синтаксис

```
void __svm_vmsave(
   size_t VmcbPhysicalAddress
);
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*VmcbPhysicalAddress*|[in] Физический адрес VMCB.|

## <a name="remarks"></a>Примечания

Функция `__svm_vmsave` эквивалентна инструкции компьютера `VMSAVE` . Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в документе «архитектуре AMD64 для программистов вручную том 2: программирование,» номер документа 24593, редакция 3.11 и более поздних версиях в [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) сайта.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__svm_vmsave`|x86, x64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_vmrun](../intrinsics/svm-vmrun.md)<br/>
[__svm_vmload](../intrinsics/svm-vmload.md)