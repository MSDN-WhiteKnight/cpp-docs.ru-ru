---
title: Классы и функции, создаваемые мастером MFC DLL
ms.date: 11/04/2016
helpviewer_keywords:
- functions [MFC]
- functions [MFC], DLLs
- MFC DLL Wizard
- DLLs [MFC], wizard classes and functions
- classes [MFC], generated by MFC DLL wizard
- code [MFC], generated by MFC DLL wizard
ms.assetid: e69e62fe-4953-42bf-a2fc-50bbf9bdaeaf
ms.openlocfilehash: 702b2ded210b4a585c1c8c8d010c71439e026b40
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260430"
---
# <a name="classes-and-functions-generated-by-the-mfc-dll-wizard"></a>Классы и функции, создаваемые мастером MFC DLL

Код, сформированному мастером MFC DLL зависит от типа библиотеки DLL, вы создаете и параметры, которые вы выбрали. Мастер библиотек DLL MFC создает тот же код для обоих видов обычные библиотеки DLL MFC.

|Типа используемой библиотеки DLL|Параметр|Классы|Функции|
|-----------------|------------|-------------|---------------|
|[Расширение](../../build/extension-dlls-overview.md)|Нет|Нет|`DllMain`|
|[Регулярные](../../build/regular-dlls-dynamically-linked-to-mfc.md)|Нет|Приложение класс, производный от `CWinApp`|Нет|
|[Регулярные](../../build/regular-dlls-dynamically-linked-to-mfc.md)|автоматизация|Приложение класс, производный от `CWinApp`|`DllGetClassObjectDllCanUnloadNowDllRegisterServer`|
|[Расширение](../../build/extension-dlls-overview.md)|Окно сокетов|Нет|`DllMain`|
|[Регулярные](../../build/regular-dlls-dynamically-linked-to-mfc.md)|Окно сокетов|Приложение класс, производный от `CWinApp`|`InitInstance` содержит вызов `AfxSocketInit`|

## <a name="see-also"></a>См. также

[Мастер DLL MFC](../../mfc/reference/mfc-dll-wizard.md)
