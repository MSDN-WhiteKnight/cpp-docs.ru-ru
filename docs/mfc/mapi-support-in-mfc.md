---
title: Поддержка MAPI в MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, MAPI support
- MAPI support in MFC
- CDocument class [MFC], and MAPI
- OnUpdateFileSendMail method [MFC]
- MAPI, MFC
- OnFileSendMail method [MFC]
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
ms.openlocfilehash: 9b873ca1b3384adab6487fb3af9dc1401aaad12c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281646"
---
# <a name="mapi-support-in-mfc"></a>Поддержка MAPI в MFC

MFC предоставляет поддержку для подмножества из Microsoft программы интерфейс MAPI (Messaging Application) в классе `CDocument`. В частности `CDocument` содержит функции-члены, которые определяют, присутствует ли поддержка электронной почты на компьютере конечного пользователя и если да, включить команду Отправка почты, идентификатор которого стандартную команду — ID_FILE_SEND_MAIL. Функция обработчика MFC для этой команды позволяет пользователю отправить документ по электронной почте.

> [!TIP]
>  Несмотря на то, что MFC не инкапсулировать весь набор функций MAPI, можно по-прежнему вызывать MAPI функции напрямую, так же как можно вызывать функции Win32 API напрямую из программ MFC.

Предоставляя Отправка почты команда в приложении является очень просто. MFC предоставляет реализацию для упаковки документ (то есть `CDocument`-объект, производной от) как вложение и отправить его в виде электронной почты. Это вложение эквивалентно команду сохранения файла, которая сохраняет (сериализует) содержимое документа к почтовому сообщению. Эта реализация вызывает почтовый клиент на компьютере пользователя, чтобы дать пользователю возможность в поле адреса и добавить тему и текст сообщения в сообщение электронной почты. Пользователи видят их знаком почтовое приложение пользовательского интерфейса. Эта функция предоставляется на два `CDocument` функций-членов: `OnFileSendMail` и `OnUpdateFileSendMail`.

MAPI необходимо прочитать файл для отправки вложения. Если приложение поддерживает его файл данных открытым во время `OnFileSendMail` вызов функции, файл необходимо открыть с помощью режима общего доступа, который позволяет нескольким процессам, доступ к файлу.

> [!NOTE]
>  Переопределение `OnFileSendMail` для класса `COleDocument` правильно обрабатывает составные документы.

#### <a name="to-implement-a-send-mail-command-with-mfc"></a>Реализация команды Отправка почты с MFC

1. Редактор меню Visual C++ для добавления элемента меню, чей идентификатор команды — ID_FILE_SEND_MAIL.

   Этот идентификатор команды предоставляется платформой в AFXRES. З. Команды могут добавляться к все меню, но он обычно добавляется **файл** меню.

1. Вручную добавьте следующие схемы сообщений в документе:

   [!code-cpp[NVC_MFCDocView#9](../mfc/codesnippet/cpp/mapi-support-in-mfc_1.cpp)]

    > [!NOTE]
    >  Эта карта сообщений работает для документа, произведенный от любого `CDocument` или `COleDocument` — он собирал правильного базового класса в любом случае, несмотря на то, что в схеме сообщений — в документ в производном классе.

1. Выполните сборку своего приложения.

Если поддержка электронной почты, MFC позволяет элемента меню с `OnUpdateFileSendMail` и впоследствии обрабатывает команды с `OnFileSendMail`. Если поддержка электронной почты недоступен, MFC автоматически удаляет элемент меню, чтобы пользователь не увидит ее.

> [!TIP]
>  Вместо того чтобы вручную добавлять записи схемы сообщений как описано выше, можно использовать окно свойств класса для сопоставления сообщений функции. Дополнительные сведения см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md).

Дополнительные сведения см. в разделе [MAPI](../mfc/mapi.md) Обзор.

Дополнительные сведения о `CDocument` функции-члены, которые позволяют MAPI, см. в разделе:

- [CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)

- [CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)

- [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

## <a name="see-also"></a>См. также

[MAPI](../mfc/mapi.md)
