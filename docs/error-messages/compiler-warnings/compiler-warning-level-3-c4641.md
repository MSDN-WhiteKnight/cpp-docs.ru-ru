---
title: Предупреждение компилятора (уровень 3) C4641
ms.date: 11/04/2016
f1_keywords:
- C4641
helpviewer_keywords:
- C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
ms.openlocfilehash: eea1f28c55c8beef5fada10080ebaac9371c94e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477484"
---
# <a name="compiler-warning-level-3-c4641"></a>Предупреждение компилятора (уровень 3) C4641

в документирующем комментарии XML присутствует неоднозначная перекрестная ссылка

Компилятору не удалось однозначно разрешить ссылку. Чтобы устранить это предупреждение, укажите сведения о параметрах, необходимо сделать ссылку однозначной.

Дополнительные сведения см. в разделе [XML Documentation](../../ide/xml-documentation-visual-cpp.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4641.

```
// C4641.cpp
// compile with: /W3 /doc /clr /c

/// <see cref="f" />   // C4641
// try the following line instead
// /// <see cref="f(int)" />
public ref class GR {
public:
   void f( int ) {}
   void f( char ) {}
};
```