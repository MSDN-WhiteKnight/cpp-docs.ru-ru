---
title: Предупреждение компилятора (уровень 4) C4127
ms.date: 09/13/2018
f1_keywords:
- C4127
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
ms.openlocfilehash: 7f1e23d15d8daa126987278611cb5a85a5a36fc9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614439"
---
# <a name="compiler-warning-level-4-c4127"></a>Предупреждение компилятора (уровень 4) C4127

> условное выражение является константой

## <a name="remarks"></a>Примечания

Управляющее выражение оператора **Если** инструкции или **хотя** цикла является константой. Из-за их идиоматичной повсеместно, начиная с Visual Studio 2015 с обновлением 3, тривиальные константы, например 1 или **true** срабатывание предупреждения, если только они получены в результате операции в выражении.

Если управляющее выражение оператора **хотя** цикла является константой, так как выход из цикла в середине, рассмотрите возможность замены **хотя** цикл **для** цикла. Можно опустить инициализацию, проверку завершения и шаг приращения цикла **для** цикле, что приводит к циклу неограниченное так же, как `while(1)`, и вы можете выйти из цикла из тела **для** инструкция.

## <a name="example"></a>Пример

В следующем примере показано два способа C4127 создается и показано, как использовать цикл предотвратить появление предупреждения:

```cpp
// C4127.cpp
// compile with: /W4
#include <stdio.h>
int main() {
   if (true) {}           // OK in VS2015 update 3 and later
   if (1 == 1) {}         // C4127
   while (42) { break; }  // C4127

   // OK
   for ( ; ; ) {
      printf("test\n");
      break;
   }
}
```