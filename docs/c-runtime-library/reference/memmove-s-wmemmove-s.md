---
title: memmove_s, wmemmove_s
ms.date: 11/04/2016
apiname:
- wmemmove_s
- memmove_s
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wmemmove_s
- memmove_s
helpviewer_keywords:
- wmemmove_s function
- memmove_s function
ms.assetid: a17619e4-1307-4bb0-98c6-77f8c68dab2d
ms.openlocfilehash: 28d879a205790d1f132caca1022d0740e317c342
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210605"
---
# <a name="memmoves-wmemmoves"></a>memmove_s, wmemmove_s

Перемещает один буфер в другой. Это версии функции [memmove, wmemmove](memmove-wmemmove.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t memmove_s(
   void *dest,
   size_t numberOfElements,
   const void *src,
   size_t count
);
errno_t wmemmove_s(
   wchar_t *dest,
   size_t numberOfElements,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>Параметры

*dest*<br/>
Конечный объект.

*numberOfElements*<br/>
Размер буфера назначения.

*src*<br/>
Исходный объект.

*count*<br/>
Число байтов (**memmove_s**) или символов (**wmemmove_s**) для копирования.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи

### <a name="error-conditions"></a>Условия ошибок

|*dest*|*numberOfElements*|*src*|Возвращаемое значение|Содержание *dest*|
|------------|------------------------|-----------|------------------|------------------------|
|**NULL**|any|any|**EINVAL**|не изменено|
|any|any|**NULL**|**EINVAL**|не изменено|
|any|< *число*|any|**ERANGE**|не изменено|

## <a name="remarks"></a>Примечания

Копирует *число* байтов символов из *src* для *dest*. Если отдельные области источника и назначения перекрывают, **memmove_s** гарантирует, что байты исходного объекта в перекрывающейся области будут скопированы, прежде чем будут перезаписаны.

Если *dest* или, если *src* является пустым указателем, или если строка назначения слишком мал, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, эти функции возвращают **EINVAL** и задайте **errno** для **EINVAL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**memmove_s**|\<string.h>|
|**wmemmove_s**|\<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_memmove_s.c
//
// The program demonstrates the
// memmove_s function which works as expected
// for moving overlapping regions.

#include <stdio.h>
#include <string.h>

int main()
{
   char str[] = "0123456789";

   printf("Before: %s\n", str);

   // Move six bytes from the start of the string
   // to a new position shifted by one byte. To protect against
   // buffer overrun, the secure version of memmove requires the
   // the length of the destination string to be specified.

   memmove_s((str + 1), strnlen(str + 1, 10), str, 6);

   printf_s(" After: %s\n", str);
}
```

### <a name="output"></a>Вывод

```Output
Before: 0123456789
After: 0012345789
```

## <a name="see-also"></a>См. также

[Манипуляция буфером](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memcpy, wmemcpy](memcpy-wmemcpy.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
