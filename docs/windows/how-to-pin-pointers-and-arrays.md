---
title: Практическое руководство. Закрепление указателей и массивов
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- pointers, pinning
- arrays [C++], pinning
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
ms.openlocfilehash: 54897253b93c97eb2d1ef94b6922c99fb75fdae9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641863"
---
# <a name="how-to-pin-pointers-and-arrays"></a>Практическое руководство. Закрепление указателей и массивов

Закрепление части объекта, определенной в управляемом объекте, имеет эффект закрепления всего объекта.  Например, если закреплен любой элемент массива, весь массив также закреплен. В языке нет расширений для объявления закрепленного массива. Чтобы закрепить массив, объявите закрепляющий указатель на тип элементов массива и закрепите один из элементов массива.

## <a name="example"></a>Пример

### <a name="code"></a>Код

```cpp
// pin_ptr_array.cpp
// compile with: /clr
#include <stdio.h>
using namespace System;

int main() {
   array<Byte>^ arr = gcnew array<Byte>(4);
   arr[0] = 'C';
   arr[1] = '+';
   arr[2] = '+';
   arr[3] = '\0';
   pin_ptr<Byte> p = &arr[1];   // entire array is now pinned
   unsigned char * cp = p;

   printf_s("%s\n", cp); // bytes pointed at by cp
                         // will not move during call
}
```

```Output
++
```

## <a name="see-also"></a>См. также

[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)