---
title: Ошибка компилятора C2228
ms.date: 11/04/2016
f1_keywords:
- C2228
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
ms.openlocfilehash: 20e295d09e39a12ed8163ec980fa304cd4167218
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628401"
---
# <a name="compiler-error-c2228"></a>Ошибка компилятора C2228

слева от ".identifier" должен быть указан класс, структура или объединение

Операнд слева от точки (.) не класса, структуры или объединения.

Следующий пример приводит к возникновению ошибки C2228:

```
// C2228.cpp
int i;
struct S {
public:
    int member;
} s, *ps = &s;

int main() {
   i.member = 0;   // C2228 i is not a class type
   ps.member = 0;  // C2228 ps is a pointer to a structure

   s.member = 0;   // s is a structure type
   ps->member = 0; // ps points to a structure S
}
```

Эта ошибка также возникает из-за неправильного синтаксиса при использовании управляемых расширений. В то время как в других языках Visual Studio для доступа к члену управляемого класса можно использовать оператор "точка", в C++ указатель на объект означает, что для доступа к члену вы должны использовать оператор ->:

Неправильно: `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`

Правильно: `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`