---
title: .DOSSEG
ms.date: 08/30/2018
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 28b3e351030ee83693c0fec5568aacf9b4b77c27
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639443"
---
# <a name="dosseg"></a>.DOSSEG

Упорядочивает сегменты в соответствии с соглашением сегмент MS-DOS: код, во-первых, затем разделяет не в DGROUP и затем разделяет в DGROUP.

## <a name="syntax"></a>Синтаксис

> .DOSSEG

## <a name="remarks"></a>Примечания

Сегменты в DGROUP выполняйте в указанном порядке: сегменты не в BSS или СТЕК, а затем BSS сегментов и, наконец, сегменты стека. В основном используется для обеспечения поддержки CodeView в изолированных программ MASM. Совпадение с кодом [DOSSEG](../../assembler/masm/dosseg.md).

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>