---
title: immediatebind (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.immediatebind
helpviewer_keywords:
- immediatebind attribute
ms.assetid: 186d40e6-9166-4d0c-9853-4e7e4d25226f
ms.openlocfilehash: 35e8ea4a761fd3cf36da335dc8519ba71772b4e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647734"
---
# <a name="immediatebind"></a>immediatebind

Указывает, что базы данных будет немедленно оповещаться обо всех изменений свойства объекта привязки данных.

## <a name="syntax"></a>Синтаксис

```cpp
[immediatebind]
```

## <a name="remarks"></a>Примечания

**Immediatebind** атрибут C++ имеет ту же функциональность, что [immediatebind](/windows/desktop/Midl/immediatebind) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в разделе [bindable](bindable.md) пример демонстрирует использование **immediatebind**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[requestedit](requestedit.md)