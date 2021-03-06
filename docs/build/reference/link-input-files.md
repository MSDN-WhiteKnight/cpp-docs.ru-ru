---
title: Входные LINK-файлы
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
ms.openlocfilehash: a5aaf162a16b6989ac1abbcb6a574af1c31b543a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550557"
---
# <a name="link-input-files"></a>Входные LINK-файлы

Компоновщик предоставить файлы, содержащие объекты, импортировать и стандартные библиотеки, ресурсов, определения модуля и ввод команд. ССЫЛКА не использует расширения файлов для делать предположения о содержимом файла. Вместо этого ссылка анализирует каждый входной файл, чтобы определить, какого рода файл.

Объектные файлы в командной строке, обрабатываются в порядке их следования в командной строке. Библиотеки осуществляется в порядке командной строки, а также с использованием следующих механизмов: неразрешенные символы при переводе в объектный файл из библиотеки ищутся в эту библиотеку во-первых, а затем перечисленные ниже библиотеки из командной строки и [/DEFAULTLIB (укажите библиотеку по умолчанию)](../../build/reference/defaultlib-specify-default-library.md) директивы, а затем на библиотеки в начале командной строки.

> [!NOTE]
>  ССЫЛКА больше не принимает точку с запятой (или любой другой символ) как начало комментария в файлы ответов и упорядочение файлов. Точка с запятой, распознаются только как начало комментариев в файлах определения модуля (.def).

СВЯЗИ используются следующие типы входных файлов:

- [OBJ-файлы](../../build/reference/dot-obj-files-as-linker-input.md)

- [NETMODULE-файлы](../../build/reference/netmodule-files-as-linker-input.md)

- [LIB-файлы](../../build/reference/dot-lib-files-as-linker-input.md)

- [EXP-файлы](../../build/reference/dot-exp-files-as-linker-input.md)

- [DEF-файлы](../../build/reference/dot-def-files-as-linker-input.md)

- [PDB-файлы](../../build/reference/dot-pdb-files-as-linker-input.md)

- [RES-файлы](../../build/reference/dot-res-files-as-linker-input.md)

- [файлы .exe](../../build/reference/dot-exe-files-as-linker-input.md)

- [TXT-файлов](../../build/reference/dot-txt-files-as-linker-input.md)

- [ILK-файлы](../../build/reference/dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)