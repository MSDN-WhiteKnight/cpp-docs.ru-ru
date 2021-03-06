---
title: Класс pointer_to_binary_function
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_binary
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
ms.openlocfilehash: 88d38be258c6ceb1054e0d31cc52e4d8d25186ec
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006803"
---
# <a name="pointertobinaryfunction-class"></a>Класс pointer_to_binary_function

Преобразует указатель на бинарную функцию в адаптируемую бинарную функцию. Рекомендуется использовать в C ++ 11, удалено в C ++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
public:
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```

### <a name="parameters"></a>Параметры

*pfunc*<br/>
Бинарная функция для преобразования.

*left*<br/>
Левый объект, для которого вызывается функция *\*pfunc*.

*right*<br/>
Правый объект, для которого вызывается функция *\*pfunc*.

## <a name="return-value"></a>Возвращаемое значение

Класс шаблона сохраняет копию `pfunc`. Он определяет свою функцию-член `operator()` как возвращающий `(* pfunc)(Left, right)`.

## <a name="remarks"></a>Примечания

Указатель на бинарную функцию является объектом функции и может передаваться в любой алгоритм стандартной библиотеки C++, ожидающий бинарную функцию в качестве параметра, но не может настраиваться. Для использования его с адаптером, например привязка к нему значения или использование его с negator, он должен передаваться с вложенными типами `first_argument_type`, `second_argument_type`, и `result_type` , делает такую возможных. Преобразование посредством `pointer_to_binary_function` позволяет адаптерам функций работать с указателями бинарных функций.

## <a name="example"></a>Пример

Конструктор `pointer_to_binary_function` редко используется напрямую. См. раздел по вспомогательной функции [ptr_fun](../standard-library/functional-functions.md#ptr_fun) с примером того, как объявлять и использовать предикат адаптера `pointer_to_binary_function`.

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
