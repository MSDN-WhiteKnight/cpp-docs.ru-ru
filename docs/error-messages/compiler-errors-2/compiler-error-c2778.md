---
title: Ошибка компилятора C2778
ms.date: 11/04/2016
f1_keywords:
- C2778
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
ms.openlocfilehash: 56c316ac971d0bdd1a0ca27ef8d4282acbe24779
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490516"
---
# <a name="compiler-error-c2778"></a>Ошибка компилятора C2778

неправильно сформированный GUID в __declspec(uuid())

Передан неверный GUID [uuid](../../cpp/uuid-cpp.md) расширенный атрибут.

Идентификатор GUID должен быть строкой шестнадцатеричных чисел в следующем формате:

```
// C2778a.cpp
// compile with: /c
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};
```

`uuid` Расширенный атрибут принимает строку, распознаваемые [CLSIDFromString](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromstring), с разделителями или без скобок.

Следующий пример приводит к возникновению ошибки C2778:

```
// C2778b.cpp
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778
```