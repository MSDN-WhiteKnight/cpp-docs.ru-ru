---
title: scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l
ms.date: 11/04/2016
apiname:
- wscanf_s
- _wscanf_s_l
- scanf_s
- _scanf_s_l
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
apitype: DLLExport
f1_keywords:
- wscanf_s
- _tscanf_s_l
- _wscanf_s_l
- scanf_s
- _tscanf_s
- _scanf_s_l
helpviewer_keywords:
- reading data [C++], from input streams
- buffers [C++], buffer overruns
- _scanf_s_l function
- _wscanf_s_l function
- tscanf_s_l function
- tscanf_s function
- scanf_s function
- data [C++], reading from input stream
- wscanf_s function
- _tscanf_s_l function
- _tscanf_s function
- scanf_s_l function
- formatted data [C++], from input streams
- wscanf_s_l function
- buffers [C++], avoiding overruns
ms.assetid: 42cafcf7-52d6-404a-80e4-b056a7faf2e5
ms.openlocfilehash: 0fcf2a9f3ac8585e71caa9f2cc990c7e303a2f5f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528622"
---
# <a name="scanfs-scanfsl-wscanfs-wscanfsl"></a>scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l

Считывает отформатированные данные из стандартного входного потока. Эти версии [scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md) отличаются повышенной безопасностью (см. раздел [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md)).

## <a name="syntax"></a>Синтаксис

```C
int scanf_s(
   const char *format [,
   argument]...
);
int _scanf_s_l(
   const char *format,
   locale_t locale [,
   argument]...
);
int wscanf_s(
   const wchar_t *format [,
   argument]...
);
int _wscanf_s_l(
   const wchar_t *format,
   locale_t locale [,
   argument]...
);
```

### <a name="parameters"></a>Параметры

*format*<br/>
Строка управления форматированием.

*Аргумент*<br/>
Необязательные аргументы.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает количество успешно преобразованных и назначенных полей. Возвращаемое значение не включает поля, которые были прочитаны, но не были назначены. Возвращаемое значение 0 указывает, что поля не были назначены. Возвращает значение **EOF** для ошибки, или если в первой попытке чтения символа обнаружен знак окончания файла или символа окончания строки. Если *формат* — **NULL** вызывается указатель, обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **scanf_s** и **wscanf_s** возвращают **EOF** и задайте **errno** для **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Scanf_s** функция считывает данные из стандартного входного потока **stdin** и записывает данные в расположение, которое задано параметром *аргумент*. Каждый *аргумент* должен быть указателем на переменную-тип, соответствующий спецификатору типа в *формат*. Если производится копирование между перекрывающимися строками, поведение не определено.

**wscanf_s** — это двухбайтовая версия **scanf_s**; *формат* аргумент **wscanf_s** — строка расширенных символов. **wscanf_s** и **scanf_s** ведут себя одинаково, если поток открыт в режиме ANSI. **scanf_s** сейчас не поддерживает ввод из потока ЮНИКОДА.

В версиях этих функций с **_l** суффиксом идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.

В отличие от **scanf** и **wscanf**, **scanf_s** и **wscanf_s** требуется размер буфера должен быть указан для всех входных параметров типа **c**, **C**, **s**, **S**, или наборов элементов управления, которые заключаются в строк **[]**. Размер буфера в символах передается как дополнительный параметр, после которого сразу следует указатель на буфер или переменную. Например, при чтении строки размер буфера для этой строки передается следующим образом:

```C
char s[10];
scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9
```

Размер буфера включает завершающее значение NULL. Можно использовать поле спецификации ширины, чтобы гарантировать, что считываемый токен поместится в буфер. Если поле, указывающее ширину, не используется, а данные чтения токена слишком большие и не помещаются в буфер, в этот буфер ничего не записывается.

> [!NOTE]
> Параметр размера имеет тип **без знака**, а не **size_t**. Использовать static_cast для преобразования **size_t** значение **без знака** для 64-разрядной конфигурации сборки.

В следующем примере показано, что параметр размера буфера описывает максимальное число символов, а не байтов. В вызове **wscanf_s**, ширины символов, которая обозначается тип буфера не соответствует ширине символов, указанное описателем формата.

```C
wchar_t ws[10];
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));
```

**S** описатель формата указывает на использование ширины символов, которая является «противоположной» ширине по умолчанию, поддерживается функцией. Ширина символов является однобайтовой, но функция поддерживает двухбайтовые символы. В данном примере демонстрируется считывание строки, состоящей из не более чем 9 однобайтовых символов, и помещение их в буфер двухбайтовых символов. Символы обрабатываются как однобайтовые значения; первые два символа сохраняются в `ws[0]`, вторые два сохраняются в `ws[1]` и т. д.

В случае символов отдельный символ может быть прочитан следующим образом:

```C
char c;
scanf_s("%c", &c, 1);
```

При чтении нескольких символов для строк, которые не завершаются нуль-символом, целые числа используются как спецификация ширины и размер буфера.

```C
char c[4];
scanf_s("%4c", &c, (unsigned)_countof(c)); // not null terminated
```

Дополнительные сведения см. в разделе [Спецификация ширины scanf](../../c-runtime-library/scanf-width-specification.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tscanf_s**|**scanf_s**|**scanf_s**|**wscanf_s**|
|**_tscanf_s_l**|**_scanf_s_l**|**_scanf_s_l**|**_wscanf_s_l**|

Дополнительные сведения см. в разделе [Поля спецификации формата — функции scanf и wscanf](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**scanf_s**, **_scanf_s_l**|\<stdio.h>|
|**wscanf_s**, **_wscanf_s_l**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, которые связаны с консоли, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_scanf_s.c
// This program uses the scanf_s and wscanf_s functions
// to read formatted input.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int      i,
            result;
   float    fp;
   char     c,
            s[80];
   wchar_t  wc,
            ws[80];

   result = scanf_s( "%d %f %c %C %s %S", &i, &fp, &c, 1,
                     &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );
   printf( "The number of fields input is %d\n", result );
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c,
           wc, s, ws);
   result = wscanf_s( L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,
                      &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );
   wprintf( L"The number of fields input is %d\n", result );
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp,
            c, wc, s, ws);
}
```

Эта программа создает следующие выходные данные для этих входных данных:

```Input
71 98.6 h z Byte characters
36 92.3 y n Wide characters
```

```Output
The number of fields input is 6
The contents are: 71 98.599998 h z Byte characters
The number of fields input is 6
The contents are: 36 92.300003 y n Wide characters
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
