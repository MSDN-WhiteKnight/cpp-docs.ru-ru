---
title: Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 921e6fac32d37f8976d53d49adab72fb27ab5e99
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632223"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC

Размещает элемент управления Windows Forms как особый вид элемента управления ActiveX MFC и взаимодействует с элементом управления с помощью интерфейсов ActiveX, свойства и методы <xref:System.Windows.Forms.Control> класса. Мы рекомендуем использовать .NET Framework свойства и методы для работы в элементе управления.

Образец приложения, Windows Forms с MFC, см. в разделе [MFC и Windows Forms Integration](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).

> [!NOTE]
>  В текущем выпуске `CDialogBar` не может размещать элементы управления Windows Forms.

## <a name="in-this-section"></a>В этом разделе

[Практическое руководство. Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[Практическое: привязка данных DDX/DDV к элементам Управления Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[Практическое руководство. Получение событий Windows Forms из собственных классов C++](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>Ссылка

[Класс CWinFormsControl](../mfc/reference/cwinformscontrol-class.md) &#124; [класса CDialog](../mfc/reference/cdialog-class.md) &#124; [класс CWnd](../mfc/reference/cwnd-class.md)&#124; <xref:System.Windows.Forms.Control>

## <a name="see-also"></a>См. также

[Использование пользовательского элемента управления формы Windows Forms в MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Различия в программировании Windows Forms и MFC](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)