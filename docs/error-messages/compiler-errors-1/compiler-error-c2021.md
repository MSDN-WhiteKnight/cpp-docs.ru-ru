---
title: Ошибка компилятора C2021
ms.date: 11/04/2016
f1_keywords:
- C2021
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
ms.openlocfilehash: 6492dfffbb5a2f80ea543d4248c0f77759c0a521
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514014"
---
# <a name="compiler-error-c2021"></a>Ошибка компилятора C2021

требуется экспоненциальное значение, а не "символ"

Символ, используемый в качестве экспоненты константы с плавающей запятой не является допустимым числом. Обязательно используйте показателя степени, который находится в диапазоне.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2021:

```
// C2021.cpp
float test1=1.175494351E;   // C2021
```

## <a name="example"></a>Пример

Возможное решение

```
// C2021b.cpp
// compile with: /c
float test2=1.175494351E8;
```