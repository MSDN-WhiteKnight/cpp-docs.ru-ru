---
title: Предупреждение компилятора (уровень 1) C4364
ms.date: 11/04/2016
f1_keywords:
- C4364
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
ms.openlocfilehash: db2774b6a73a989b4e9250719f99122826b486fe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643603"
---
# <a name="compiler-warning-level-1-c4364"></a>Предупреждение компилятора (уровень 1) C4364

\#с помощью для сборки «файл» ранее использовалась в location(line_number) без атрибута as_friend; as_friend не применяется

Объект `#using` директива была повторена для данного файла метаданных, но `as_friend` квалификатор не использовался в первом случае; компилятор будет игнорировать второй `as_friend`.

Дополнительные сведения см. в разделе [дружественные сборки (C++)](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Пример

В следующем примере создается компонент.

```
// C4364.cpp
// compile with: /clr /LD
ref class A {};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4364.

```
// C4364_b.cpp
// compile with: /clr /W1 /c
#using " C4364.dll"
#using " C4364.dll" as_friend   // C4364
```