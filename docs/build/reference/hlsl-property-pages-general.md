---
title: 'Страницы свойств HLSL: Общие'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EntryPointName
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
ms.openlocfilehash: 0fce8a3b2a43cf05024a028a9e3325a929922abb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826536"
---
# <a name="hlsl-property-pages-general"></a>Страницы свойств HLSL: Общие

Чтобы настроить следующие свойства компилятора HLSL (fxc.exe), используйте его страницу свойств **Общие**. Сведения о доступе к **Общие** см. на странице свойств в папке HLSL [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

## <a name="uielement-list"></a>Список элементов пользовательского интерфейса

- **Дополнительные каталоги включаемых файлов**

   Добавляет один или несколько каталогов к пути поиска включаемых файлов. Для разделения каталогов используйте точку с запятой.

Это свойство соответствует аргументу командной строки **/I[путь]**.

- **Имя точки входа**

   Указывает точку входа для шейдера. По умолчанию используется значение **main**.

Это свойство соответствует аргументу командной строки **/E[имя]**.

- **Отключить оптимизацию**

   Значение **Да (/Od)** для отключения оптимизаций, в противном случае значение **Нет**. По умолчанию значение **Да (/Od)** используется для конфигураций **Отладка**, а значение **Нет** — для конфигураций **Выпуск**.

Аргумент командной строки **/Od** для компилятора HLSL неявно применяет аргумент командной строки **/gfp**, однако выходные данные могут не совпадать с выходными данными, создаваемыми при явной передаче обоих аргументов командной строки **/Od**  и **/gfp**.

- **Включить сведения об отладке**

   Значение **Да (/Zi)** для включения сведений об отладке, в противном случае значение **Нет**. По умолчанию значение **Да (/Zi)** используется для конфигураций **Отладка**, а значение **Нет** — для конфигураций **Выпуск**.

- **Тип шейдера**

   Указывает вид шейдера. Различные виды шейдеров реализуют различные части графического конвейера. Некоторые виды шейдеров доступны только в более поздних моделях шейдеров (которые указываются свойством **Модель шейдера**), например, вычислительные шейдеры впервые появились в модели шейдера 5.

   Это свойство соответствует части **\[тип]** аргумента командной строки **/T \[тип]_\[модель]** для компилятора HLSL. Свойство **Модель шейдера** указывает часть **[модель]** этого аргумента.

- **Модель шейдера**

   Указывает модель шейдера. Разные модели шейдеров имеют разные возможности. Как правило, последние модели шейдеров предоставляют расширенные возможности, но требуют более современного графического оборудования для выполнения кода шейдеров. Некоторые виды шейдеров (которые указываются свойством **Тип шейдера**) доступны только в более поздних моделях шейдеров, например, вычислительные шейдеры впервые появились в модели шейдера 5.

   Это свойство соответствует части **\[модель]** аргумента командной строки **/T \[тип]_\[модель]** для компилятора HLSL. Свойство **Тип шейдера** указывает часть **[тип]** этого аргумента.

- **Определения препроцессора**

   Добавляет одно или несколько определений препроцессора, применяемых к файлу исходного кода HLSL. Для разделения определений символов используйте точку с запятой.

   Это свойство соответствует аргументу командной строки **/D \[определения]** для компилятора HLSL.

## <a name="see-also"></a>См. также

[Страницы свойств HLSL](hlsl-property-pages.md)<br>
[Страницы свойств HLSL: дополнительно](hlsl-property-pages-advanced.md)<br>
[Страницы свойств HLSL: выходные файлы](hlsl-property-pages-output-files.md)