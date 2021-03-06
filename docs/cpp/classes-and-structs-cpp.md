---
title: Классы и структуры (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Visual C++, classes
- structures, C++ classes
- user-defined types
- classes [C++]
- user-defined types, C++ classes
ms.assetid: 516dd496-13fb-4f17-845a-e9ca45437873
ms.openlocfilehash: 44736b9515363d1406b124858f72f12f8f7f552a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562751"
---
# <a name="classes-and-structs-c"></a>Классы и структуры (C++)

В этом разделе приводится информация о классах и структурах C++. В C++ эти конструкции идентичны, за исключением того факта, что структуры по умолчанию открыты для доступа, а классы — закрыты.

Классы и структуры являются конструкциями, в которых пользователь определяет собственные типы. Классы и структуры могут включать данные-члены и функции-члены, позволяющие описывать состояние и поведение данного типа.

В раздел входят следующие темы:

- [class](../cpp/class-cpp.md)

- [struct](../cpp/struct-cpp.md)

- [Обзор членов класса](../cpp/class-member-overview.md)

- [Контроль доступа к членам](../cpp/member-access-control-cpp.md)

- [Наследование](../cpp/inheritance-cpp.md)

- [Статические члены](../cpp/static-members-cpp.md)

- [Пользовательские преобразования типов](../cpp/user-defined-type-conversions-cpp.md)

- [Изменяемые данные-члены (изменяемый спецификатор)](../cpp/mutable-data-members-cpp.md)

- [Объявления вложенных классов](../cpp/nested-class-declarations.md)

- [Типы анонимных классов](../cpp/anonymous-class-types.md)

- [Указатели на члены](../cpp/pointers-to-members.md)

- [Указатель this](../cpp/this-pointer.md)

- [Битовые поля в C++](../cpp/cpp-bit-fields.md)

Существует три типа классов: структура, класс и объединение. Они объявляются с помощью [структуры](../cpp/struct-cpp.md), [класс](../cpp/class-cpp.md), и [объединение](../cpp/unions.md) ключевые слова. В следующей таблице показаны различия между этими тремя типами классов.

Дополнительные сведения об объединениях см. в разделе [объединения](../cpp/unions.md). Сведения об управляемых классах и структурах см. в разделе [классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md).

### <a name="access-control-and-constraints-of-structures-classes-and-unions"></a>Управление доступом и ограничения для структур, классов и объединений

|Структуры|Классы|Объединения|
|----------------|-------------|------------|
|ключ класса **структуры**|ключ класса **класса**|ключ класса **union**|
|Доступ по умолчанию: public (открытый).|Доступ по умолчанию: private (закрытый).|Доступ по умолчанию: public (открытый).|
|Нет ограничений на использование|Нет ограничений на использование|Используется только один член за один раз|

## <a name="see-also"></a>См. также

[Справочник по языку C++](../cpp/cpp-language-reference.md)