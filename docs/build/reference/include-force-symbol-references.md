---
title: /INCLUDE (принудительные ссылки на символы)
ms.date: 11/04/2016
f1_keywords:
- /include
- VC.Project.VCLinkerTool.ForceSymbolReferences
helpviewer_keywords:
- INCLUDE linker option
- force symbol references linker option
- symbol references linker force
- /INCLUDE linker option
- symbols, add to symbol table
- -INCLUDE linker option
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
ms.openlocfilehash: 418b66cb16954f23036eaa65e07a4abf80fdba79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439342"
---
# <a name="include-force-symbol-references"></a>/INCLUDE (принудительные ссылки на символы)

```
/INCLUDE:symbol
```

## <a name="parameters"></a>Параметры

*Символ*<br/>
Указывает символ для добавления в таблицу символов.

## <a name="remarks"></a>Примечания

Параметр/include предписывает компоновщику добавить заданный символ в таблицу символов.

Чтобы указать несколько символов, введите запятую (,), точку с запятой (;) или пробел между именами символ. В командной строке укажите/include:`symbol` один раз для каждого символа.

Компоновщик разрешает `symbol` , добавив объект, содержащий определения символа в программу. Эта функция полезна для включения объект библиотеки, в противном случае не будут связаны в программу.

Указание символ этот параметр переопределяет удаление данного символа с [предотвратят](../../build/reference/opt-optimizations.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **ввода** страницу свойств.

1. Изменить **принудительные ссылки на символы** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)