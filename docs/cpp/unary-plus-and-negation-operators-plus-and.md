---
title: 'Унарные операторы «плюс» и «отрицание»: + и -'
ms.date: 11/04/2016
f1_keywords:
- +
- '-'
helpviewer_keywords:
- unary operators [C++], plus
- '- operator'
- negation operator
- + operator [C++], unary operators
- + operator
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
ms.openlocfilehash: c1d5fc926b396f1ec44b9e44e79721e2ca4a0908
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580912"
---
# <a name="unary-plus-and-negation-operators--and--"></a>Унарные операторы «плюс» и «отрицание»: + и -

## <a name="syntax"></a>Синтаксис

```
+ cast-expression
- cast-expression
```

## <a name="-operator"></a>+ - оператор

Результатом унарного оператора сложения (**+**) является значение операнда. Операнд оператора унарного оператора сложения должен иметь арифметический тип.

Над целочисленными операндами выполняется восходящее приведение целого типа. Результирующим типом является тип, до которого повышается уровень операнда. Таким образом, выражение `+ch`, где `ch` имеет тип **char**, в тип **int**; значение не меняется. См. в разделе [стандартные преобразования](standard-conversions.md) Дополнительные сведения о том, как выполняется такое повышение.

## <a name="--operator"></a>- - оператор

Оператор унарного отрицания (**-**) изменяет знак операнда. Операнд оператора унарного отрицания должен быть арифметическим типом.

Над целочисленными операндами выполняется восходящее приведение целого типа, и результирующим типом является тип, до которого повышается уровень операнда. См. в разделе [стандартные преобразования](standard-conversions.md) Дополнительные сведения о том, как выполняется такое повышение.

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

Унарное отрицание величин без знака выполняется путем вычитания значения операнда из числа 2^n, где n — количество битов в объекте заданного типа без знака.

## <a name="see-also"></a>См. также

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)