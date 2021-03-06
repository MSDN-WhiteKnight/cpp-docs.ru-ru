---
title: Работа с файлами ресурсов (C++)
ms.date: 02/14/2019
helpviewer_keywords:
- resources [C++], about resources
- resources [C++], about resource files
- resource files [C++], about resource files
ms.assetid: 2699a539-b369-4b78-80f0-df03eb7b6780
ms.openlocfilehash: 71a76da9f4eadfdca0d69873b821f4ea8eb8fc05
ms.sourcegitcommit: e540706f4e2675e7f597cfc5b4f8dde648b007bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56676426"
---
# <a name="working-with-resource-files"></a>Работа с файлами ресурсов

> [!WARNING]
> Этот раздел относится к классическим приложениям Windows, написанным на C++.
>
> Сведения о ресурсах в приложениях универсальной платформы Windows, написанного на языке C++ см. в разделе [определение ресурсов приложения](/windows/uwp/app-resources/), или о добавлении ресурсов в C + +/ CLI (управляемые) проектов, см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*.

Ресурсы могут состоять из широкий спектр элементов, таких как:

- Элементы интерфейса, которые предоставляют сведения пользователю, например точечного рисунка, значка или курсора.
- Пользовательские ресурсы, которые содержат данные и приложения требуется.
- Ресурсы версии, которые используются API-интерфейсами настройки.
- Ресурсы меню и диалоговому окну.

Вы можете добавить новые ресурсы в проект и изменить их с помощью соответствующего редактора ресурсов. Большинство мастеров Visual C++ автоматически создают RC-файл для проекта.

Чтобы вручную добавлять файлы ресурсов в управляемые проекты, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Эта статья содержит способы доступа к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам.

Глобализация и локализация ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="in-this-section"></a>В этом разделе

[Файлы ресурсов](../windows/resource-files-visual-studio.md)<br/>
Описывает файлы ресурсов и их использования в классических приложениях Windows. Также содержит ссылки на статьи, описывающие использование файлов ресурсов.

[Идентификаторы ресурсов (символы)](../windows/symbols-resource-identifiers.md)<br/>
В этой статье описываются символы и использование диалогового окна **Символы ресурсов** для управления символами в проекте.

[Редакторы ресурсов](../windows/resource-editors.md)<br/>
Описывает редакторы ресурсов, доступные в Visual Studio и типы ресурсов, которые можно изменять с каждым редактором. Также содержит ссылки на подробные сведения об использовании каждого редактора отдельно.

## <a name="related-sections"></a>Связанные разделы

[Visual C++](../visual-cpp-in-visual-studio.md)<br/>
Ссылки на документацию по Visual C++.

[Обращайтесь к нам](/visualstudio/ide/talk-to-us)<br/>
Ссылки на сведения об использовании документации, обращении в службу поддержки и использовании специальных возможностей.

## <a name="see-also"></a>См. также

[Классические приложения Windows](../windows/windows-desktop-applications-cpp.md)<br/>
[Меню и другие ресурсы](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)