---
title: Предупреждение компилятора (уровень 3) C4373
ms.date: 11/04/2016
f1_keywords:
- C4373
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
ms.openlocfilehash: 031b32a03d93a51f6fa00041a5b0bdf99e6eacf1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456060"
---
# <a name="compiler-warning-level-3-c4373"></a>Предупреждение компилятора (уровень 3) C4373

> "*функция*": переопределения виртуальных функций*базовая_функция*", предыдущие версии компилятора не выполняли переопределение, когда параметры только квалификаторами const или volatile

## <a name="remarks"></a>Примечания

Ваше приложение содержит метод в производном классе, который переопределяет виртуальный метод в базовом классе, и параметры в переопределяющем методе отличаются от параметров виртуального метода только по квалификатору [const](../../cpp/const-cpp.md) или [volatile](../../cpp/volatile-cpp.md) . Это означает, что компилятор должен привязать ссылку на функцию к методу в базовом или производном классе.

Версии компилятора до Visual Studio 2008 привязывают функцию к методу в базовом классе, а затем выдают предупреждение. Последующие версии компилятора игнорируют `const` или `volatile` квалификатор, привязывают функцию к методу в производном классе, а затем выдают предупреждение **C4373**. Поведение в последнем случае соответствует стандарту C++.

## <a name="example"></a>Пример

Следующий пример кода приводит к возникновению ошибки C4373. Чтобы устранить эту проблему, можно сделать либо переопределение использовать же CV-квалификаторы, как функция-член базового класса или если вы не планировали создайте переопределение, то можно присвоить функция в производном классе другое имя.

```cpp
// c4373.cpp
// compile with: /c /W3
#include <stdio.h>
struct Base
{
    virtual void f(int i) {
        printf("base\n");
    }
};

struct Derived : Base
{
    void f(const int i) {  // C4373
        printf("derived\n");
    }
};

void main()
{
    Derived d;
    Base* p = &d;
    p->f(1);
}
```

```Output
derived
```