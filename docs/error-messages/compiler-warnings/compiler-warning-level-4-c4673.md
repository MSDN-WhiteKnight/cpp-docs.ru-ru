---
title: Предупреждение компилятора (уровень 4) C4673
ms.date: 11/04/2016
f1_keywords:
- C4673
helpviewer_keywords:
- C4673
ms.assetid: 95626ec6-f05b-43c7-8b9a-a60a6f98dd30
ms.openlocfilehash: ceaa5cd647dfb527713613b9ce3b5cd81a780fd7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657734"
---
# <a name="compiler-warning-level-4-c4673"></a>Предупреждение компилятора (уровень 4) C4673

Создание следующих типов «идентификатор» не будет учитываться на сайте получателя

Объект исключения не может быть обработано в **catch** блока. Каждый тип, который не может быть обработано отображается в выводе ошибок сразу после строки, содержащей это предупреждение. Каждый необработанное тип имеет свой собственный предупреждение. Прочтите предупреждение для каждого отдельного типа, Дополнительные сведения.

Следующий пример приводит к возникновению ошибки C4673:

```
// C4673.cpp
// compile with: /EHsc /W4
class Base {
private:
   char * m_chr;
public:
   Base() {
      m_chr = 0;
   }

   ~Base() {
      if(m_chr)
         delete m_chr;
   }
};

class Derv : private Base {
public:
   Derv() {}
   ~Derv() {}
};

int main() {
   try {
      Derv D1;
      // delete previous line, uncomment the next line to resolve
      // Base D1;
      throw D1;   // C4673
   }

   catch(...) {}
}
```