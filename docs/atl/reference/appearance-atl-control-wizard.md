---
title: Внешний вид, мастер элементов управления ATL
ms.date: 08/31/2018
f1_keywords:
- vc.codewiz.class.atl.control.misc
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
ms.openlocfilehash: 4d3b0519951636fad4175dc35261ba35b3694ffa
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280411"
---
# <a name="appearance-atl-control-wizard"></a>Внешний вид, мастер элементов управления ATL

Эта страница мастера используется для определения дополнительных параметров пользовательских элементов для элемента управления. Эта страница доступна для элементов управления, которые определены как **стандартные элементы управления** под **типа элемента управления** на [параметры, мастер элементов управления ATL](../../atl/reference/options-atl-control-wizard.md) страницы.

## <a name="uielement-list"></a>Список элементов пользовательского интерфейса

- **Просмотр состояния**

   Задает внешний вид элемента управления в контейнере.

   - **Непрозрачный**: Задает VIEWSTATUS_OPAQUE, бит в [Просмотр СОСТОЯНИЯ](/windows/desktop/api/ocidl/ne-ocidl-tagviewstatus) перечисления и рисует прямоугольник весь элемент управления, переданный в [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) метод. Элемент управления отображается непрозрачным, а контейнеры показывает за элемента управления.

      Этот параметр помогает быстрее нарисуйте элемент управления контейнера. Если этот параметр не выбран, элемент управления может содержать прозрачного частей.

      Только непрозрачного элемента управления может иметь непрозрачный фон.

   - **Непрозрачный фон**: Задает VIEWSTATUS_SOLIDBKGND бит в перечислении Просмотр СОСТОЯНИЯ. Фон элемента управления отображается в виде сплошной цвет не узором.

      Этот параметр доступен только если **непрозрачный** также выбран параметр.

- **Добавление элемента управления на основе**

   Задает элемент управления должен быть основан на тип элемента управления Windows, добавив [CContainedWindow](ccontainedwindowt-class.md) данные-член к классу, реализующему элемент управления. Он также добавляет схему сообщений и функций обработчиков сообщений для обработки сообщений Windows для элемента управления. Выберите из списка тип элемента управления Windows, который вы хотите создать, если таковые имеются.

   - **Button**

   - **ListBox**

   - **SysAnimate32**

   - **SysListView32**

   - **ComboBox**

   - **RichEdit**

   - **SysDateTimePick32**

   - **SysMonthCal32**

   - **ComboBoxEx32**

   - **ScrollBar**

   - **SysHeader32**

   - **SysTabControl32**

   - **Правка**

   - **Статические**

   - **SysIPAddress32**

   - **SysTreeView32**

- **Прочее состояние**

   Задает дополнительные параметры внешнего вида и поведения элемента управления.

   - **Невидимым во время выполнения**: Задает элемент управления, чтобы быть невидимым во время выполнения. Невидимые элементы управления можно использовать для выполнения операций в фоновом режиме, например для срабатывания событий через определенные интервалы.

   - **Действует как кнопка**: Задает OLEMISC_ACTSLIKEBUTTON, бит в [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) перечисление, чтобы разрешить элементу управления действовать как кнопка. Если контейнер пометил сайта клиентского элемента управления как кнопка по умолчанию, этот параметр позволяет включить элемент управления кнопки отображаться как кнопка по умолчанию путем рисования самого полужирным фреймом. См. в разделе [CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) Дополнительные сведения.

   - **Выступает в качестве метки**: Задает OLEMISC_ACTSLIKELABEL бит в перечислении OLEMISC, чтобы включить элемент управления заменить контейнера. Контейнер определяет то, что делать с этим флагом, во всяком случае.

- **Другое**

   Задает дополнительные параметры поведения для элемента управления.

   - **Нормализовать DC**: Задает элемент управления, чтобы создать нормализованный контекст устройства при ее вызове для рисования самого себя. Это действие стандартизирует внешнего вида элемента управления, но оно Рисование менее эффективным.

   - **Только окно**: Указывает, что элемент управления не может быть без окон. Если этот параметр не выбран, элемент управления автоматически без окон в контейнерах, поддерживающих объекты и автоматически задается с окном в контейнерах, не поддерживающих объекты. При выборе этого параметра заставляет элемент управления задается с окном даже в контейнерах, поддерживающих объекты.

   - **Вставляемые**: Выберите этот параметр, чтобы элемент управления появился в **вставить объект** диалоговом приложений, таких как Word и Excel. Элемент управления затем может быть вставлен в любое приложение, и поддерживает внедренные объекты через это диалоговое окно.

## <a name="see-also"></a>См. также

[Мастер элементов управления ATL](../../atl/reference/atl-control-wizard.md)<br/>
[SUBEDIT образца: Порождает обычное поле ввода элемента управления стандартный Windows](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)
