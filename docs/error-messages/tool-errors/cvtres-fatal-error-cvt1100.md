---
title: Неустранимая ошибка CVTRES CVT1100
ms.date: 11/04/2016
f1_keywords:
- CVT1100
helpviewer_keywords:
- CVT1100
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
ms.openlocfilehash: c7e65ccc79852ec99dd2406398fe1b3cdecacde7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429306"
---
# <a name="cvtres-fatal-error-cvt1100"></a>Неустранимая ошибка CVTRES CVT1100

дублировать ресурсов, тип: тип, имя: имя, язык: язык, флаги: флаги, размер: размер

Данный ресурс был указан более одного раза.

Эта ошибка может возникнуть, если компоновщик создает библиотеку типов, и вы не указали [/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) и ресурсов в проекте уже использует 1. В этом случае укажите /TLBID и укажите другой номер до 65535.