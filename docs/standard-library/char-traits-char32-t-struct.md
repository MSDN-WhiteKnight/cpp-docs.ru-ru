---
title: Структура char_traits&lt;char32_t&gt;
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::char_traits<char_32t>
- char_traits<char32_t>
helpviewer_keywords:
- char_traits<char32_t> class
ms.assetid: c0315466-45d0-4a99-b83e-3b1dbfbfbbc3
ms.openlocfilehash: 12fc36a9256a8a744e789fc95bb8603ee6cbf3d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581354"
---
# <a name="chartraitsltchar32tgt-struct"></a>Структура char_traits&lt;char32_t&gt;

Структура, которая является специализацией структуры шаблона **char_traits\<CharType>** к элементу типа `char32_t`.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
struct char_traits<char32_t>;
```

## <a name="remarks"></a>Примечания

Специализация позволяет структуре использовать преимущества функций библиотеки, которые управляют объектами данного типа `char32_t`.

## <a name="requirements"></a>Требования

**Заголовок:** \<string>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<string>](../standard-library/string.md)<br/>
[Структура char_traits](../standard-library/char-traits-struct.md)<br/>
