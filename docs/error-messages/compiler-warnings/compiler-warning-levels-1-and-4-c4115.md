---
title: Предупреждение компилятора (уровни 1 и 4) C4115
ms.date: 11/04/2016
f1_keywords:
- C4115
helpviewer_keywords:
- C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
ms.openlocfilehash: 20e44eba3b6f6079e6f37b7cf33fa530a996e829
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462963"
---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>Предупреждение компилятора (уровни 1 и 4) C4115

"тип": определение именованного типа в круглых скобках

Указанный символ используется для определения структуры, объединения или перечисляемого типа в выражении в скобках. Область определения может быть непредусмотренной.

В вызове функции C определение имеет глобальную область. В вызове C++ определение имеет ту же область, что и вызываемая функция.

Это предупреждение также может быть вызвано деклараторами внутри скобок (такими как прототипы), которые не являются выражениями в скобках.

Это предупреждение уровня 1 для программ C++ и программ C, скомпилированных в режиме совместимости с ANSI (/Za). В противном случае оно имеет уровень 3.