---
title: Класс хранения
ms.date: 11/04/2016
helpviewer_keywords:
- linkage [C++], external
- function storage class
- function specifiers, storage class
- storage classes
- Microsoft-specific storage classes
- external linkage, storage-class specifiers
- static storage class specifiers
ms.assetid: 39a79ba6-edf5-42b6-8e45-f94227603dd6
ms.openlocfilehash: d5664634687c689316427c8652865ba9423e24f4
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147819"
---
# <a name="storage-class"></a>Класс хранения

Спецификатор класса хранения в определении функции предоставляет ей класс хранения `extern` или **static**.

## <a name="syntax"></a>Синтаксис

*function-definition*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *attribute-seq*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

/\* *attribute-seq* Поддерживается только компилятором Microsoft \*/

*declaration-specifiers*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*storage-class-specifier* *declaration-specifiers*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-specifier* *declaration-specifiers*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier* *declaration-specifiers*<sub>opt</sub>

*storage-class-specifier*: /\* Для определений функции \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**extern**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**static**

Если определение функции не содержит *storage-class-specifier*, по умолчанию устанавливается класс хранения `extern`. Функцию можно явно объявить как `extern`, но это необязательно.

Если объявление функции содержит *storage-class-specifier* `extern`, идентификатор имеет ту же компоновку, что и любое видимое объявление идентификатора с областью видимости файла. Если видимого объявления с областью видимости файла нет, идентификатор имеет внешнюю компоновку. Если идентификатор содержит область видимости файла и не содержит *storage-class-specifier*, он имеет внешнюю компоновку. Внешняя компоновка означает, что каждый экземпляр идентификатора определяет один и тот же объект или функцию. Дополнительные сведения о компоновке и области видимости файла см. в статье [Lifetime, Scope, Visibility, and Linkage](../c-language/lifetime-scope-visibility-and-linkage.md) (Время существования, область, видимость и компоновка).

Объявления функций в области видимости блока со спецификатором класса хранения, отличным от `extern`, приводят к ошибкам.

Функция с классом хранения **static** видна только в исходном файле, в котором она определена. Все остальные функции видны во всех исходных файлах программы независимо от того, явно или неявно им предоставлен класс хранения `extern`. Если требуется класс хранения **static**, он должен быть объявлен в первом экземпляре объявления функции (при его наличии) и в определении функции.

**Блок, относящийся только к системам Microsoft**

При включенных расширениях Майкрософт функции, первоначально объявленной без класса хранения (или с классом хранения `extern`), предоставляется класс хранения **static**, если определение этой функции находится в том же исходном файле и в нем явно указан класс хранения **static**.

При компиляции с параметром компилятора /Ze функции, объявленные внутри блока с помощью ключевого слова `extern`, имеют глобальную видимость. При компиляции с параметром /Za это не так. Если необходимо учитывать переносимость исходного кода, не следует полагаться на эту возможность.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Определения функций в C](../c-language/c-function-definitions.md)
