---
title: Предупреждение средств компоновщика LNK4098
ms.date: 11/04/2016
f1_keywords:
- LNK4098
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
ms.openlocfilehash: 088124fcce7cafad3fab3280ae0b3ae0d893283e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468722"
---
# <a name="linker-tools-warning-lnk4098"></a>Предупреждение средств компоновщика LNK4098

DEFAULTLIB «библиотека» противоречит использованию других библиотек; использовать /NODEFAULTLIB:library

Вы пытаетесь подключить несовместимые библиотеки.

> [!NOTE]
>  Библиотеки времени выполнения теперь содержат директивы для предотвращения смешать различные типы. Вы получите это предупреждение, если вы попытаетесь использовать разные типы или отладке и неотладочные версии библиотеки времени выполнения в одной программе. Например если компиляция выполнялась один файл для использования одного библиотеки типа времени выполнения, а другой файл для использования другого типа (например, однопоточной и многопоточных) и пытался скомпоновать их, вы получите это предупреждение. Следует компилировать все исходные файлы для использования той же библиотеке времени выполнения. См. в разделе [использование библиотеки времени выполнения](../../build/reference/md-mt-ld-use-run-time-library.md) (**/MD**, **/MT**, **/LD**) параметры компилятора, Дополнительные сведения.

Можно использовать компоновщика [/verbose: LIB](../../build/reference/verbose-print-progress-messages.md) параметр, позволяющий определить, какие библиотеки ищет компоновщик. Если вы получите LNK4098 и необходимо создать исполняемый файл, который использует, например, один поток, библиотек времени выполнения, используйте **/verbose: LIB** параметр, чтобы определить, какие библиотеки ищет компоновщик. Компоновщик должна вывести LIBC.lib и не LIBCMT.lib, MSVCRT.lib, LIBCD.lib, LIBCMTD.lib или MSVCRTD.lib как искомых библиотек. Можно указать компоновщику игнорировать некорректные библиотеки времени выполнения с помощью [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) для каждой библиотеки, которую следует игнорировать.

В следующей таблице показано, какие библиотеки должны игнорироваться в зависимости от того, какие библиотеки времени выполнения, вы хотите использовать.

|Чтобы использовать эту библиотеку времени выполнения|Игнорировать эти библиотеки|
|-----------------------------------|----------------------------|
|Один поток (libc.lib)|LIBCMT.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|
|Многопоточный (libcmt.lib)|Libc.lib, msvcrt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|
|Многопоточные с использованием библиотеки DLL (msvcrt.lib)|Libc.lib, libcmt.lib, libcd.lib, libcmtd.lib, msvcrtd.lib|
|Single-threaded отладки (libcd.lib)|Libc.lib, libcmt.lib, msvcrt.lib, libcmtd.lib, msvcrtd.lib|
|Отладка многопоточных (libcmtd.lib)|Libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, msvcrtd.lib|
|Отладочные многопоточные с использованием библиотеки DLL (msvcrtd.lib)|Libc.lib, libcmt.lib, msvcrt.lib, libcd.lib, libcmtd.lib|

Например если вы получили это предупреждение, и вы хотите создать исполняемый файл, который использует без отладки, однопоточную версию библиотеки времени выполнения, можно использовать следующие параметры с ключом компоновщика:

```
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:msvcrt.lib /NODEFAULTLIB:libcd.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib
```