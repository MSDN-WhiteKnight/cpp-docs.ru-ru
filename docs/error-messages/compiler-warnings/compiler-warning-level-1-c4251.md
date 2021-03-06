---
title: Предупреждение компилятора (уровень 1) C4251
ms.date: 11/04/2016
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: d2fff1d2f30c4ac80af6d5b9ca452fa5f30f5a15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649661"
---
# <a name="compiler-warning-level-1-c4251"></a>Предупреждение компилятора (уровень 1) C4251

«Идентификатор»: класс «тип» должен иметь интерфейс dll для использования клиентами класса «тип2»

Чтобы свести к минимуму возможность повреждения данных при экспорте класс с [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), убедитесь, что:

- Все статические данные — доступ с помощью функций, которые экспортируются из библиотеки DLL.

- Нет встроенных методов класса могут изменять статические данные.

- Нет встроенных методов класса использовать функции CRT или другие функции библиотеки используют статические данные (см. в разделе [потенциальные ошибки передачи CRT объекты через границы DLL](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) Дополнительные сведения).

- Нет методов класса (вне зависимости от встраивания) можно использовать типы, где отличаются статические данные в экземпляров в EXE и DLL.

Экспортирование классов, определяя, библиотеки DLL, которая определяет класс с виртуальными функциями и функции, которые можно использовать для создания и удаления объектов типа, можно предотвратить.  Затем можно просто вызвать виртуальные функции в типе.

C4251 может игнорироваться при наследовании от типа в стандартной библиотеке C++, компиляция отладочного выпуска (**/MTd**), где сообщение об ошибке компилятора ссылается на _Container_base.

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251
```