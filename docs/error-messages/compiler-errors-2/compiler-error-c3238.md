---
title: Ошибка компилятора C3238
ms.date: 11/04/2016
f1_keywords:
- C3238
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
ms.openlocfilehash: d81fd0fb3612a8c22fa6365aa7fc6dddb89cf120
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481163"
---
# <a name="compiler-error-c3238"></a>Ошибка компилятора C3238

"тип": тип с этим именем уже перенаправлен в сборку "сборка"

В клиентском приложении был определен тип, который также определен посредством синтаксиса перенаправления в связанной сборке. Нельзя определять оба типа в области приложения.

См. в разделе [Переадресация типа (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md) Дополнительные сведения.

## <a name="example"></a>Пример

В следующем примере создается сборка, содержащая тип, перенаправленный из другой сборки.

```
// C3238.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>Пример

В следующем примере создается сборка, которая используется для содержания определения типа, но содержит не только синтаксис перенаправления для типа.

```
// C3238_b.cpp
// compile with: /clr /LD
#using "C3238.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3238.

```
// C3238_c.cpp
// compile with: /clr /c
// C3238 expected
// Delete the following line to resolve.
#using "C3238_b.dll"
public ref class R {};
```