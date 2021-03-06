---
title: __argc, __argv, __wargv
ms.date: 11/04/2016
apiname:
- __wargv
- __argv
- __argc
apilocation:
- msvcrt120.dll
apitype: DLLExport
f1_keywords:
- __argv
- __argc
- __wargv
helpviewer_keywords:
- __argv
- __wargv
- __argc
ms.assetid: 17001b0a-04ad-4762-b3a6-c54847f02d7c
ms.openlocfilehash: de0c4783b30764350eea35007583c1481ab01024
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575322"
---
# <a name="argc-argv-wargv"></a>__argc, __argv, __wargv

Глобальная переменная `__argc` — это счетчик числа аргументов командной строки, переданных программе. `__argv` — указатель на массив одно- или многобайтовых строк, который содержит аргументы программы, а `__wargv` — указатель на массив строк расширенных символов, который содержит аргументы программы. Эти глобальные переменные обеспечивают аргументы для `main` или `wmain`.

## <a name="syntax"></a>Синтаксис

```
extern int __argc;
extern char ** __argv;
extern wchar_t ** __wargv;
```

## <a name="remarks"></a>Примечания

В программе, которая использует функцию `main`, `__argc` и `__argv` инициализируются при запуске программы на основе командной строки, которая используется для запуска программы. Командная строка разбирается на отдельные аргументы, а подстановочные знаки разворачиваются. Число аргументов назначается функции `__argc`, строки аргументов выделяются в куче, а указатель на массив аргументов назначается `__argv`. В программе, которая скомпилирована для использования расширенных символов и функции `wmain`, аргументы анализируются и подстановочные знаки разворачиваются как строки расширенных символов, а указатель на массив строк аргументов назначается `__wargv`.

Для создания переносимого кода рекомендуется использовать аргументы, переданные в `main`, чтобы получить аргументы командной строки в программе.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE не определен|_UNICODE определено|
|---------------------|---------------------------|-----------------------|
|`__targv`|`__argv`|`__wargv`|

## <a name="requirements"></a>Требования

|Глобальная переменная|Обязательный заголовок|
|---------------------|---------------------|
|`__argc`, `__argv`, `__wargv`|\<stdlib.h>, \<cstdlib> (C++)|

`__argc`, `__argv` и `__wargv` являются расширениями Майкрософт. Сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Глобальные переменные](../c-runtime-library/global-variables.md)<br/>
[Функция main: запуск программы](../cpp/main-program-startup.md)<br/>
[Использование wmain вместо main](../cpp/using-wmain-instead-of-main.md)