---
title: Стили окна фрейма (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
ms.openlocfilehash: cade8e7e50779437feb73a94058dc62118c03c10
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274652"
---
# <a name="frame-window-styles-c"></a>Стили окна фрейма (C++)

Окна фрейма, вы получаете с помощью платформы подходят для большинства программ, но вы получаете дополнительную гибкость при помощи дополнительных функций [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) и глобальные функции MFC [AfxRegisterWndClass ](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow` функция-член из `CWnd`.

Если применить **WS_HSCROLL** и **WS_VSCROLL** стили для фрейма главного окна, вместо этого применяются к **MDICLIENT** окно, поэтому пользователи смогут прокручивать **MDICLIENT** области.

Если окна **FWS_ADDTOTITLE** бит стиля имеет значение (который по умолчанию он разрешен), представление окна фрейма сообщает, какой заголовок, отображаемый в заголовке окна на основе имени представления документа.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Управление дочерними окнами MDI (MDICLIENT)](../mfc/managing-mdi-child-windows.md), окна внутри фрейма MDI, содержащий дочерние окна MDI

- [Изменение стилей окна, созданного MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

- [Стили окна](../mfc/reference/styles-used-by-mfc.md#window-styles)

## <a name="see-also"></a>См. также

[Окна фрейма](../mfc/frame-windows.md)
