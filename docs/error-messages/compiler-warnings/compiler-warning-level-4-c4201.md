---
title: Предупреждение компилятора (уровень 4) C4201
ms.date: 11/04/2016
f1_keywords:
- C4201
helpviewer_keywords:
- C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
ms.openlocfilehash: c7c10273e06ec35528dbd9d51c02bb844d275638
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445803"
---
# <a name="compiler-warning-level-4-c4201"></a>Предупреждение компилятора (уровень 4) C4201

использовано нестандартное расширение: безымянные структуры или объединения

При использовании расширений Майкрософт (/Ze) можно указать структуру без объявления членами другой структуры или объединения. Эти структуры создает ошибку совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>Пример

```
// C4201.cpp
// compile with: /W4
struct S
{
   float y;
   struct
   {
      int a, b, c;  // C4201
   };
} *p_s;

int main()
{
}
```