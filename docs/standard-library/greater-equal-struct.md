---
title: greater_equal - структура
ms.date: 11/04/2016
f1_keywords:
- functional/std::greater_equal
helpviewer_keywords:
- greater_equal struct
- greater_equal function
ms.assetid: a8ba911b-7af8-4653-b972-d8618f4df7d5
ms.openlocfilehash: 91d8265fa699bbaafe946c44a55dd63c13f44b42
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006504"
---
# <a name="greaterequal-struct"></a>greater_equal - структура

Бинарный предикат, который выполняет операцию больше или равен (`operator>=`) к своим аргументам.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type = void>
struct greater_equal : public binary_function <Type, Type, bool>
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator>=
template <>
struct greater_equal<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left)>= std::forward<U>(Right));
};
```

### <a name="parameters"></a>Параметры

*Тип*, *T*, *U* любой тип, поддерживающий `operator>=` , принимающий операнды указанного или выводимого типа.

*Слева*<br/>
Левый операнд в операции "больше или равно". Неспециализированный шаблон принимает ссылочный аргумент lvalue типа *тип*. Специализированный шаблон выполняет точную пересылку lvalue и rvalue ссылочных аргументов выводимого типа *T*.

*Справа*<br/>
Правый операнд в операции "больше или равно". Неспециализированный шаблон принимает ссылочный аргумент lvalue типа *тип*. Специализированный шаблон выполняет точную пересылку lvalue и rvalue ссылочных аргументов выводимого типа *U*.

## <a name="return-value"></a>Возвращаемое значение

Результат `Left >= Right`. Специализированный шаблон выполняет точную пересылку результата типа, возвращаемого `operator>=`.

## <a name="remarks"></a>Примечания

Бинарный предикат `greater_equal` <  `Type`> обеспечивает строгое слабое упорядочение набора значений элементов типа *тип* в классы эквивалентности только в том случае, если этот тип удовлетворяет стандартные математические требования для такого упорядочивания. Специализации для любого типа указателя дают общее упорядочение элементов в том, что все элементы из различных значений упорядочиваются относительно друг друга.

## <a name="example"></a>Пример

```cpp
// functional_greater_equal.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <cstdlib>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   v1.push_back( 6262 );
   v1.push_back( 6262 );
   for ( i = 0 ; i < 5 ; i++ )
   {
      v1.push_back( rand( ) );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use default binary predicate less<int>( )
   sort( v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order,
   // specify binary predicate greater_equal<int>( )
   sort( v1.begin( ), v1.end( ), greater_equal<int>( ) );
   cout << "Resorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = (6262 6262 41 18467 6334 26500 19169)
Sorted vector v1 = (41 6262 6262 6334 18467 19169 26500)
Resorted vector v1 = (26500 19169 18467 6334 6262 6262 41)
```

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
