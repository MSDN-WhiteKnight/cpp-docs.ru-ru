---
title: "Класс remove_extent | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::remove_extent
dev_langs: C++
helpviewer_keywords:
- remove_extent class
- remove_extent
ms.assetid: b9320862-3891-49fc-80bc-571eb2c035cf
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fe46bfa09b7b1c9ae47702a729b0f64723aa6c12
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="removeextent-class"></a>Класс remove_extent
Создает тип элемента из типа массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class T>  
struct remove_extent;  
 
template <class T>  
using remove_extent_t = typename remove_extent<T>::type;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип для изменения.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр `remove_extent<T>` содержит измененный тип, т. е. `T1`, если `T` имеет форму `T1[N]`; в противном случае — `T`.  
  
## <a name="example"></a>Пример  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "remove_extent_t<int> == "  
        << typeid(std::remove_extent_t<int>).name()  
        << std::endl;T  
    std::cout << "remove_extent_t<int[5]> == "  
        << typeid(std::remove_extent_t<int[5]>).name()  
        << std::endl;T  
    std::cout << "remove_extent_t<int[5][10]> == "  
        << typeid(std::remove_extent_t<int[5][10]>).name()  
        << std::endl;   
    return (0);   
    }  
```  
  
```Output  
remove_extent_t<int> == int  
remove_extent_t<int[5]> == int  
remove_extent_t<int[5][10]> == int [10]  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)   
 [Класс remove_all_extents](../standard-library/remove-all-extents-class.md)