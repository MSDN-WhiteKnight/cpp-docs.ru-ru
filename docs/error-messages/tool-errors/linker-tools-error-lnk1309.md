---
title: Ошибка средств компоновщика LNK1309
ms.date: 11/04/2016
f1_keywords:
- LNK1309
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
ms.openlocfilehash: ea675ca835dfc3fe4881e5fabbea746a4442b10a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499053"
---
# <a name="linker-tools-error-lnk1309"></a>Ошибка средств компоновщика LNK1309

> *тип1* модуль обнаружен; недопустим с параметром переключения/CLRIMAGETYPE:*тип2*

## <a name="remarks"></a>Примечания

Тип образа среды CLR была запрошена с помощью **/CLRIMAGETYPE** , но компоновщик не удалось создать образ этого типа, поскольку один или несколько модулей несовместимы с этим типом.

Например, вы увидите LNK1309 при указании **/CLRIMAGETYPE:safe** и передать модуль, построенный с **/CLR: pure**.

**/CLR: pure** и **/CLR: safe** параметров и поддержка библиотек компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017.

Вы также увидите LNK1309 Если при попытке выполнить сборку CLR чисто приложения с частичным доверием с помощью .lib ptrustu [d]. Сведения о создании приложения с частичным доверием см. в разделе [как: создание частично доверенное приложение путем удаления зависимостей в библиотеке DLL CRT](../../dotnet/create-a-partially-trusted-application.md).

Дополнительные сведения см. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) и [/CLRIMAGETYPE (укажите тип объекта CLR Image)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).