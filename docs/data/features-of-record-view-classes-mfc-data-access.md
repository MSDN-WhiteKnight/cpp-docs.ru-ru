---
title: Функциональные возможности классов представления записей (доступ к данным MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
ms.openlocfilehash: 2feda8f8f446e02a5056287c656707ea038f5387
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461156"
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>Функциональные возможности классов представления записей (доступ к данным MFC)

Можно сделать программирование доступа к данным на основе форм с использованием класса [CFormView](../mfc/reference/cformview-class.md), но [CRecordView](../mfc/reference/crecordview-class.md) обычно является лучшим класса для наследования. В дополнение к его `CFormView` функций, `CRecordView`:

- Обеспечивает обмен данными диалоговых (окон DDX) между элементами управления формы и ассоциированным объектом набора записей.

- Обрабатывает команды Переместить первый, переместить следующий, переместить предыдущий и переместить последний для перемещения по записям в связанном объекте набора записей.

- Сохраняет изменения текущей записи в том случае, когда пользователь переходит на другую запись.

Дополнительные сведения о навигации, см. в разделе [представления записей: поддержка навигации в представлении записей](../data/supporting-navigation-in-a-record-view-mfc-data-access.md).

## <a name="see-also"></a>См. также

[Представления записей (доступ к данным MFC)](../data/record-views-mfc-data-access.md)<br/>
[Список драйверов ODBC](../data/odbc/odbc-driver-list.md)