---
title: /Zf (Создание быстрее PDB-файла)
ms.date: 03/29/2018
f1_keywords:
- /Zf
helpviewer_keywords:
- /Zf
- -Zf
ms.openlocfilehash: 2c3f8d08f59c3a6803eda67126ef8a8f9ba6b1fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595744"
---
# <a name="zf-faster-pdb-generation"></a>/Zf (Создание быстрее PDB-файла)

Включите быстрее создавать PDB-ФАЙЛ в параллельные сборки, сводя к минимуму вызовы RPC к mspdbsrv.exe.

## <a name="syntax"></a>Синтаксис

> **/Zf**

## <a name="remarks"></a>Примечания

**/Zf** параметр включает поддержку компилятора для быстрее Создание PDB-файлы, при использовании [/MP (построить с несколькими процессами)](mp-build-with-multiple-processes.md) параметр, или когда система сборки (например, [MSBuild ](/visualstudio/msbuild/msbuild-reference) или [CMake](../../ide/cmake-tools-for-visual-cpp.md)) может выполнять несколько cl.exe компилятора процессы в то же время. Этот параметр заставляет компилятор внешнего интерфейса до отложить создание типов индексов для каждого типа записи в PDB-файл до конца компиляции, а затем запрашивает их все в одном вызове RPC к mspdbsrv.exe, вместо того, чтобы запрос RPC для каждой записи. Это может существенно повысить пропускную способность сборки, снижая нагрузку на процесс mspdbsrv.exe в среде, где одновременно запустить несколько процессов компилятора cl.exe RPC.

Так как **/Zf** параметр применяется только к Создание PDB-файла, он требует [/ZI](z7-zi-zi-debug-information-format.md) или [/ZI](z7-zi-zi-debug-information-format.md) параметр.

**/Zf** параметр доступно в Visual Studio 2017 версии 15.1, где оно отключено по умолчанию. Начиная с Visual Studio 2017 версии 15.7 предварительной версии 3, этот параметр включен по умолчанию при **/ZI** или **/ZI** включен параметр.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство **/Zf** и выберите **ОК**.

## <a name="see-also"></a>См. также

[Параметры компилятора в алфавитном порядке](compiler-options-listed-alphabetically.md)<br/>
[/MP (сборка с несколькими процессами)](mp-build-with-multiple-processes.md)<br/>
