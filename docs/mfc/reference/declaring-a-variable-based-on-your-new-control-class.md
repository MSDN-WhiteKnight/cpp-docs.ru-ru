---
title: Объявление переменной на основании нового класса элемента управления
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.control.variable
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
ms.openlocfilehash: b3b1a168619c1c111db3e71e1a9562d441cc710d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302082"
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>Объявление переменной на основании нового класса элемента управления

После создания класса элемента управления MFC, можно объявить переменную, на его основе. Чтобы предоставить контекст для новой переменной, необходимо открыть редактор диалоговых окон и изменить диалоговое окно, в котором вы хотите использовать элемент управления. Кроме того диалоговое окно должно уже есть класс, связанный с ним. Сведения об использовании редактора диалоговых окон, см. в разделе [редактор диалоговых окон](../../windows/dialog-editor.md).

### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>Для объявления переменной на основании повторно используемого класса

1. Во время редактирования диалоговое окно, перетащите элемент управления того же типа как базовый класс нового элемента управления из панели элементов в диалоговом окне.

1. Наведите указатель мыши на перетащенный элемент управления.

1. Удерживая нажатой клавишу CTRL, дважды щелкните элемент управления.

   [Добавление переменной-члена](../../ide/add-member-variable-wizard.md) откроется диалоговое окно.

1. В **доступа** окне выберите соответствующий тип доступа для элемента управления.

1. Нажмите кнопку **управляющей переменной** "флажок".

1. В **имя переменной** введите имя.

1. В разделе **категории**, нажмите кнопку **управления**.

1. В **идентификатор элемента управления** списке, выберите элемент управления, который был добавлен. **Тип переменной** в списке должен отобразиться соответствующий тип переменной и **типа элемента управления** управления правильный тип.

9. В **комментарий** , добавьте любые комментарии, будет отображаться в коде.

10. Нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также

[Сопоставление сообщений с функциями](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)
