---
title: Предупреждение программы NMAKE U4011
ms.date: 11/04/2016
f1_keywords:
- U4011
helpviewer_keywords:
- U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
ms.openlocfilehash: 3b73e92c929b3dd5924584ab732f731d565d0430
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428448"
---
# <a name="nmake-warning-u4011"></a>Предупреждение программы NMAKE U4011

'target': не все зависимые компоненты; целевой объект не построен

Зависимый компонент заданного целевого объекта не существует или устарела, и команда обновления возвратила ненулевой код выхода. Параметр /K дал NMAKE продолжать обработку несвязанных частей построения и вывести код выхода 1 при окончании сеанса NMAKE.

Это предупреждение предшествует предупреждение [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) для каждой зависимости, которую не удалось создать или обновить.