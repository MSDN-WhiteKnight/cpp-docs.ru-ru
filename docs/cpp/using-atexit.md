---
title: Использование atexit
ms.date: 11/04/2016
f1_keywords:
- atexit
helpviewer_keywords:
- atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
ms.openlocfilehash: 06baba59b5765f853f081b34d73be28a187730ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637454"
---
# <a name="using-atexit"></a>Использование atexit

С помощью [atexit](../c-runtime-library/reference/atexit.md) функции, можно указать функцию обработки выхода, который выполняется перед завершением работы программы. Никакие глобальные статические объекты, инициализированные до вызова **atexit** уничтожаются до выполнения функции обработки выхода.

## <a name="see-also"></a>См. также

[Дополнительные сведения о завершении](../cpp/additional-termination-considerations.md)