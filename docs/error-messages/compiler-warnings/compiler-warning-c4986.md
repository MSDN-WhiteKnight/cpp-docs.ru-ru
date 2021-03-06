---
title: Предупреждение компилятора C4986
ms.date: 11/04/2016
f1_keywords:
- C4986
helpviewer_keywords:
- C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
ms.openlocfilehash: fb52e33ceeadda03105e391d8e0b5b3f6234d6b9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499142"
---
# <a name="compiler-warning-c4986"></a>Предупреждение компилятора C4986

«функция»: спецификация исключения не соответствует предыдущему объявлению

Это предупреждение может создаваться при отсутствии спецификацию исключений в одном объявлении, а не другой.

По умолчанию C4986 — off. Дополнительные сведения см. в разделе [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4986.

```cpp
class X { };
void f1() throw (X*);
// ...
void f1()
{
    // ...
}
```

## <a name="example"></a>Пример

Следующий пример позволяет исключить это предупреждение.

```cpp
class X { };
void f1() throw (X*);
// ...
void f1() throw (X*)
{
    // ...
}
```