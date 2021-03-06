---
title: Тестирование элемента управления DHTML в ATL
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls
- DHTML controls, testing
ms.assetid: 0e4b4358-80ce-4505-8b06-ef4f30b1d1f0
ms.openlocfilehash: 510b24b383f6ae0489a1c54d701c632159140c2a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289953"
---
# <a name="testing-the-atl-dhtml-control"></a>Тестирование элемента управления DHTML в ATL

После создания проекта, можно создать и протестировать пример элемента управления. Прежде чем это сделать, используйте **представление классов** и **обозревателе решений** для проверки проекта. Элементы проекта описаны более подробно в [определение элементов для проекта элемента управления DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md).

## <a name="to-build-and-test-the-atl-dhtml-control"></a>Построение и тестирование элемента управления DHTML в ATL

1. Выполните построение проекта. Из **построения** меню, щелкните **построить решение**.

1. После завершения построения откройте **тестовый контейнер**. См. в разделе [тестирование свойств и событий с использованием тестового контейнера](../mfc/testing-properties-and-events-with-test-container.md) сведения о том, как получить доступ к **тестовый контейнер**.

1. В **тестовый контейнер**, из **изменить** меню, щелкните **вставить новый элемент управления**.

1. В **Вставка элемента** диалоговом окне выберите элемент управления из списка. Помните, что его имя основывается на короткое имя, которое указано в мастер элементов управления ATL. Нажмите кнопку **ОК**.

1. Проверьте элемент управления. Обратите внимание на то, что он содержит полосу прокрутки. Используйте маркеры элемента управления, чтобы изменить размер элемента управления, чтобы активировать полосы прокрутки.

1. Тестирование элемента управления кнопки. Цвета, заданного с помощью кнопки изменяет цвет фона.

1. Закрыть **тестовый контейнер**.

Далее ознакомьтесь [изменение элемента управления DHTML](../atl/modifying-the-atl-dhtml-control.md).

## <a name="see-also"></a>См. также

[Поддержка элементов управления DHTML](../atl/atl-support-for-dhtml-controls.md)
