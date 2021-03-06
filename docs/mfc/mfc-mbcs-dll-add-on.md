---
title: Надстройка DLL MBCS MFC
ms.date: 1/04/2018
helpviewer_keywords:
- MBCS
- MFC
ms.openlocfilehash: 2fdbb5dd862c7d1a8845813c6234fea9e902c1f9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57292507"
---
# <a name="mfc-mbcs-dll-add-on"></a>Надстройка DLL MBCS MFC

Поддержка MFC и его библиотек многобайтовой кодировки (MBCS) требуется дополнительный этап во время установки Visual Studio в Visual Studio 2013, 2015 и 2017.

**Visual Studio 2013**: По умолчанию библиотеки MFC, установленные в Visual Studio 2013 поддерживают только Юникод разработки. Требуется библиотек MBCS для построения проекта MFC в Visual Studio 2013 с **кодировка** свойство значение **использовать многобайтовую кодировку** или **не задано**. Загрузить библиотеку DLL в [многобайтовая библиотека MFC для Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40770).

**Visual Studio 2015**: Одновременное использование Юникода и многобайтовой Кодировки MFC DLL, включаются в состав компонентов установки Visual C++, но поддержка MFC не устанавливается по умолчанию. Visual C++ и MFC относятся к необязательным компонентам в программе установки Visual Studio. Чтобы убедиться в том, что компонент MFC установлен, в программе установки установите переключатель **Выборочная** и в разделе **Языки программирования**убедитесь, что выбраны пункты **Visual C++** и **Microsoft Foundation Classes для C++** . Если вы уже установили Visual Studio, при попытке создания проекта MFC вам будет предложено установить Visual C++ и (или) MFC.

**Visual Studio 2017**: Юникода и многобайтовой Кодировки MFC DLL устанавливаются вместе с **разработка классических приложений C++** рабочей нагрузки, при выборе **MFC и ATL поддерживает** из **дополнительных компонентов** области. Если установку не включает эти компоненты, перейдите к **файл | Новые проекты** окна и нажмите кнопку **открыть установщик Visual Studio** ссылку.

## <a name="see-also"></a>См. также

[Версии библиотек MFC](../mfc/mfc-library-versions.md)
