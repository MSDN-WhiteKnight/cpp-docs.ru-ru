---
title: Ошибка компилятора C3209
ms.date: 11/04/2016
f1_keywords:
- C3209
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
ms.openlocfilehash: f907d0605cccf0a36abd1361d8c87a783bb81506
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526715"
---
# <a name="compiler-error-c3209"></a>Ошибка компилятора C3209

«класс»: универсальный класс должен быть управляемым или WinRTclass

Универсальный класс должен быть управляемым классом или классом среды выполнения Windows.

В следующем примере показано возникновение ошибки C3209 и приводятся сведения по ее устранению.

```
// C3209.cpp
// compile with: /clr
generic <class T>
class C {};   // C3209

// OK - ref class can be generic
generic <class T>
ref class D {};
```