---
title: Ошибка средств компоновщика LNK1313
ms.date: 11/04/2016
f1_keywords:
- LNK1313
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
ms.openlocfilehash: 380df2bff305acc47e423d69ea702d77c4eafdfd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604234"
---
# <a name="linker-tools-error-lnk1313"></a>Ошибка средств компоновщика LNK1313

> обнаружен модуль ijw/native, невозможно скомпоновать с чистыми модулями

## <a name="remarks"></a>Примечания

Текущая версия Visual C++ не поддерживает компоновку собственных или смешанных управляемых или собственных OBJ-файлов с OBJ-файлы, скомпилированные с использованием **/CLR: pure**.

**/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017.

## <a name="example"></a>Пример

```cpp
// LNK1313.cpp
// compile with: /c /clr:pure
// a pure module
int main() {}
```

## <a name="example"></a>Пример

```cpp
// LNK1313_b.cpp
// compile with: /c /clr
// an IJW module
void test(){}
```

## <a name="example"></a>Пример

Следующий пример кода образует ошибку LNK1313.

```cpp
// LNK1313_c.cpp
// compile with: /link LNK1313.obj LNK1313_b.obj
// LNK1313 warning expected
```