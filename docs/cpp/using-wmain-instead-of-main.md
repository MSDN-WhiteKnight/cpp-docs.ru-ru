---
title: Использование wmain вместо main
ms.date: 11/04/2016
f1_keywords:
- wmain
helpviewer_keywords:
- main function, vs. wmain
- wmain function
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
ms.openlocfilehash: 8cdc986d1582d2b26f137e3147ce78bc83e9daca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677764"
---
# <a name="using-wmain-instead-of-main"></a>Использование wmain вместо main

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

В модели программирования Юникода можно определить версию расширенных символов `main` функции. Используйте **wmain** вместо `main` Если требуется создать переносимый код, который соответствует спецификации Юникода.

Формальные параметры для **wmain** с помощью формат, аналогичный формату `main`. Затем можно передать в качестве аргументов "широкие" символы и указатель среды кодировки Юникод (необязательно) в программу. *Argv* и *envp* параметров **wmain** относятся к типу `wchar_t*`.

Если программа использует `main` функция, среда многобайтовой кодировки создается операционной системой при запуске программы. Расширенных символов копия среды создается только при необходимости (например, путем вызова [_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md) или [_wputenv](../c-runtime-library/reference/putenv-wputenv.md) функции). При первом вызове `_wputenv` или `_wgetenv`, если среда многобайтовой кодировки (MBCS) уже существует, создается соответствующая среда широкосимвольной строки, на которую затем указывает глобальная переменная `_wenviron`, представляющая собой широкосимвольную версию глобальной переменной `_environ`. В этот момент две копии среды (для многобайтовой кодировки и Юникода) существуют одновременно и поддерживаются операционной системой в течение всего срока жизни программы.

Аналогично Если программа использует **wmain** функция, среде MBCS (ASCII) создается в первом вызове `_putenv` или `getenv`и указывает `_environ` глобальной переменной.

Дополнительные сведения о среде MBCS см. в разделе [однобайтовые и многобайтовые кодировки](../c-runtime-library/single-byte-and-multibyte-character-sets.md) в *Справочник по библиотеке времени выполнения.*

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Функция main: запуск программы](../cpp/main-program-startup.md)