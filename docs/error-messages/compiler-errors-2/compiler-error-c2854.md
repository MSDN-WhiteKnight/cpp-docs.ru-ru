---
title: Ошибка компилятора C2854
ms.date: 11/04/2016
f1_keywords:
- C2854
helpviewer_keywords:
- C2854
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
ms.openlocfilehash: a1c30e1fa0f70e5e7bb4b1c97421ca06913fc6f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628973"
---
# <a name="compiler-error-c2854"></a>Ошибка компилятора C2854

Синтаксическая ошибка в #pragma hdrstop

`#pragma hdrstop` Указано недопустимое имя файла. Директива pragma может следовать необязательное имя файла в круглые скобки и кавычки:

Следующий пример приводит к возникновению ошибки C2854:

```
// C2854.cpp
// compile with: /c
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854
// try the following line instead
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )
```