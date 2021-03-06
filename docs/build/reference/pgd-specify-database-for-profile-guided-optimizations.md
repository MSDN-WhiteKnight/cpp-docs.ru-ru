---
title: /PGD (указание базы данных для профильной оптимизации)
ms.date: 03/14/2018
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
ms.openlocfilehash: 68d112c0a40289ba62e3fe5c37ae23f8f55f9209
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601296"
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (указание базы данных для профильной оптимизации)

**Параметр/PGD является устаревшим.** Начиная с Visual Studio 2015, предпочитать [/genprofile или/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) параметры компоновщика. Этот параметр используется для указания имени PGD-файла, используемые в процессе профильной оптимизации.

## <a name="syntax"></a>Синтаксис

> **/PGD:**_filename_

## <a name="argument"></a>Аргумент

*filename*<br/>
Задает имя PGD-файла, который используется для хранения сведений о выполняемой программе.

## <a name="remarks"></a>Примечания

При использовании устаревших [/LTCG: PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md) , используйте **/PGD** для указания нестандартным именем или расположением PGD-файла. Если вы не укажете **/PGD**, базовое имя файла .pgd совпадает со значением имени выходного файла (.exe или .dll) базового и создается в том же каталоге, из которого была вызвана ссылка.

При использовании устаревших **/LTCG: PGOPTIMIZE** , используйте **/PGD** параметр, чтобы указать имя PGD-файла, в которых будет производиться создание оптимизированного образа. *Filename* аргумент должен соответствовать *filename* заданное **/LTCG: PGINSTRUMENT**.

Дополнительные сведения см. в разделе [профильной оптимизации](../../build/reference/profile-guided-optimizations.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **оптимизации** страницу свойств.

1. Изменить **база данных профиля** свойство. Выберите **ОК** для сохранения изменений.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)<br/>
