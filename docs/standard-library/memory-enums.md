---
title: Перечисления &lt;memory&gt;
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 5c5f87905b772ef277a72ef11defef8cb1001661
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495008"
---
# <a name="ltmemorygt-enums"></a>Перечисления &lt;memory&gt;

||
|-|
|[pointer_safety](#pointer_safety)|

## <a name="pointer_safety"></a>  Перечисление pointer_safety

Перечисление возможных значений, возвращаемых `get_pointer_safety`.

class pointer_safety { relaxed, preferred, strict };

### <a name="remarks"></a>Примечания

Ограниченную **перечисления** определяет значения, которые могут быть возвращены `get_pointer_safety()`:

`relaxed` — указатели, наследованные небезопасно (указатели на объявленные объекты или объекты, для которых выделена память), обрабатываются так же, как наследованные безопасно.

`preferred` — как и раньше, но указатели, наследованные небезопасно, не должны разыменовываться.

`strict` — указатели, наследованные небезопасно, могут обрабатываться не так, как наследованные безопасно.

## <a name="see-also"></a>См. также

[\<memory>](../standard-library/memory.md)<br/>
