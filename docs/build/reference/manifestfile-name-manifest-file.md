---
title: /MANIFESTFILE (Имя файла манифеста)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ManifestFile
helpviewer_keywords:
- MANIFESTFILE linker option
- -MANIFESTFILE linker option
- /MANIFESTFILE linker option
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
ms.openlocfilehash: 9839665c3d74fd9d60afd21a825ffbdb752c7b00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656173"
---
# <a name="manifestfile-name-manifest-file"></a>/MANIFESTFILE (Имя файла манифеста)

```
/MANIFESTFILE:filename
```

## <a name="remarks"></a>Примечания

/ MANIFESTFILE позволяет изменить имя файла манифеста по умолчанию.  По умолчанию имя файла манифеста — имя файла с расширением MANIFEST.

/ MANIFESTFILE не имеет смысла, если также не связана с [/MANIFEST](../../build/reference/manifest-create-side-by-side-assembly-manifest.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните **компоновщика** узла.

1. Выберите **файл манифеста** страницу свойств.

1. Изменить **файл манифеста** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)