---
title: Специальные символы в файле makefile
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
ms.openlocfilehash: 18fa83fcfd0c70ac4e8b9bf5be08ac1922998ecb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443734"
---
# <a name="special-characters-in-a-makefile"></a>Специальные символы в файле makefile

Чтобы использовать специальный знак NMAKE как буквенный символ, поместите знак вставки (^) перед ним. NMAKE игнорирует крышки, которые предшествуют другие символы. Специальные символы — это:

`:  ;  #  (  )  $  ^  \  {  }  !  @  —`

Знак вставки (^) в строку в кавычках рассматривается как символ литерала. Курсор в конце строки вставляет символ новой строки в строку или макрос.

В макросах, обратную косую черту (\\) за новой строкой символ заменяется пробелом.

В командах символ процента (%) — это описатель файла. Для представления % буквально в команде, укажите двойной знак процента (%) вместо одного. В других ситуациях NMAKE интерпретирует единый %, буквально, но он всегда интерпретирует значение типа double %% как единый объект %. Таким образом для представления литерала %%, укажите либо три знака процента, %%%, либо четыре, %%%.

Чтобы использовать знак доллара ($) как буквенный символ в команде, укажите два знака доллара ($). Этот метод также может использоваться в других ситуациях, где ^ $ работает.

## <a name="see-also"></a>См. также

[Содержимое файла Makefile](../build/contents-of-a-makefile.md)