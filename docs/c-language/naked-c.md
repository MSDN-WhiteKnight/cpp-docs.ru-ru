---
title: Naked (C)
ms.date: 11/04/2016
helpviewer_keywords:
- naked keyword [C], storage-class attribute
- naked keyword [C]
- prolog code
- epilog code
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
ms.openlocfilehash: 519d7bceb700e9862f0d0025b755cf28fb0fbc0c
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56149782"
---
# <a name="naked-c"></a>Naked (C)

**Блок, относящийся только к системам Microsoft**

Атрибут класса хранения naked является расширением языка C для систем Microsoft. Код функций, объявленных с этим атрибутом, создается компилятором без кода пролога и эпилога. Благодаря этому вы можете вставить в качестве пролога и эпилога свой собственный код на языке ассемблера. Функции с атрибутом naked полезны для написания драйверов виртуальных устройств.

Дополнительные сведения см. в статье [Функции Naked](../c-language/naked-functions.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Расширенные атрибуты классов хранения в C](../c-language/c-extended-storage-class-attributes.md)
