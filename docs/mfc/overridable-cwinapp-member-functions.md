---
title: Переопределяемые функции-члены CWinApp
ms.date: 11/04/2016
f1_keywords:
- CWinApp
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
ms.openlocfilehash: 35db009f86a0cb984f70a349a3ecdd93bfefb0f0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261249"
---
# <a name="overridable-cwinapp-member-functions"></a>Переопределяемые функции-члены CWinApp

[CWinApp](../mfc/reference/cwinapp-class.md) предоставляет несколько ключевых функций является переопределяемым элементом (`CWinApp` переопределяет эти члены из класса [CWinThread](../mfc/reference/cwinthread-class.md), из которого `CWinApp` производный):

- [InitInstance](../mfc/initinstance-member-function.md)

- [Выполнить](../mfc/run-member-function.md)

- [ExitInstance](../mfc/exitinstance-member-function.md)

- [OnIdle](../mfc/onidle-member-function.md)

Единственным `CWinApp` функцию-член, необходимо переопределить `InitInstance`.

## <a name="see-also"></a>См. также

[CWinApp: Класс приложений](../mfc/cwinapp-the-application-class.md)
