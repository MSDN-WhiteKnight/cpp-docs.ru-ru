---
title: Ошибка компилятора C2309
ms.date: 11/04/2016
f1_keywords:
- C2309
helpviewer_keywords:
- C2309
ms.assetid: 6303d5b5-72cf-42b8-92ce-b1eb48e80d48
ms.openlocfilehash: 9d114565b6b119711aaa773d76658cc27838f4a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484647"
---
# <a name="compiler-error-c2309"></a>Ошибка компилятора C2309

CATCH требуется объявление исключения заключенные в круглые скобки

Обработчик catch имеет тип, не заключенные в круглые скобки.

Следующий пример приводит к возникновению ошибки C2309:

```
// C2309.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
   try {
      throw "ooops!";
   }
   catch C {}   // C2309
   // try the following line instead
   // catch( C ) {}
}
```