---
title: Распространение компонентов с использованием модулей слияния
ms.date: 11/04/2016
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
ms.openlocfilehash: 7a110826e21f33986d68dcd46417ec5cbd5171bc
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58786530"
---
# <a name="redistributing-components-by-using-merge-modules"></a>Распространение компонентов с использованием модулей слияния

Visual Studio включает в себя [модули слияния](/windows/desktop/Msi/about-merge-modules) для каждого компонента Visual C++, лицензированного для распространения вместе с приложением. Если модуль слияния компилируется в файле установщика Windows, он включает развертывание определенных DLL на компьютерах, имеющих определенную платформу. В файле установки укажите, что модули слияния являются необходимыми компонентами для вашего приложения. Если Visual Studio установлена, модули слияния помещаются в папку \Program Files\Common Files\Merge Modules\\. (Распространять можно только неотладочные версии библиотек DLL Visual C++.) Дополнительные сведения и ссылку на список модулей слияния, которые подлежат лицензированию для распространения, см. в разделе [Распространение файлов Visual C++](redistributing-visual-cpp-files.md).

Модули слияния можно использовать для включения возможности установки распространяемых библиотек DLL Visual C++ в папку %SYSTEMROOT%\system32\. (Сама Visual Studio использует этот метод.) Однако установка в эту папку завершится неудачей, если у выполняющего установку пользователя нет прав администратора.

Рекомендуется не использовать модули слияния за исключением тех случаев, когда нет необходимости обслуживания приложения и нет зависимостей от более чем одной версии библиотек DLL. Модули слияния для разных версий одной и той же библиотеки DLL нельзя включить в один установщик, и модули слияния осложняют поддержку DLL независимо от приложения. Вместо этого рекомендуется установить распространяемый пакет Visual C++.

## <a name="see-also"></a>См. также

[Распространение файлов Visual C++](redistributing-visual-cpp-files.md)