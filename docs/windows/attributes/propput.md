---
title: propput (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propput
helpviewer_keywords:
- propput attribute
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
ms.openlocfilehash: 1902ba61417be457b4c296b513e1632bfdd8cec6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492733"
---
# <a name="propput"></a>propput

Задает функцию настройки свойства.

## <a name="syntax"></a>Синтаксис

```cpp
[propput]
```

## <a name="remarks"></a>Примечания

**Propput** атрибут C++ имеет ту же функциональность, что [propput](/windows/desktop/Midl/propput) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [bindable](bindable.md) использовать образец **propput**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|`propget`, `propputref`|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propputref](propputref.md)