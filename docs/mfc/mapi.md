---
title: MAPI
ms.date: 11/04/2016
helpviewer_keywords:
- messaging [MFC], client applications
- enabling applications for MAPI [MFC]
- MAPI support in MFC
- e-mail [MFC], enabling
- mail [MFC], enabling your application
- MAPI, MFC
- enabling applications for mail [MFC]
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
ms.openlocfilehash: a5f60e1ba8c2b68ddca312859694f532e38da965
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279111"
---
# <a name="mapi"></a>MAPI

Для разработчиков приложений сообщение клиента, в этой статье описаны Microsoft программирования интерфейс MAPI (Messaging Application). MFC предоставляет поддержку для подмножества MAPI в классе `CDocument` , но не инкапсулировать весь API. Дополнительные сведения см. в разделе [поддержка MAPI в MFC](../mfc/mapi-support-in-mfc.md).

MAPI — это набор функций, которые используются приложениями, поддержкой электронной почты и электронной почты с поддержкой для создания, управления, передавать и хранить почтовые сообщения. Он дает разработчикам приложений средства, позволяющие определить задачи и содержимое сообщения электронной почты и обеспечивает гибкость в их управление хранимой почтовых сообщений. MAPI также предоставляет общий интерфейс, который разработчики приложений могут использовать для создания, электронную почту и электронной почты с поддержкой приложений, независимо от нижележащей системы обмена сообщениями.

Обмен сообщениями клиенты предоставляют работе с человеческим интерфейсом для взаимодействия с Microsoft Windows обмена сообщениями системы (WMS). Как правило, это взаимодействие включает запрашивать услуги у MAPI-совместимой поставщики, например хранилищ сообщений и адресные книги.

Дополнительные сведения о MAPI см. в разделе статьи в разделе руководства в Win32 MAPI (Messaging) пакета SDK для Windows.

## <a name="in-this-section"></a>В этом разделе

[Поддержка MAPI в MFC](../mfc/mapi-support-in-mfc.md)

## <a name="see-also"></a>См. также

[CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)<br/>
[CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)<br/>
[COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)
