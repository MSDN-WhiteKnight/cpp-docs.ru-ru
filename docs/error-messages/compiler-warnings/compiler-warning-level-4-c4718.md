---
title: Предупреждение компилятора (уровень 4) C4718
ms.date: 11/04/2016
f1_keywords:
- C4718
helpviewer_keywords:
- C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
ms.openlocfilehash: c313e26af5f5b17db9c7d001a705ff7211461c2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573703"
---
# <a name="compiler-warning-level-4-c4718"></a>Предупреждение компилятора (уровень 4) C4718

"вызов_функции": рекурсивный вызов не имеет побочных эффектов; удаление

Функция содержит рекурсивный вызов, но с другой стороны побочные эффекты отсутствуют. Вызов этой функции удаляется. Это повлияет на поведение программы, но не на ее правильность. В то время как оставленный вызов может привести к исключению переполнения стека, удаление этого вызова устраняет такую возможность.