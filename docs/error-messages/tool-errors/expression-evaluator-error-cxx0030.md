---
title: Ошибка вычислителя выражений CXX0030
ms.date: 11/04/2016
f1_keywords:
- CXX0030
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
ms.openlocfilehash: 1e52b238905fba5c310a89377b81548a1c6b5784
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500351"
---
# <a name="expression-evaluator-error-cxx0030"></a>Ошибка вычислителя выражений CXX0030

невычислимое выражение

Вычислитель выражений отладчика не удалось получить значение для выражения, по мере записи. Возможной причиной является то, что выражение ссылается на область памяти, который находится вне адресного пространства программы (разыменования указателя null является одним из примеров). Windows не поддерживает доступ к памяти за пределами адресном пространстве программы.

Можно переписать выражение с помощью скобок для управления порядком вычисления.

Эта ошибка идентична ошибке CAN0030.