---
title: / Diagnostics (диагностические параметры компилятора)
ms.date: 11/11/2016
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: d9b485f749f4d4d9fce4e07d9bcd6d6de564fb58
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531803"
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/ Diagnostics (диагностические параметры компилятора)

Используйте **/Diagnostics** параметра компилятора определяют отображение данных об ошибках и предупреждения о географическом положении.

## <a name="syntax"></a>Синтаксис

```
/diagnostics:{caret|classic|column}
```

## <a name="remarks"></a>Примечания

Этот параметр поддерживается в Visual Studio 2017 и более поздних версий.

**/Diagnostics** параметр компилятора управляет отображением ошибки и предупреждения.

**/Diagnostics:classic** параметр используется по умолчанию, который сообщает номер строки, где была обнаружена проблема.

**/Diagnostics:column** параметр также включает в себя столбец, где была обнаружена проблема. Это может помочь выявить конструкция конкретного языка или символ, который является причиной проблемы.

**/Diagnostics:caret** параметр включает в себя столбец, где был найден проблему и помещает вставки (^) в расположении в строке кода, в которых была обнаружена проблема.

Обратите внимание на то, что в некоторых случаях компилятор не обнаруживает ошибку, где оно произошло. Например отсутствие точки с запятой может быть незамечен до возникла непредвиденная, другие символы. Столбец передается и курсор помещается, где компилятор обнаружил, что что-то было не так, что не всегда должны убедитесь, что изменения внесены.

**/Diagnostics** параметр доступен, начиная с Visual Studio 2017.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте свой проект **страницы свойств** диалоговое окно.

1. В разделе **свойства конфигурации**, разверните **C/C++** папку и выберите **Общие** страницу свойств.

1. Используйте элемент управления dropdown в **формат диагностики** поле, чтобы выбрать диагностический режим отображения. Выберите **ОК** или **применить** для сохранения изменений.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
