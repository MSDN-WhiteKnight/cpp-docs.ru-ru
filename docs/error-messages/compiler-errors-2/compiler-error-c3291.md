---
title: Ошибка компилятора C3291
ms.date: 11/04/2016
f1_keywords:
- C3291
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
ms.openlocfilehash: 6d9602d1ec9f2e4a72784e20bfd90c7f3aac0781
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611345"
---
# <a name="compiler-error-c3291"></a>Ошибка компилятора C3291

default: не может быть именем тривиального свойства

Тривиальное свойство нельзя назвать `default` Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md) .

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3291.

```
// C3291.cpp
// compile with: /clr /c
ref struct C {
   property System::String ^ default;   // C3291
   property System::String ^ Default;   // OK
};
```