---
title: Приоритет в макроопределениях
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
ms.openlocfilehash: 8829b3cdbc7b2324ef3d118f8ca45dd2a1621e7e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619089"
---
# <a name="precedence-in-macro-definitions"></a>Приоритет в макроопределениях

Если макрос имеет несколько определений, NMAKE использует определение самый высокий приоритет. Ниже показан порядок приоритетов от самого высокого до самого низкого:

1. Макрос, определенный в командной строке

1. Макрос, определенный в файле makefile или включить файл

1. Унаследованные макрос переменной среды

1. Макрос, определенный в файле Tools.ini

1. Предопределенный макрос, такие как [CC](../build/command-macros-and-options-macros.md) и [AS](../build/command-macros-and-options-macros.md)

Используйте /E для макросы, унаследованные из переменных среды для переопределения макросы makefile с тем же именем. Используйте **! UNDEF** для переопределения командной строки.

## <a name="see-also"></a>См. также

[Определение макроса NMAKE](../build/defining-an-nmake-macro.md)