---
title: Отсутствует тело функции или переменная
ms.date: 11/04/2016
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
ms.openlocfilehash: 88470272192520e9aa0582fd06ff36a0542803ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647126"
---
# <a name="missing-function-body-or-variable"></a>Отсутствует тело функции или переменная

С прототипом функции компилятор может продолжать работу без ошибок, но компоновщик не удается разрешить вызов по адресу, поскольку отсутствует код функции или переменной пространство, которое зарезервировано. Эта ошибка не увидят пока не создадите вызова функции, что компоновщик должен разрешаться.

## <a name="example"></a>Пример

Вызов функции в методе main, вызовет ошибку LNK2019, поскольку прототип позволяет компилятору считать, что функция существует.  Компоновщик обнаруживает, что это не так.

```
// LNK2019_MFBV.cpp
// LNK2019 expected
void DoSomething(void);
int main() {
   DoSomething();
}
```

## <a name="example"></a>Пример

В C++ убедитесь, что включение реализации определенной функции для класса и не только для прототипа в определении класса. При определении класса за пределами файла заголовка, не забудьте включить имя класса перед функцией (`Classname::memberfunction`).

```
// LNK2019_MFBV_2.cpp
// LNK2019 expected
struct A {
   static void Test();
};

// Should be void A::Test() {}
void Test() {}

int main() {
   A AObject;
   AObject.Test();
}
```

## <a name="see-also"></a>См. также

[Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)