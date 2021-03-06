---
title: Синтаксис командной строки компоновщика
ms.date: 11/04/2016
helpviewer_keywords:
- linker [C++], syntax
- linker command line [C++]
- LINK tool [C++], command-line syntax
ms.assetid: e2a31e17-77bd-4e74-9305-75b105b26539
ms.openlocfilehash: 844d2fe4c02e274cda02fe71303f0b6dd092b431
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464120"
---
# <a name="linker-command-line-syntax"></a>Синтаксис командной строки компоновщика

Чтобы выполнить LINK. EXE-файла, используйте следующий синтаксис команды:

```
LINK arguments
```

`arguments` Параметры и имена файлов и может быть указан в любом порядке. Параметры, сначала обрабатываются, а затем файлы. Для разделения аргументов используйте пробелы или вкладки.

> [!NOTE]
>  Это средство можно запустить только из командной строки Visual Studio. В системной командной строке или проводнике это невозможно.

В командной строке параметр состоит из спецификатора дефисом (-) или косой черты (/), а затем имя параметра. Имена параметров не может быть сокращены. Некоторые параметры принимают аргумент, указанный после двоеточия (:). Не пробелы или символы табуляции, допустимы внутри параметра, за исключением в строку в кавычках в параметре/COMMENT. Укажите числовым аргументам в десятичном или нотации языка. Имена параметров, а также их аргументы ключевое слово или имя файла не учитывается регистр, но идентификаторов в качестве аргументов чувствительны к регистру.

Чтобы передать файл компоновщику, укажите имя файла в командной строке после команды LINK. Можно указать абсолютный или относительный путь с именем файла, и можно использовать подстановочные знаки в имени файла. Если опустить точку (.) и расширение имени файла, ссылка предполагается .obj целью поиск файла. ССЫЛКА не использует расширения имен файлов или отсутствие таких предположения о содержимом файлов; он определяет тип файла путем проверки его и обрабатывает его соответствующим образом.

LINK.exe возвращает ноль при успешном завершении (без ошибок).  В противном случае компоновщик возвращает номер ошибки, которое остановило ссылку.  Например если компоновщик создает LNK1104, компоновщик возвращает 1104.  Соответственно наименьшее номер ошибки, возвращаемый при возникновении ошибки компоновщика — 1000.  Возвращаемое значение 128 представляет на проблемы настройки операционной системы или config-файла; загрузчик не удалось загрузить c2.dll или link.exe.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)