---
title: регистр (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.case
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
ms.openlocfilehash: 1ed107b78ea5638d93a773e19de13b4c1fe1036c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648413"
---
# <a name="case-c"></a>case (C++)

Используется с [switch_type](switch-type.md) атрибут в **объединение**.

## <a name="syntax"></a>Синтаксис

```cpp
[ case(value) ]
```

#### <a name="parameters"></a>Параметры

*значение*<br/>
Возможное значение ввода, для которого вы хотите предоставить обработки. Тип **значение** может принимать одно из следующих типов:

- `int`

- `char`

- `boolean`

- `enum`

или идентификатор такого типа.

## <a name="remarks"></a>Примечания

**Случай** атрибут C++ имеет ту же функциональность, что **случай** описании атрибута MIDL. Этот атрибут используется только с [switch_type](switch-type.md) атрибута.

## <a name="example"></a>Пример

В следующем коде показано использование **случай** атрибут:

```cpp
// cpp_attr_ref_case.cpp
// compile with: /LD
#include <unknwn.h>
[export]
struct SizedValue2 {
   [switch_type(char), switch_is(kind)] union {
      [case(1), string]
          wchar_t* wval;
      [default, string]
          char* val;
   };
    char kind;
};
[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Член **класс** или **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)