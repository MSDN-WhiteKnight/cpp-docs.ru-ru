---
title: /WINMDKEYCONTAINER (указать контейнер ключей)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
ms.openlocfilehash: 8d26c49a8cf4a1f71841fabdd4ec30fb437ad349
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532240"
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER (указать контейнер ключей)

Задает контейнер ключа для подписывания файла метаданных Windows (.winmd).

```
/WINMDKEYCONTAINER:name
```

## <a name="remarks"></a>Примечания

Напоминает [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) параметра компоновщика, который применяется в файл (с расширением winmd).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **компоновщика** папки.

1. Выберите **метаданных Windows** страницу свойств.

1. В **контейнер ключа метаданных Windows** введите расположение.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)