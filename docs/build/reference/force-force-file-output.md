---
title: /FORCE (Назначенный файл вывода)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
ms.openlocfilehash: 5555a76cc792c15bea9c6c393debbd0fb38e30e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445661"
---
# <a name="force-force-file-output"></a>/FORCE (Назначенный файл вывода)

```
/FORCE:[MULTIPLE|UNRESOLVED]
```

## <a name="remarks"></a>Примечания

Параметр/Force предписывает компоновщику создание .exe-файл или DLL, даже если на символ существует ссылка, но не определен или определен многократно.

Параметр/Force может занять необязательный аргумент:

- Используйте/FORCE: Multiple, чтобы создать выходной файл, или не найдет параметр LINK несколько определений символа.

- Использовать параметр/FORCE: UNRESOLVED, чтобы создать выходной файл, или не найдет параметр LINK неопределенный символ. / FORCE: НЕРАЗРЕШЕННЫЕ учитывается, если символ точки записи НЕРАЗРЕШЕН.

/ FORCE без аргументов выражает как многократные и неразрешенные ссылки.

Файл, созданный с помощью этого параметра не может выполняться правильно. Компоновщик не будет инкрементная компоновка при указании параметра/FORCE.

При компиляции модуля **/CLR**, **/FORCE** не создает образ.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр в **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)