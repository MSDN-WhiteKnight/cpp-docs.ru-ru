---
title: Сведения об этапах настраиваемого построения и событиях построения.
ms.date: 11/04/2016
helpviewer_keywords:
- builds [C++], events
- custom build steps [C++], customizing builds
- events [C++], build
- custom build steps [C++]
- build steps [C++]
- build events [C++], order of events and build steps
- build steps [C++], build events
- builds [C++], custom build steps
ms.assetid: beb2f017-3e9f-4b2c-9b57-2572fd2628e4
ms.openlocfilehash: 5bc402ad8999f1864c7e6b1155da3c68862dda97
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827743"
---
# <a name="understanding-custom-build-steps-and-build-events"></a>Сведения об этапах настраиваемого построения и событиях построения.

В среде разработки Visual C++ существует три основных способа для настройки процесса сборки.

- **Настраиваемые этапы сборки**

   Настраиваемый этап сборки — это правило сборки, связанное с проектом. Настраиваемый этап сборки может указать командную строку для выполнения, любые дополнительные входные или выходные файлы, а также отображаемые сообщения. Дополнительные сведения см. в разделе [Как добавить пользовательский шаг сборки в проекты MSBuild](how-to-add-a-custom-build-step-to-msbuild-projects.md).

- **Настраиваемые средства сборки**

   Настраиваемое средство сборки — это правило сборки, связанное с одним или несколькими файлами. Настраиваемый этап сборки может передавать входные файлы настраиваемому средству сборки, в результате чего создается один или несколько выходных файлов. Например, файлы справки в приложении MFC создаются с помощью настраиваемого средства сборки. Дополнительные сведения см. в разделе [Как Добавление пользовательских средств сборки в проекты MSBuild](how-to-add-custom-build-tools-to-msbuild-projects.md) и [Задание пользовательских средств сборки](specifying-custom-build-tools.md).

- **События сборки**

   События сборки позволяют настроить сборку проекта. Существует три события сборки: *перед сборкой*, *перед компоновкой* и *после сборки*. Событие сборки позволяет указать действие, выполняемое в определенное время в процессе сборки. Например, можно использовать событие сборки для регистрации файла в **regsvr32.exe** после завершения сборки проекта. Дополнительные сведения см. в разделе [Задание событий сборки](specifying-build-events.md).

Раздел [Устранение неполадок настроек сборки](troubleshooting-build-customizations.md) поможет убедиться, что настраиваемые этапы и события сборки работают ожидаемым образом.

Формат вывода для настраиваемого этапа сборки или события сборки также может сделать работу с инструментом более удобной. Дополнительные сведения см. в разделе [Форматирование выходных данных этапа настраиваемой сборки или события сборки](formatting-the-output-of-a-custom-build-step-or-build-event.md).

События и настраиваемые этапы сборки выполняются в следующем порядке вместе с другими этапами сборки:

1. Событие перед сборкой

2. Настраиваемые средства сборки для отдельных файлов

3. MIDL

4. Компилятор ресурсов

5. Компилятор C/C++

6. Событие перед компоновкой

7. Компоновщик или библиотекарь (по необходимости)

8. Инструмент манифеста

9. BSCMake

10. Настраиваемый этап сборки для проекта

11. Событие после сборки

`custom build step on the project` и `post-build event` выполняются последовательно после завершения всех остальных процессов сборки.

## <a name="in-this-section"></a>В данном разделе

[Определение пользовательских инструментов сборки](specifying-custom-build-tools.md)<br/>
[Определение событий сборки](specifying-build-events.md)<br/>
[Устранение неполадок с настройками сборки](troubleshooting-build-customizations.md)<br/>
[Форматирование выходных данных этапа настраиваемой сборки или события сборки](formatting-the-output-of-a-custom-build-step-or-build-event.md)<br/>

## <a name="see-also"></a>См. также

[Проекты Visual Studio — C++](creating-and-managing-visual-cpp-projects.md)<br>
[Стандартные макросы для команд и свойств сборки](reference/common-macros-for-build-commands-and-properties.md)