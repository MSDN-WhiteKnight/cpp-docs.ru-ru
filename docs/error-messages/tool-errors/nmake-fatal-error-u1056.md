---
title: Неустранимая ошибка NMAKE U1056
ms.date: 11/04/2016
f1_keywords:
- U1056
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
ms.openlocfilehash: b15b14c04dd91ae648ea4311612c122f04f90477
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635933"
---
# <a name="nmake-fatal-error-u1056"></a>Неустранимая ошибка NMAKE U1056

не удается найти процессор команд

Интерпретатор командной строки не находился в каталоге, указанном в **COMSPEC** или **путь** переменные среды.

Программа NMAKE использует COMMAND.COM или CMD. EXE-файла в качестве обработчика команды при выполнении команд. Он сначала ищет для обработки команды в пути, заданном в **COMSPEC**. Если **COMSPEC** не существует, поиск NMAKE, каталоги, заданные в **путь**.