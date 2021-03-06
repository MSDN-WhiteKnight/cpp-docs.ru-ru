---
title: c16rtomb, c32rtomb
ms.date: 01/22/2018
apiname:
- c16rtomb
- c32rtomb
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- c16rtomb
- c32rtomb
- uchar/c16rtomb
- uchar/c32rtomb
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
ms.openlocfilehash: ad58184c7bab6f95a842bda5f9eb545f09434a3e
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702782"
---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb, c32rtomb

Преобразует расширенный символ в кодировке UTF-16 или UTF-32 в многобайтовый массив в текущем языковом стандарте.

## <a name="syntax"></a>Синтаксис

```C
size_t c16rtomb(
    char *mbchar,
    char16_t wchar,
    mbstate_t *state
);
size_t c32rtomb(
    char *mbchar,
    char32_t wchar,
    mbstate_t *state
);
```

### <a name="parameters"></a>Параметры

*mbchar*<br/>
Указатель на массив для хранения преобразованного многобайтового символа.

*wchar*<br/>
Расширенный символ для преобразования.

*state*<br/>
Указатель на **mbstate_t** объекта.

## <a name="return-value"></a>Возвращаемое значение

Число байтов, сохраняемых в объекте массива *mbchar*, включая любые последовательности сдвигов. Если *wchar* не является допустимым расширенным символом, значение (**size_t**)(-1) возвращается, **errno** присваивается **EILSEQ**, а для параметра *состояние* не определен.

## <a name="remarks"></a>Примечания

**C16rtomb** функция преобразует символ UTF-16 *wchar* последовательность эквивалентное обычных символов в текущем языковом стандарте. Если *mbchar* не является пустым указателем, функция сохраняет преобразованную последовательность в объекте массива, на которые указывают *mbchar*. До **MB_CUR_MAX** байтов сохраняется в *mbchar*, и *состояние* присваивается итоговое состояние многобайтового сдвига.    Если *wchar* является пустым расширенным символом, необходимые для последовательности восстановления, начальное состояние сдвига хранится, при необходимости следует символ null, и *состояние* присваивается начальное состояние преобразования. **C32rtomb** функция идентична, но преобразует символ UTF-32.

Если *mbchar* является пустым указателем, поведение аналогично вызову к функции, которая заменяет внутренний буфер для *mbchar* и расширенный символ null для *wchar*.

*Состояние* объект состояния преобразования позволяет выполнять последующие вызовы этой функции и других перезапускаемых функций, которые сохраняют состояние сдвига многобайтовых выходных символов. Результаты не определены при смешивании использовании перезапускаемых и неперезапускаемых функций или если в вызове **setlocale** между вызовами перезапускаемой функции.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**c16rtomb**, **c32rtomb**|C, C++: \<uchar.h>|

Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtoc16, mbrtoc32](mbrtoc16-mbrtoc323.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
