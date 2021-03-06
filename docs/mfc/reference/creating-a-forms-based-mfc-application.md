---
title: Создание приложений MFC на основе форм
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfcforms.project
helpviewer_keywords:
- applications [MFC], forms-based
- forms-based applications [MFC]
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
ms.openlocfilehash: 6810a6c7fce91865a92d048129da29305e22abc1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291253"
---
# <a name="creating-a-forms-based-mfc-application"></a>Создание приложений MFC на основе форм

Форма является диалоговое окно с элементами управления, позволяющих пользователям получить доступ к данным и их возможно изменения. Можно разработать приложение, в котором пользователь выбирает из выделенной области форм. Обычно, приложения на основе форм позволяет формы доступ пользователя щелкнуть **New** из **файл** меню. Это приложение на основе диалоговых окон, которое не предоставляет пользователям доступ к **New** в диалоговом окне **файл** меню, также считается приложений на основе форм.

Интерфейс одного документа (SDI), приложения на основе форм позволяет только один экземпляр формы для выполнения за раз. Возможно, для выполнения различных форм в то же время в приложении SDI на основе форм, выбрав новую форму в **New** в диалоговом окне **файл** меню.

При создании многодокументного интерфейса (MDI), приложения на основе форм, приложение будет поддерживать несколько экземпляров той же форме.

При создании приложения с поддержкой нескольких документов верхнего уровня, рабочий стол является неявное родительским для документа, а фрейм документа не привязана к клиентской области приложения. Можно открыть несколько экземпляров документа, каждый из которых свой собственный фрейм, меню и значок в панели задач. Вы можете закрыть последующие экземпляры документов по отдельности, но если вы выберите **выхода** вариант **файл** меню исходного экземпляра, приложение закрывает все экземпляры.

SDI, MDI и несколько документов верхнего уровня приложения сохраняются все формы на основе и используется архитектура документов и представлений.

Любое приложение на базе диалогового окна по определению, — на основе форм. Приложения на основе диалоговое окно не использует архитектуры document/view, поэтому необходимо управлять методами создания и доступа для дополнительных форм.

Является базовым классом для приложений на основе формы [CFormView](../../mfc/reference/cformview-class.md). Если приложение поддерживает базы данных, то можно также выбрать любой класс, производный от `CFormView`. Форма является любое окно, производное от `CFormView` или из любого класса, который наследует от `CFormView`.

Даже при использовании базового класса, такие как [CView](../../mfc/reference/cview-class.md), позднее можно сделать ваши приложения на основе форм, [Добавление класса MFC](../../mfc/reference/adding-an-mfc-class.md) производным от `CFormView` и проверка **Generate DocTemplate ресурсы** флажок в [мастер классов MFC](../../mfc/reference/document-template-strings-mfc-add-class-wizard.md).

После завершения работы мастера будет открыт проект, и если вы выбрали `CFormView` (или класс, наследуемый от `CFormView`) в качестве базового класса или если вы создали приложение на основе диалогового окна, Visual C++ открывает редактор диалоговых окон. На этом этапе вы готовы к созданию первой формы.

### <a name="to-begin-creating-a-forms-based-mfc-executable"></a>Чтобы начать создание приложения MFC на основе форм

1. Следуйте указаниям, приведенным в [Создание приложения MFC](../../mfc/reference/creating-an-mfc-application.md).

1. В мастере приложений MFC [тип приложения](../../mfc/reference/application-type-mfc-application-wizard.md) выберите **поддержка архитектуры Document/view** "флажок".

1. Выберите **одного документа**, **несколько документов**, или **несколько документов верхнего уровня**.

    > [!NOTE]
    >  Если вы выбрали SDI-приложения, MDI или несколько документов верхнего уровня приложения, по умолчанию `CView` задается как базовый класс для представления приложения на [классы, создаваемые](../../mfc/reference/generated-classes-mfc-application-wizard.md) странице мастера. Чтобы создать приложение на основе форм, необходимо выбрать `CFormView` как базовый класс для представления приложения. Обратите внимание на то, что мастер не обеспечивает поддержку печати для приложений на основе форм.

1. Задайте другие необходимые параметры проекта на других страницах мастера.

1. Нажмите кнопку **Готово** создать общую схему приложения.

Дополнительные сведения см. в следующих разделах.

- [Производные классы представлений](../../mfc/derived-view-classes-available-in-mfc.md)

- [Альтернативы для архитектуры документ/представление](../../mfc/alternatives-to-the-document-view-architecture.md)

- [Решения, которые необходимо принять при разработке приложения](../../mfc/application-design-choices.md)

## <a name="see-also"></a>См. также

[Мастер приложений MFC](../../mfc/reference/mfc-application-wizard.md)<br/>
[Представления форм](../../mfc/form-views-mfc.md)<br/>
[Создание приложения MFC в стиле проводника](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)<br/>
[Создание приложения MFC в стиле браузера](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)
