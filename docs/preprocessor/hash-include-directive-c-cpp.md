---
title: '#Директива #include (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#include'
helpviewer_keywords:
- preprocessor, directives
- '#include directive'
- include directive (#include)
ms.assetid: 17067dc0-8db1-4f2d-b43e-ec12ecf83238
ms.openlocfilehash: da68f71d2a3830cdd86870d8ef072c3fb04933db
ms.sourcegitcommit: 45835842604602a011813d0cd70abc5df91b89ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2018
ms.locfileid: "50750409"
---
# <a name="include-directive-cc"></a>Директива #include (C/C++)

Указывает препроцессору, что содержимое заданного файла необходимо обработать так, как если бы оно находилось в исходной программе в той точке, в которой располагается эта директива.

## <a name="syntax"></a>Синтаксис

```
#include  "path-spec"
#include  <path-spec>
```

## <a name="remarks"></a>Примечания

Можно упорядочить постоянный и определения макроса в содержат файлы, а затем использовать **#include** директивы, чтобы добавить их к любому файлу источника. Включаемые файлы также позволяют внедрять объявления внешних переменных и сложных типов данных. Типы можно определять и именовать только один раз во включаемом файле, созданном с этой целью.

*Path-spec* является именем файла, который при необходимости может быть предваряется спецификацией каталога. Имя файла должно указывать на существующий файл. Синтаксис *path-spec* зависит от операционной системы, на котором программа будет скомпилирована.

Сведения о том, как ссылаться на сборки в приложении C++, который компилируется с помощью [/CLR](../build/reference/clr-common-language-runtime-compilation.md), см. в разделе [#using](../preprocessor/hash-using-directive-cpp.md).

Какая бы из двух форм синтаксиса ни использовалась, вместо директивы подставляется все содержимое указанного включаемого файла. Различие между ними заключается в том, в каком порядке препроцессор ищет файлы заголовков, если путь указан не полностью. В приведенной ниже таблице показывается различие между этими формами синтаксиса.

|Форма синтаксиса|Действие|
|---|------------|
|Форма в кавычках|Препроцессор ищет включаемые файлы в следующем порядке:<br/><br/> (1) в том же каталоге, что и файл, содержащий **#include** инструкции.<br/><br/> (2) в каталогах открытых в данный момент включаемых файлов, в обратном порядке, в котором они были открыты. Поиск начинается в каталоге родительского включаемого файла, а затем выполняется в каталогах всех включаемых файлов-прародителей.<br/><br/> (3) вдоль пути, задаваемый каждого **/I** параметр компилятора.<br/><br/> (4) по путям, указанных в переменной среды INCLUDE.|
|Форма с угловыми скобками|Препроцессор ищет включаемые файлы в следующем порядке:<br/><br/> (1) вдоль пути, задаваемый каждого **/I** параметр компилятора.<br/><br/> (2) Если компиляция выполняется из командной строки, по путям, заданные в переменной среды INCLUDE.|

Как только препроцессор найдет файл с заданным именем, поиск останавливается. Если заключить полный и неоднозначная спецификация пути для файла Включение между в двойные кавычки (**""**), препроцессор ищет только спецификацию пути и игнорирует стандартные каталоги.

Если имя файла в двойных кавычках представляет собой неполную спецификацию пути, то препроцессор сначала просматривает каталог "родительского" файла. Родительский файл — это файл, содержащий **#include** директива. Например, если включить файл с именем *"файл2"* в файле с именем *file1*, *file1* является родительским файлом.

Включаемые файлы, которые могут быть «вложенными»; то есть **#include** директива может отображаться в файле, который указан другой **#include** директива. Например *"файл2"* может включать в себя *файлами "файл3"*. В этом случае *file1* по-прежнему будет родительским для объекта *"файл2"*, но он будет «дедом» *файлами "файл3"*.

Если используются вложенные файлы и компиляция выполняется из командной строки, то поиск начинается с каталогов родительских файлов, а затем выполняется в каталогах всех файлов-прародителей. Таким образом, поиск начинается относительно каталога, в котором находится исходный файл, обрабатываемый в текущий момент. Если файл не найден, поиск перемещается в каталоги, которые определяются [/I (Дополнительные каталоги включения)](../build/reference/i-additional-include-directories.md) параметр компилятора. Наконец, производится поиск в каталогах, указанных в переменной среды INCLUDE.

Из среды разработки Visual Studio в переменной среды INCLUDE игнорируется. Сведения о том, как установить нужные каталоги, в которых производится поиск включаемых файлов — это также относится к переменной среды LIB, см. в разделе [страница свойств каталогов VC ++](../ide/vcpp-directories-property-page.md).

В приведенном ниже примере демонстрируется включение файлов с помощью угловых скобок:

```
#include <stdio.h>
```

В этом примере в исходную программу добавляется содержимое файла с именем STDIO.H. Угловые скобки вызывают препроцессор осуществлять поиск в каталогах, указанных в переменной среды INCLUDE для STDIO. H, каталогах, которые определяются **/I** параметр компилятора.

В следующем примере демонстрируется включение файлов, заданных в кавычках:

```
#include "defs.h"
```

В этом примере в исходную программу добавляется содержимое файла с именем DEFS.H. Кавычки означают, что препроцессор сначала попытается найти этот файл в каталоге, содержащем родительский исходный файл.

Для включаемых файлов поддерживается до 10 уровней вложения. Когда вложенный **#include** — обработано, препроцессор продолжает вставлять файл включения в исходный файл.

**Блок, относящийся только к системам Microsoft**

Чтобы найти включаемые исходные файлы, препроцессор сначала попытается найти каталоги, которые определяются **/I** параметр компилятора. Если **/I** дополнительный параметр не указан или завершается ошибкой, то препроцессор в переменной среды INCLUDE для ищет все включаемые файлы, заданные в угловых скобках. В переменной среды INCLUDE и **/I** параметр компилятора могут содержать несколько путей, разделенных точкой с запятой (**;**). Если задано несколько каталогов отображается как часть **/I** параметр или в переменной среды INCLUDE, то препроцессор просматривает их в порядке, в котором они появляются.

Представим себе следующую команду:

```
CL /ID:\MSVC\INCLUDE MYPROG.C
```

Она дает препроцессору указание просмотреть папку D:\MSVC\INCLUDE\ и найти в ней включаемые файлы (например, STDIO.H). Ниже еще один пример:

```
SET INCLUDE=D:\MSVC\INCLUDE
CL MYPROG.C
```

Эта инструкция действуют точно так же. Если найти файл в обоих наборах каталогов не удастся, возникает неустранимая ошибка компилятора.

Если имя включаемого файла определено полностью, включая путь с двоеточием (например, F:\MSVC\SPECIAL\INCL\TEST.H), то препроцессор проходит по этому пути.

Для включаемых файлов, указанных в качестве `#include "path-spec"`, поиск начинается с каталога родительского файла, а затем переходит в каталоги всех прародительских файлов. Таким образом, поиск начинается относительно каталога, содержащего исходный файл, содержащий **#include** директивы, которые обрабатываются. Если у файла нет прародителей, а включаемый файл найти не удалось, то поиск продолжается так, как если бы его имя было заключено в угловые скобки.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Директивы препроцессора](../preprocessor/preprocessor-directives.md)<br/>
[/I (Дополнительные каталоги включения)](../build/reference/i-additional-include-directories.md)<br/>
