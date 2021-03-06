---
title: PROTO
ms.date: 10/22/2018
f1_keywords:
- PROTO
helpviewer_keywords:
- PROTO directive
ms.assetid: 0487ee16-9dc7-43d1-9445-cd1601f5a080
ms.openlocfilehash: 616b6be2a5c191ebc67d61288cb5fa6c183091fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536740"
---
# <a name="proto"></a>PROTO

Прототипы функции или процедуры. Можно вызвать функцию прототипом директивой PROTO с помощью [INVOKE](invoke.md) директива.

## <a name="syntax"></a>Синтаксис

> *Метка* **PROTO** \[ *расстояние*] \[ *langtype*] \[ __,__ \[ *параметр*]__:__*тега*]...

### <a name="parameters"></a>Параметры

*Метка*<br/>
Имя прототипом функции.

*distance*<br/>
(Необязательно) Используется в моделях памяти 16-разрядное переопределить значение по умолчанию и указать **NEAR** или **FAR** вызовов.

*langtype*<br/>
(Необязательно) Задает соглашение о вызывающих и имен для процедур и открытые символы. Приведены поддерживаемые соглашения.

- 32-разрядных **НЕСТРУКТУРИРОВАННЫЙ** модели: **C**, **STDCALL**

- 16-разрядное моделей: **C**, **BASIC**, **FORTRAN**, **PASCAL**, **SYSCALL**, **STDCALL**

*Параметр*<br/>
Необязательное имя параметра функции.

*Тег*<br/>
Тип параметра функции.

*Параметр* и *тега* параметры могут встречаться несколько раз для каждого переданного аргумента.

## <a name="example"></a>Пример

В этом примере показано **PROTO** объявление функции с именем `addup3` , использующий **NEAR** вызов для переопределения модели 16-разрядное значение по умолчанию для вызовов процедур, а также используется **C**соглашение о вызовах для сбора параметров и возвращения значений. Он принимает два аргумента: **WORD** и **VARARG**.

```MASM
addup3 PROTO NEAR C, argcount:WORD, arg1:VARARG
```

## <a name="see-also"></a>См. также

[Справочник по директивам](directives-reference.md)<br/>
[. Справочник по МОДЕЛИ](dot-model.md)<br/>
