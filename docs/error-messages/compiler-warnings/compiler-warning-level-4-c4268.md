---
title: Предупреждение компилятора (уровень 4) C4268
ms.date: 11/04/2016
f1_keywords:
- C4268
helpviewer_keywords:
- C4268
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
ms.openlocfilehash: e3cda7ed70963508d7663c6c12b2b98ac64db204
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676503"
---
# <a name="compiler-warning-level-4-c4268"></a>Предупреждение компилятора (уровень 4) C4268

«Идентификатор»: «const»-статическое или глобальное данные, инициализированные конструктором по умолчанию, созданный компилятором заполняет объект нулями

Объект **const** инициализации глобальных или статических экземпляра нетривиальные класса с конструктором по умолчанию, созданный компилятором.

## <a name="example"></a>Пример

```
// C4268.cpp
// compile with: /c /LD /W4
class X {
public:
   int m_data;
};

const X x1;   // C4268
```

Так как этот экземпляр класса **const**, значение `m_data` не может быть изменено.