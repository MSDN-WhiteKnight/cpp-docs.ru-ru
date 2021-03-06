---
title: Разрешение неоднозначных объявлений (C++)
ms.date: 11/04/2016
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
ms.openlocfilehash: 52e94f474d59505298cb4f78a477cedd21b90aad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507371"
---
# <a name="resolving-ambiguous-declarations-c"></a>Разрешение неоднозначных объявлений (C++)

Для выполнения явных преобразований из одного типа в другой необходимо использовать приведения, указывая имя требуемого типа. Некоторые приведения типов ведут к синтаксической неоднозначности. Следующее приведение типов в стиле функции неоднозначно.

```cpp
char *aName( String( s ) );
```

Неясно, является ли объявление функции или объявлением объекта с в стиле функции приводится к типу инициализатора: такой оператор может объявлять функцию, возвращающую тип `char *` , принимающий один аргумент типа `String`, или объявлять объект `aName` и инициализировать его со значением `s` приведенное к типу `String`.

Если объявление может считаться допустимым объявлением функции, оно считается таковым. Оператор проверяется на предмет того, представляет ли он приведение типов в стиле функции, только в том случае, если объявление не может считаться объявлением функции, т. е. оно синтаксически неверно. Поэтому компилятор считает данный оператор объявлением функции и игнорирует скобки вокруг идентификатора `s`. С другой стороны, операторы

```cpp
char *aName( (String)s );
```

и

```cpp
char *aName = String( s );
```

однозначно являются объявлениями объектов и определенного пользователем преобразования из типа `String` ввода `char *` вызывается для инициализации объекта `aName`.