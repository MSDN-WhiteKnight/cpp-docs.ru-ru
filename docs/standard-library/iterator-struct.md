---
title: Структура iterator
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
ms.openlocfilehash: 1dd62a6141e690d3bd4dcad69aa107c126a0f386
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631404"
---
# <a name="iterator-struct"></a>Структура iterator

Пустая базовая структура позволяет убедиться в правильной работе класс пользовательской итератора с `iterator_trait`s.

## <a name="syntax"></a>Синтаксис

```cpp
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };
```

## <a name="remarks"></a>Примечания

Данная структура-шаблон используется как базовый тип для всех итераторов. Она определяет типы членов

- `iterator_category` (синоним для параметра-шаблона `Category`).

- `value_type` (синоним для параметра-шаблона `Type`).

- `difference_type` (синоним для параметра-шаблона `Distance`).

- `distance_type` (синоним для параметра-шаблона `Distance`)

- `pointer` (синоним для параметра-шаблона `Pointer`).

- `reference` (синоним для параметра-шаблона `Reference`).

Обратите внимание, что `value_type` не должны даже если тип константы `pointer` указывает на объект из **const** `Type` и ссылка обозначает объект **const** `Type`.

## <a name="example"></a>Пример

См. раздел [iterator_traits](../standard-library/iterator-traits-struct.md) с примером того, как объявить и использовать типы в базовом классе итератора.

## <a name="requirements"></a>Требования

**Заголовок:** \<iterator>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<iterator>](../standard-library/iterator.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
