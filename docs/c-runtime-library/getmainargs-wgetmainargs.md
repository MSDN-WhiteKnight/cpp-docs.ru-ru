---
title: __getmainargs, __wgetmainargs
ms.date: 11/04/2016
apiname:
- __wgetmainargs
- __getmainargs
apilocation:
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- __wgetmainargs
- __getmainargs
helpviewer_keywords:
- __wgetmainargs
- __getmainargs
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
ms.openlocfilehash: 6e2bf21f2ac50d3486af56f9581ff6c8d0e0c309
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523342"
---
# <a name="getmainargs-wgetmainargs"></a>__getmainargs, __wgetmainargs

Вызывает синтаксический анализ командной строки и снова копирует аргументы в `main()` через переданные указатели.

## <a name="syntax"></a>Синтаксис

```cpp
int __getmainargs(
    int * _Argc,
   char *** _Argv,
   char *** _Env,
   int _DoWildCard,
_startupinfo * _StartInfo);

int __wgetmainargs (
   int *_Argc,
   wchar_t ***_Argv,
   wchar_t ***_Env,
   int _DoWildCard,
   _startupinfo * _StartInfo)
```

#### <a name="parameters"></a>Параметры

`_Argc`<br/>
Целое число, которое содержит число аргументов, передаваемых в `argv`. Параметр `argc` всегда больше или равен 1.

`_Argv`<br/>
Массив завершающихся null строк, представляющих введенные пользователем программы аргументы командной строки. По правилам `argv[0]` — это команда, с помощью которой вызывается программа, а argv[1] — это первый аргумент командной строки и так далее до аргумента argv[argc], который всегда имеет значение **NULL**. Первый аргумент командной строки — всегда `argv[1]`, а последний — `argv[argc - 1]`.

`_Env`<br/>
Массив строк, которые представляют переменные, заданные в среде пользователя. Этот массив завершается записью **NULL**.

`_DoWildCard`<br/>
Целое число, которое, если имеет значение 1, разворачивает подстановочные знаки в аргументах командной строки, а если имеет значение 0, не выполняет никаких действий.

`_StartInfo`<br/>
Другие сведения, передаваемые в DLL CRT.

## <a name="return-value"></a>Возвращаемое значение

0 в случае успешного выполнения; отрицательное значение, если операция завершилась неудачей.

## <a name="remarks"></a>Примечания

Используйте `__getmainargs` на платформах без расширенных символов и `__wgetmainargs` на платформах расширенных символов (Unicode).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|__getmainargs|internal.h|
|__wgetmainargs|internal.h|