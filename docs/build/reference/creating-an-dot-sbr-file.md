---
title: Создание SBR-файла
ms.date: 11/04/2016
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
ms.openlocfilehash: 63f007e567f3c1db556ba6a7f0c1a354c449f31b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501014"
---
# <a name="creating-an-sbr-file"></a>Создание SBR-файла

Входные файлы для BSCMAKE, SBR-файлов. Компилятор создает SBR-файл для каждого файла объект (.obj), то компилируется. При сборке или обновить файл информации об все SBR-файлы для вашего проекта должно быть доступно на диске.

Чтобы создать SBR-файл с помощью сведений, укажите [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md).

Чтобы создать SBR-файл, в которых нет локальных символов, укажите [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md). Если SBR-файлы содержат локальные символы, можно удалить их из BSC-файл с помощью BSCMAKE [параметр /El](../../build/reference/bscmake-options.md)`.`

Можно создать SBR-файл, не выполняя полную компиляцию. Например можно указать параметр /Zs компилятору выполнить проверку синтаксиса и по-прежнему создавать SBR-файл, если указать /FR или/fr.

Процесс построения может быть более эффективным, если SBR-файлы сначала упаковать, чтобы удалить неиспользуемые определения. Компилятор автоматически упаковывает SBR-файлов.

## <a name="see-also"></a>См. также

[Сборка BSC-файла](../../build/reference/building-a-dot-bsc-file.md)