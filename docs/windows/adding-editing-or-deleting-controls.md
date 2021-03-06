---
title: 'Как выполнить: Добавление, редактирование или удаление элементов управления'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog.dialog
- vc.controls.activex
- vc.editors.dialog.insertActiveXControls
helpviewer_keywords:
- Dialog Editor [C++], creating controls
- dialog boxes [C++], adding controls to
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls in dialog boxes
- custom controls [C++], dialog boxes
- controls [C++], standard
- Dialog Editor [C++], creating controls
- controls [C++], adding to dialog boxes
- controls [C++], adding multiple
- dialog box controls [C++], size
- controls [C++], sizing
- dialog boxes [C++], adding ActiveX controls
- ActiveX controls [C++], adding to dialog boxes
- Insert ActiveX Control dialog box [C++]
- controls [C++], editing properties
- ActiveX controls [C++], properties
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls [C++], editing properties
- dialog box controls [C++], deleting
- controls [C++], deleting
- Dialog Editor [C++], default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls [C++], events
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog Editor [C++], defining member variables for controls
- controls [C++], troubleshooting
- Dialog Editor [C++], troubleshooting
- dialog boxes [C++], troubleshooting
- InitCommonControls
- RichEdit 1.0 control
- rich edit controls [C++], RichEdit 1.0
ms.assetid: 73cef03f-5c8c-456a-87d1-1458dff185cf
ms.openlocfilehash: 87acb2c8356508358f68c1ae4c8d5deaa94ecd9a
ms.sourcegitcommit: 24592ba0a38c7c996ffd3d55fe1024231a59ccc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2019
ms.locfileid: "56336570"
---
# <a name="how-to-add-edit-or-delete-controls"></a>Как выполнить: Добавление, редактирование или удаление элементов управления

С помощью **диалоговое окно** редактора, можно добавить, изменить размер, изменить и удалить элементы управления в диалоговых окнах. Можно также изменить свойства элемента управления, например его идентификатор, или это изначально является видимым во время выполнения.

**Редактор диалоговых окон** отображается вкладка [окно панели элементов](/visualstudio/ide/reference/toolbox) при работе **диалоговое окно** редактора. Вы также можете настроить **элементов** окно, чтобы упростить работу. Дополнительные сведения см. в разделе [с помощью панели элементов](/visualstudio/ide/using-the-toolbox) и [отображать или скрывать окно панели элементов](showing-or-hiding-the-dialog-editor-toolbar.md).

> [!TIP]
> При использовании **диалоговое окно** редактора, во многих случаях можно выбрать кнопку правой кнопкой мыши, чтобы вывести контекстное меню с часто используемыми командами.

## <a name="add-controls"></a>Добавление элементов управления

Добавление элементов управления в новое диалоговое окно, перетащите элементы управления из **элементов** в диалоговое окно, вы создаете. Затем можно изменить местонахождение элементов управления или их размеры и форму.

Можно добавить пользовательские элементы управления в диалоговое окно, выбрав **пользовательский элемент управления** значок в **элементов** и перетащив его в диалоговое окно. Чтобы добавить **Syslink** управления, добавьте пользовательский элемент управления, а затем изменить элемент управления **класс** свойства **Syslink**. Это действие приведет к свойства для обновления и Показать **Syslink** свойства элемента управления. Сведения об оболочках MFC см. в разделе [CLinkCtrl](../mfc/reference/clinkctrl-class.md).

### <a name="to-add-a-control"></a>Добавление элемента управления

1. Убедитесь, что диалоговое окно с вкладками открыто как текущий документ в окне редактора. Если диалоговое окно не является текущим документом, вы не увидите **вкладка диалогового окна редактора** в **элементов**.

1. На **редактор диалоговых окон** вкладке **элементов** окно, выберите нужный элемент управления, а затем —:

   - Выберите диалоговое окно, в расположении, где вы хотите поместить элемент управления. Элемент управления выглядит, где вы выбрали.

   - Перетаскивание элемента управления с **элементов** окно в расположение в диалоговом окне.

   - Дважды щелкните элемент управления **элементов** окна (он отображается в диалоговом окне), затем переместите его в расположение, вы предпочитаете.

### <a name="to-add-multiple-controls"></a>Чтобы добавить несколько элементов управления

1. Удерживая нажатой **Ctrl** ключа, выберите элемент управления в **элементов** окна.

1. Выпуск **Ctrl** ключа и диалоговое окно выбора столько раз, сколько вы хотите добавить конкретного элемента управления.

1. Нажмите клавишу **Esc** остановить размещения элементов управления.

### <a name="to-size-a-control-while-you-add-it"></a>Чтобы изменить размер элемента управления при его добавлении

1. Выберите элемент управления в **элементов** окна.

1. Поместите курсор (которая отображается как перекрестие) место верхнего левого угла нового элемента управления в диалоговом окне.

1. Выберите и удерживайте кнопку мыши, чтобы закрепить в левом верхнем углу элемента управления в диалоговом окне, а затем перетащите курсор вправо и вниз до нужного размера элемента управления.

   > [!NOTE]
   > Фактически можно привязать любой из четырех углов рисуемого элемента управления. Эта процедура в качестве примера использован верхнего левого угла.

1. Отпустите кнопку мыши. В диалоговом окне, в заданный размер сопоставляет элемент управления.

   > [!TIP]
   > Можно изменить размер элемента управления после перетаскивания диалоговом окне, перемещая маркеры на границы элемента управления. Дополнительные сведения см. в разделе [изменения размера отдельных элементов управления](../windows/sizing-individual-controls.md).

## <a name="edit-controls"></a>Изменение элементов управления

### <a name="to-edit-the-properties-of-a-control-or-controls"></a>Чтобы изменить свойства элемента управления или элементов управления

1. В диалоговом окне выберите элемент управления, который требуется изменить.

   > [!NOTE]
   > Если выбрано несколько элементов управления, может редактироваться только свойствами, общими для выбранных элементов управления.

1. В [окно "Свойства"](/visualstudio/ide/reference/properties-window), изменение свойств элемента управления.

   > [!NOTE]
   > При задании **точечного рисунка** свойства для кнопки, "переключатель" или управления "флажок", равным **True**, стиль для элемента управления реализуется BS_BITMAP. Дополнительные сведения см. в разделе [стили кнопок](../mfc/reference/styles-used-by-mfc.md#button-styles). Пример сопоставления растрового изображения с элементом управления, см. в разделе [CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap). Растровые изображения не будут отображаться на элемент управления, пока вы находитесь в **диалоговое окно** редактора ресурсов.

### <a name="to-undo-changes-to-the-properties-of-a-control"></a>Чтобы отменить изменения свойств элемента управления

1. Убедитесь, что элемент управления имеет фокус **диалоговое окно** редактора.

1. Выберите **отменить** из **изменить** меню (если фокус находится не на элементе управления, **отменить** команда будет недоступна).

### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>Определение переменной-члена для элемента управления диалогового окна (кроме кнопки)

Для определения переменных-членов для всех элементов управления диалогового окна кроме кнопок можно использовать следующий метод.

> [!NOTE]
> Эта процедура применяется только к элементам управления диалогового окна в проекте MFC. Проекты ATL должны использовать **новые сообщения Windows и обработчики событий** диалоговое окно. Дополнительные сведения см. в разделе [типы сообщение, связанное с объектами пользовательского интерфейса](../mfc/reference/message-types-associated-with-user-interface-objects.md), [редактирование обработчика сообщений](../mfc/reference/editing-a-message-handler.md), и [определение обработчика сообщений для сообщения отражены](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).

1. В [редактор диалоговых окон](../windows/dialog-editor.md), выберите элемент управления.

1. Удерживая нажатой клавишу **Ctrl** , дважды щелкните управления диалогового окна.

   [Мастер добавления переменной-члена](../ide/add-member-variable-wizard.md) отображается.

1. Введите соответствующие сведения в **Добавление переменной-члена** мастера. Дополнительные сведения см. в разделе [обмен данными диалоговых окон](../mfc/dialog-data-exchange.md).

1. Выберите **ОК** для возврата **диалоговое окно** редактора.

   > [!TIP]
   > Чтобы перейти из любого элемента управления диалогового окна к его обработчику, дважды щелкните элемент управления.

Можно также использовать **переменных-членов** вкладке [мастер классов MFC](../mfc/reference/mfc-class-wizard.md) Чтобы добавить новые переменные-члены для заданного класса и просмотреть переменные-члены, которые уже были определены.

## <a name="delete-controls"></a>Удаление элементов управления

В диалоговом окне выберите элемент управления, нажмите клавишу **удалить** ключа или перейдите к **изменить** меню и выберите **удалить**.

## <a name="other-issues"></a>Другие проблемы

### <a name="troubleshooting"></a>Устранение неполадок

После добавления общего элемента управления или элемента управления форматированным редактированием в диалоговое окно, он не будет отображаться при тестировании диалоговое окно или диалоговое окно, сам не будет отображаться.

Пример проблемы:

1. Создайте проект Win32, измените параметры приложения, поэтому создается приложение Windows (не консольное приложение).

1. В [представление ресурсов](../windows/resource-view-window.md), дважды щелкните RC-файл.

1. В разделе диалоговое окно, дважды щелкните **о** поле.

1. Добавить **контроль IP-адресов** в диалоговое окно.

1. Сохранить и **перестроить все**.

1. Запустите программу.

1. В диалоговом окне **помочь** меню, выберите **о** команду и просмотрите диалоговое окно не отображается.

В настоящее время **диалоговое окно** редактор не добавляет автоматически код в проект при перетаскивании следующие общие элементы управления или элементов управления в диалоговое окно "rich edit". И не Visual Studio обеспечивает ошибку или предупреждение при возникновении этой проблемы. Чтобы устранить проблему, вручную добавьте код для элемента управления.

||||
|-|-|-|
|Элемент управления «Ползунок»|Дерево|Элемент управления "Выбор даты и времени"|
|Элемент управления "Счетчик"|Набор вкладок|Календарь месяца|
|Элемент управления хода выполнения|Анимация элемента управления|Контроль IP-адресов|
|Сочетания клавиш|Элемент управления "Rich Edit"|Расширенное поле со списком поле|
|Управления "список"|Элемент управления Rich Edit 2.0|Пользовательский элемент управления|

Чтобы использовать стандартные элементы управления в диалоговом окне, необходимо вызвать [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) или `AFXInitCommonControls` перед созданием диалоговое окно.

Для использования элементов управления RichEdit, необходимо вызвать `LoadLibrary`. Дополнительные сведения см. в разделе [о элементами управления Rich Edit](/windows/desktop/Controls/about-rich-edit-controls) в пакете SDK для Windows и [Обзор элемента управления Rich Edit](../mfc/overview-of-the-rich-edit-control.md).

> [!NOTE]
> Чтобы использовать элемент управления RichEdit с MFC, необходимо сначала вызвать [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) загрузить элемент управления RichEdit 2.0 (библиотеки RICHED20. Библиотека DLL), или вызвать [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) для загрузки более старых элемента управления RichEdit 1.0 (RICHED32. БИБЛИОТЕКА DLL).
>
> Вы можете использовать текущий [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) класса с помощью более старых элемента управления RichEdit 1.0, но `CRichEditCtrl` предназначена только для поддержки управления RichEdit 2.0. Поскольку RichEdit 1.0 и RichEdit 2.0 похожи, большинство методов будет работать. Тем не менее Обратите внимание, что существуют некоторые различия между 1.0 и 2.0 элементы управления, поэтому некоторые методы могут работать неправильно или вообще не работать.

### <a name="activex-controls"></a>Элементы управления ActiveX

Среда разработки Visual Studio позволяет вставлять элементы ActiveX в диалоговое окно. Дополнительные сведения см. в разделе [элементы ActiveX в MFC](../mfc/mfc-activex-controls.md) и [контейнеры элементов управления ActiveX](../mfc/activex-control-containers.md).

Можно использовать контекстное меню в **диалоговое окно** редактор, чтобы быстро добавить зарегистрированных элементов управления ActiveX в диалоговое окно, а также можно добавить элементы управления ActiveX для **элементов** для быстрого доступа.

**Вставка элемента ActiveX** диалоговом окне можно вставить элементы управления ActiveX в диалоговое окно при использовании [редактор диалоговых окон](../windows/dialog-editor.md). Это диалоговое окно содержит следующие свойства:

|Свойство.|Описание:|
|---|---|
|**Элемент управления ActiveX**|Отображает список элементов управления Active X. Вставка элемента управления в этом диалоговом окне не создает класс-оболочку. Если вам требуется класс-оболочку, используйте [представление классов](/visualstudio/ide/viewing-the-structure-of-code) ее создать (Дополнительные сведения см. в разделе [Добавление класса](../ide/adding-a-class-visual-cpp.md)). В этом диалоговом окне не отображается элемент управления Active X, попробуйте установить элемент управления в соответствии с инструкциями производителя.|
|**Путь**|Открывает файл, в котором находится элемент управления ActiveX.|

> [!CAUTION]
> Распространение всех элементов ActiveX в системе может быть незаконным. Эти вопросы освещены в лицензионном соглашении к программному обеспечению, которое обеспечивает установку элементов управления. Также можно обратиться к поставщику данного ПО.

#### <a name="to-add-an-activex-control"></a>Добавление элемента управления ActiveX

1. Откройте диалоговое окно, **диалоговое окно** редактора.

1. Щелкните правой кнопкой мыши в любом месте в тексте диалогового окна и в контекстном меню, выберите **Вставка элемента ActiveX**.

   **Вставка элемента ActiveX** появится диалоговое окно, показывающее все элементы управления ActiveX в вашей системе. В нижней части диалогового окна отображается путь к файлу элемента ActiveX.

1. Выберите элемент управления, нужно добавить в диалоговое окно и выбрать **ОК**.

   Элемент появится в диалоговом окне, после чего его можно будет изменить или создать для него обработчики, как для любого другого элемента управления.

> [!NOTE]
> Элементы ActiveX можно добавить **элементов** окно для упрощения доступа.

#### <a name="to-edit-properties-for-an-activex-control"></a>Чтобы изменить свойства для элемента управления ActiveX

Элементы управления ActiveX, предоставляемые независимыми поставщиками могут поставляться с их свойствами и характеристики предварительно. Будут показаны свойства элементов управления ActiveX в **свойства** окна. Кроме того, отображаются все страницы свойств, созданные изготовителем элемента управления ActiveX в **страницы свойств** диалоговое окно (для просмотра **страницу свойств** для конкретного элемента управления ActiveX, нажмите кнопку **Страницу свойств** кнопку [окно "Свойства"](/visualstudio/ide/reference/properties-window)).

На странице свойств для элемента управления ActiveX, в зависимости от свойств, поставляемые как часть элемента управления ActiveX отображаются различные вкладки.

> [!NOTE]
> Следующая процедура применяется с помощью страницы свойств для редактирования элементов управления ActiveX. Можно также просматривать и изменять свойства ActiveX в новом **свойства** окна.

1. Выберите **ActiveX** элемента управления.

1. На **представление** меню, выберите **страницу свойств** и просмотреть свойства.

1. Внесите изменения на странице свойств.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор диалоговых окон](../windows/dialog-editor.md)<br/>
[Элементы управления в диалоговых окнах](controls-in-dialog-boxes.md)<br/>
[Файлы ресурсов](../windows/resource-files-visual-studio.md)<br/>

<!-- excluded links
[Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md)<br/>
[Adding Functionality with Code Wizards](../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Adding a Class](../ide/adding-a-class-visual-cpp.md)<br/>
[Adding a Member Function](../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable](../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Overriding a Virtual Function](../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler](../mfc/reference/adding-an-mfc-message-handler.md)
[Declaring a Variable Based on Your New Control Class](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)<br/>
-->