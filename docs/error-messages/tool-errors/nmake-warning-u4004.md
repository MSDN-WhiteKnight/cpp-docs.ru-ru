---
title: Предупреждение программы NMAKE U4004
ms.date: 11/04/2016
f1_keywords:
- U4004
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
ms.openlocfilehash: 882f6c98b31d23d283f5e8b32b46a46c543b1a76
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436222"
---
# <a name="nmake-warning-u4004"></a>Предупреждение программы NMAKE U4004

слишком много правил для целевой объект «targetname»

Был указан более одного блока описания для заданного целевого объекта с помощью одного двоеточия (**:**) в качестве разделителей. NMAKE выполнения команды в первом блоке описание и не последующих блоков.

Чтобы указать тот же целевой объект в несколько зависимостей, используйте двойные двоеточия (`::`) в качестве разделителя в каждой строке зависимость.