---
title: Предупреждение компилятора (уровень 3) C4278
ms.date: 08/27/2018
f1_keywords:
- C4278
helpviewer_keywords:
- C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
ms.openlocfilehash: 8c5c15105581602566116d3ed82b89a6337435c9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627634"
---
# <a name="compiler-warning-level-3-c4278"></a>Предупреждение компилятора (уровень 3) C4278

> "*идентификатор*": идентификатор в библиотеке типов "*tlb*" уже является макроопределением; используйте квалификатор «rename»

При использовании [#import](../../preprocessor/hash-import-directive-cpp.md), идентификатор в библиотеке типов, импортируемой пытается объявить идентификатор *идентификатор*. Тем не менее это уже допустимый символ.

Используйте `#import` **Переименовать** атрибута позволяют назначить псевдоним для символа в библиотеке типов.