---
title: Серверы автоматизации
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers
- COM components, Automation servers
- dispatch maps [MFC], Automation servers
- servers, Automation
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
ms.openlocfilehash: 39e870db2f5476a630a8ed3bc68944dbb164d469
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57305137"
---
# <a name="automation-servers"></a>Серверы автоматизации

Автоматизации делает возможным для вашего приложения для управления объектами, реализованными в другом приложении, или для представления объектов, поэтому ими можно управлять. Сервер автоматизации — это приложение, которое предоставляет программируемые объекты (называются объектами автоматизации) для других приложений (вызывается [клиенты автоматизации](../mfc/automation-clients.md)). Серверы автоматизации, иногда называются компоненты автоматизации.

Предоставление доступа к объектам автоматизации позволяет клиентам автоматизировать некоторые процедуры путем прямого доступа к объектам и доступные функциональные возможности сервера. Таким образом, предоставление доступа к объектам это удобно, когда приложения предлагают функциональные возможности, которые полезны для других приложений. Например текстовый процессор может предоставлять его функциональность, проверка орфографии, чтобы его можно использовать другие программы. Доступу к объектам таким образом таким образом поставщики могут улучшить функциональность своих приложений с помощью готовых функциональных возможностей других приложений.

Эти объекты автоматизации имеют свойства и методы, как их внешнего интерфейса. Свойства называются атрибуты объекта автоматизации. Свойства похожи на члены данных класса C++. Методы, функции, которые работают на объектах автоматизации. Методы похожи на открытыми функциями-членами класса C++.

> [!NOTE]
>  Несмотря на то, что свойства похожи на данные-члены C++, они недоступны напрямую. Чтобы обеспечить прозрачный доступ, настройте внутреннюю переменную в объект автоматизации с помощью пары функций-членов get и set для доступа к ним.

Обеспечивая доступ к функциональным возможностям приложений через стандартный и четко определенный интерфейс, автоматизации позволяет создавать приложения в одном общем языке программирования как Microsoft Visual Basic вместо в макросе различных, относящиеся к приложению Языки.

##  <a name="_core_support_for_automation_servers"></a> Поддержка для серверов автоматизации

Visual C++ и платформы MFC предоставляют широкие возможности для серверов автоматизации. Они обрабатывают значительную часть накладные расходы на создание сервера автоматизации, поэтому вам сосредоточиться на функциональности приложения.

Основной механизм для поддержки автоматизации — это схема подготовки к отправке, набор макросов, разворачивается в объявлений и вызовов, требовалось предоставить методы и свойства для OLE. Типичный диспетчеризации карты выглядит следующим образом:

[!code-cpp[NVC_MFCAutomation#1](../mfc/codesnippet/cpp/automation-servers_1.cpp)]

Окно "Свойства" и представление классов помогают в обслуживание схемы подготовки к отправке. При добавлении новый метод или свойство к классу, Visual C++ добавляет соответствующий `DISP_FUNCTION` или `DISP_PROPERTY` с параметрами, указывающее имя класса, внешних и внутренних имен типов, метода или свойства и данные.

**Добавление класса** диалоговое окно также упрощает объявления классов автоматизации и управления их свойств и операций. При использовании диалоговое окно "Добавление класса" Добавление класса в проект, необходимо указать его базового класса. Если базовый класс позволяет автоматизации, Добавление класса диалоговое окно отображает элементы управления, который используется для указания, поддерживает ли новый класс автоматизации, будь то «OLE создаваемый объект» (то есть объекты класса могут ли быть созданы по запросу COM-клиент) и внешнее имя для COM-клиентом.

**Добавление класса** диалоговое окно, затем создает объявление класса, включая соответствующий макрос OLE функций вы указали. Он также добавляет «скелет» кода для реализации функций-членов вашего класса.

Мастер приложений MFC упрощает процесс получения приложение сервера автоматизации воплощения. При выборе **автоматизации** смарт-теге **дополнительные функции** странице мастера приложений MFC добавляет в приложение `InitInstance` вызовов, необходимых для регистрации автоматизации функций объекты и запуск приложения как сервера автоматизации.

### <a name="what-do-you-want-to-do"></a>Что Вы хотите делать

- [Дополнительные сведения о клиенты автоматизации](../mfc/automation-clients.md)

- [Дополнительные сведения о классе CCmdTarget](../mfc/reference/ccmdtarget-class.md)

- [Дополнительные сведения о классе COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)

## <a name="see-also"></a>См. также

[Автоматизация](../mfc/automation.md)<br/>
[Мастер приложений MFC](../mfc/reference/mfc-application-wizard.md)
