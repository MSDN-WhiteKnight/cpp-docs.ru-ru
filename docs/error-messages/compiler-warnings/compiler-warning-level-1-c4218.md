---
title: Предупреждение компилятора (уровень 4) C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: 36d5de3b1270b41edfc391df960a556aca207709
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555302"
---
# <a name="compiler-warning-level-1-c4218"></a>Предупреждение компилятора (уровень 4) C4218

использовано нестандартное расширение: необходимо указать по крайней мере класс хранения или тип

В расширениях Майкрософт по умолчанию (/Ze) можно объявить переменную без указания типа или хранилища класса. Значение по умолчанию — `int`.

## <a name="example"></a>Пример

```
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

Такие объявления недопустимы в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).