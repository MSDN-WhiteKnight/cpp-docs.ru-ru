---
title: /DYNAMICBASE
ms.date: 06/12/2018
f1_keywords:
- /dynamicbase
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
ms.openlocfilehash: fb8bfd4f4b11d14dbbc605f4366cf1cd5446a319
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430800"
---
# <a name="dynamicbase"></a>/DYNAMICBASE

Указывает, следует ли создавать исполняемый образ, который может быть случайным образом переместить во время загрузки с помощью функции Windows, впервые появившаяся в Windows Vista адрес макета пространства randomization (ASLR).

## <a name="syntax"></a>Синтаксис

> **/ DYNAMICBASE**[**: НЕТ**]

## <a name="remarks"></a>Примечания

**/DYNAMICBASE** параметр изменяет заголовок *исполняемый образ*, файл .dll или .exe, чтобы указать, использует ли приложение следует случайным образом переместить во время загрузки и включает виртуальный адрес случайный выбор срока выделения, что влияет на расположение виртуальной памяти кучи, стеки и выделения памяти для операционной системы. **/DYNAMICBASE** параметр применяется к 32-разрядных и 64-разрядные образы. ASLR поддерживается в Windows Vista и более поздних операционных системах. Параметр обрабатывается в более ранних операционных систем.

По умолчанию **/DYNAMICBASE** включен. Чтобы отключить этот параметр, используйте **/DYNAMICBASE:NO**. **/DYNAMICBASE** параметр является обязательным для [/highentropyva](highentropyva-support-64-bit-aslr.md) параметр вступил в силу.

## <a name="see-also"></a>См. также

- [Параметры EDITBIN](../../build/reference/editbin-options.md)
- [Способы защиты программного обеспечения для независимых поставщиков программного обеспечения Windows](https://msdn.microsoft.com/library/bb430720.aspx)