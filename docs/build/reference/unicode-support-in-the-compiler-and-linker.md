---
title: Поддержка Юникода в компиляторе и компоновщике
ms.date: 12/15/2017
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
helpviewer_keywords:
- Unicode, Visual C++
ms.openlocfilehash: cb21165e51960c0ca2f728381413c1a7260c9f83
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494982"
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>Поддержка Юникода в компиляторе и компоновщике

Большинство средств сборки Visual C++ поддерживает Юникод входные и выходные данные.

## <a name="filenames"></a>Имена файлов

Имена файлов, указываемые в командной строке или директивах компилятора (такие как `#include`) может содержать символы Юникода.

## <a name="source-code-files"></a>Файлы исходного кода

Символы Юникода поддерживаются в идентификаторах, макросах, строковых и символьных литералах и в комментариях.  Также поддерживаются универсальные имена символов.

Символы Юникода могут вводиться в файл исходного кода в следующие кодировки:

- UTF-16 с прямым порядком байтов с или без отметки порядка байтов (BOM)

- UTF-16 с обратным порядком байтов с или без НЕЕ

- UTF-8 с метки порядка БАЙТОВ

## <a name="output"></a>Вывод

Во время компиляции компилятор выводит диагностические данные в консоль в кодировке UTF-16.  Символы, которые могут отображаться на консоли зависят от свойств окна консоли.  Выходные данные компилятора перенаправлены в файл находится в текущей кодовой страницы ANSI консоли.

## <a name="linker-response-files-and-def-files"></a>Файлы отклика компоновщика и. DEF-файлы

Файлы отклика и DEF-файлов может быть либо UTF-16 с метки порядка БАЙТОВ или ANSI.

## <a name="asm-and-cod-dumps"></a>ASM и COD

ASM и COD, в формате ANSI по умолчанию для обеспечения совместимости с MASM. Используйте [параметр/FAu](../../build/reference/fa-fa-listing-file.md) для вывода UTF-8. Обратите внимание, что при указании **параметра/FAs**, смешанный источник будет печататься напрямую и может выглядеть например, если исходный код — UTF-8, и вы не указали **/FAsu**.

## <a name="see-also"></a>См. также

[Создание кода C/C++ в командной строке](../../build/building-on-the-command-line.md)