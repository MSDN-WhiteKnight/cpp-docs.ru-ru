---
title: /RELEASE (установить контрольную сумму)
ms.date: 11/04/2016
f1_keywords:
- /release
- VC.Project.VCLinkerTool.SetChecksum
helpviewer_keywords:
- -RELEASE linker option
- /RELEASE linker option
- checksum setting
- RELEASE linker option
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
ms.openlocfilehash: 6a45e6caa94054d4d485476786ecc5149545ed8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478813"
---
# <a name="release-set-the-checksum"></a>/RELEASE (установить контрольную сумму)

```
/RELEASE
```

## <a name="remarks"></a>Примечания

Параметр/Release задает контрольную сумму в заголовке файла .exe.

Операционная система запрашивает контрольную сумму для драйверов устройств. Задайте контрольную сумму для предварительных версий драйверов устройств для обеспечения совместимости с будущими операционными системами.

Параметр/Release имеет значение по умолчанию при [/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) параметра.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **Дополнительно** страницу свойств.

1. Изменить **установить контрольную сумму** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)