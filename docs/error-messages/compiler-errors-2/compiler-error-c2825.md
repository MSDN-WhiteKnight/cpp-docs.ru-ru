---
title: Ошибка компилятора C2825
ms.date: 11/04/2016
f1_keywords:
- C2825
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
ms.openlocfilehash: 1e2f8e8cd38b90a698994743609892896ef0d1a5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625879"
---
# <a name="compiler-error-c2825"></a>Ошибка компилятора C2825

var: должен быть классом или пространство имен с последующим "::"

Неудачная попытка была произведена для формирования полного имени.

Например, убедитесь, что ваш код не содержит объявление функции, где имя функции начинается с::.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2825:

```
// C2825.cpp
typedef int i;
int main() {
   int* p = new int;
   p->i::i();   // C2825
   // try the following line instead
   // p->i::~i();
}
```