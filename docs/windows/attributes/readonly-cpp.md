---
title: только для чтения (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.readonly
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
ms.openlocfilehash: d174399b213bc6c8dbaeb0a01f3e457cfcf3a3e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653041"
---
# <a name="readonly-c"></a>readonly (C++)

Запрещает назначение элементу данных.

## <a name="syntax"></a>Синтаксис

```cpp
[readonly]
```

## <a name="remarks"></a>Примечания

Атрибут **readonly** языка C++ имеет ту же функциональность, что и атрибут [readonly](/windows/desktop/Midl/readonly) языка MIDL.

Если вы хотите запретить изменение параметра метода, используйте атрибут [in](in-cpp.md) .

## <a name="example"></a>Пример

В следующем коде показано использование атрибута **readonly** :

```cpp
// cpp_attr_ref_readonly.cpp
// compile with: /LD
[idl_quote("midl_pragma warning(disable:2461)")];
#include "unknwn.h"
[module(name="ATLFIRELib")];

[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]
__interface IFireTabCtrl
{
   [readonly, id(1)] int i();
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты элементов данных](data-member-attributes.md)