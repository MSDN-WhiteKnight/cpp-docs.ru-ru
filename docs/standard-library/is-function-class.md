---
title: Класс is_function
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::is_function
helpviewer_keywords:
- is_function class
- is_function
ms.assetid: e5c0dbcd-829b-415f-853f-8c5be47c5040
ms.openlocfilehash: ea1f2ae025823a700ca4e91f3f6b3c05ed79e1cc
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006478"
---
# <a name="isfunction-class"></a>Класс is_function

Проверяет, является ли данный тип типом функции.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_function;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является типом функции, в противном случае он содержит значение false.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_function.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

struct functional
    {
    int f();
    };

int main()
    {
    std::cout << "is_function<trivial> == " << std::boolalpha
        << std::is_function<trivial>::value << std::endl;
    std::cout << "is_function<functional> == " << std::boolalpha
        << std::is_function<functional>::value << std::endl;
    std::cout << "is_function<float()> == " << std::boolalpha
        << std::is_function<float()>::value << std::endl;

    return (0);
    }
```

```Output
is_function<trivial> == false
is_function<functional> == false
is_function<float()> == true
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_object](../standard-library/is-object-class.md)<br/>
