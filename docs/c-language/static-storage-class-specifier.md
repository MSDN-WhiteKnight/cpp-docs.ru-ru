---
title: Спецификатор класса хранения static
ms.date: 11/04/2016
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
ms.openlocfilehash: ef85ee4d757cb9579431427fba7b46a0e5ac905f
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56148235"
---
# <a name="static-storage-class-specifier"></a>Спецификатор класса хранения static

Переменная, объявленная на внутреннем уровне с помощью описателя класса хранения **static**, имеет глобальное время существования, но является видимой только внутри блока, в котором она объявлена. Описатель **static** полезно использовать константных строках, потому что при этом снимается нагрузка частой инициализации в часто вызываемых функциях.

## <a name="remarks"></a>Примечания

Если переменная **static** не инициализирована явно, она инициализируется значением 0 по умолчанию. Внутри функции **static** выделяет хранилище и служит определением. Внутренние статические переменные представляют закрытое постоянное хранилище, видимое только одной функции.

## <a name="see-also"></a>См. также

[Классы хранения в C](c-storage-classes.md)<br/>
[Storage classes (C++)](../cpp/storage-classes-cpp.md) (Классы хранения (C++))
