---
title: Компилятор предупреждение (уровень 4) C4032
ms.date: 11/04/2016
f1_keywords:
- C4032
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
ms.openlocfilehash: fa1602d63ed9822725fea8e1b842929f221d3926
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657305"
---
# <a name="compiler-warning-level-4-c4032"></a>Компилятор предупреждение (уровень 4) C4032

формальный параметр «число» имеет другой тип после расширения

Тип параметра несовместим, по умолчанию повышениями с типом в предыдущем объявлении.

Это ошибка в ANSI C ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) и предупреждение при использовании расширений Майкрософт (/Ze).

## <a name="example"></a>Пример

```
// C4032.c
// compile with: /W4
void func();
void func(char);   // C4032, char promotes to int

int main()
{
}
```