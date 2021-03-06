---
title: /C (сохранять комментарии во время предварительной обработки)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- /c
- VC.Project.VCCLWCECompilerTool.KeepComments
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
ms.openlocfilehash: b37e279af3995bd1d61c97dc88b49cdd95495c75
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442605"
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C (сохранять комментарии во время предварительной обработки)

Сохраняет комментарии на этапе предварительной обработки.

## <a name="syntax"></a>Синтаксис

```
/C
```

## <a name="remarks"></a>Примечания

Этот параметр компилятора требует **/E**, **/P**, или **/EP** параметр.

В следующем образце кода будет отображать комментарии исходного кода.

```
// C_compiler_option.cpp
// compile with: /E /C /c
int i;   // a variable
```

В этом примере создаст следующие выходные данные.

```
#line 1 "C_compiler_option.cpp"
int i;   // a variable
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **препроцессор** страницу свойств.

1. Изменить **оставлять комментарии** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[/E (предварительная обработка в stdout)](../../build/reference/e-preprocess-to-stdout.md)<br/>
[/P (вывод результатов предварительной обработки в файл)](../../build/reference/p-preprocess-to-a-file.md)<br/>
[/EP (предварительная обработка в stdout без директив #line)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)