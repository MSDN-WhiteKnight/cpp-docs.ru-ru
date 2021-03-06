---
title: __vmx_vmptrld
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmptrld
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
ms.openlocfilehash: 4f74a69bf0a4a780834dc9669c1266c82f7038e6
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51325928"
---
# <a name="vmxvmptrld"></a>__vmx_vmptrld

**Блок, относящийся только к системам Microsoft**

Загружает указатель на текущую структуру управления виртуальной машины (VMCS) из указанного адреса.

## <a name="syntax"></a>Синтаксис

```
int __vmx_vmptrld(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Параметры

*VmcsPhysicalAddress*<br/>
[in] Адрес, где хранится указатель VMCS.

## <a name="return-value"></a>Возвращаемое значение

0<br/>
Операция успешно выполнена.

1<br/>
Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.

2<br/>
Сбой операции без сведений о состоянии.

## <a name="remarks"></a>Примечания

Указатель VMCS — это 64-разрядный физический адрес.

Функция `__vmx_vmptrld` эквивалентна инструкции компьютера `VMPTRLD` . Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения в документе «Intel Virtualization технические спецификации для архитектуры IA-32 Intel,» номер документа C97063-002, на [корпорации Intel](https://software.intel.com/articles/intel-sdm) сайта.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__vmx_vmptrld`|X64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)