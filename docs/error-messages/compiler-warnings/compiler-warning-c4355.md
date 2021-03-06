---
title: Предупреждение компилятора C4355
ms.date: 11/04/2016
f1_keywords:
- C4355
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
ms.openlocfilehash: 6b74c8dd5ce9860cb218d21790f12ba05e9be22f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554184"
---
# <a name="compiler-warning-c4355"></a>Предупреждение компилятора C4355

'this': используется в основном списке инициализации членов

**Это** указатель допустим только в нестатических функциях-членах. Он не может использоваться в списке инициализации для базового класса.

Конструкторы базового класса и конструкторы члена класса вызываются до **это** конструктор. По сути Вы передали указатель на объект несконструированное с другим конструктором. Если эти другие конструкторы, доступ к любым элементам или вызов функций-членов на это, результат будет неопределенным. Не следует использовать **это** указатель, пока завершит все конструкторы.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Следующий пример приводит к возникновению ошибки C4355:

```
// C4355.cpp
// compile with: /w14355 /c
#include <tchar.h>

class CDerived;
class CBase {
public:
   CBase(CDerived *derived): m_pDerived(derived) {};
   ~CBase();
   virtual void function() = 0;

   CDerived * m_pDerived;
};

class CDerived : public CBase {
public:
   CDerived() : CBase(this) {};   // C4355 "this" used in derived c'tor
   virtual void function() {};
};

CBase::~CBase() {
   m_pDerived -> function();
}

int main() {
   CDerived myDerived;
}
```