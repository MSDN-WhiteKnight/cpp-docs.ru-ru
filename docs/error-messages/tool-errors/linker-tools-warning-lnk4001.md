---
title: Предупреждение средств компоновщика LNK4001
ms.date: 11/04/2016
f1_keywords:
- LNK4001
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
ms.openlocfilehash: 75ca9ec92bbba1c15efc11a731b3894ea03e33dd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651429"
---
# <a name="linker-tools-warning-lnk4001"></a>Предупреждение средств компоновщика LNK4001

объектные файлы не указаны; библиотеки, которые используются

Компоновщик передан один или несколько LIB-файлы, но не OBJ-файлы.

Так как компоновщик не может получить доступ к данным в LIB-файл, он может обращаться в OBJ-файл, это предупреждение означает, что необходимо явно указать другие параметры компоновщика. Например, может понадобиться указать [или компьютер,](../../build/reference/machine-specify-target-platform.md), [/OUT](../../build/reference/out-output-file-name.md), или [/Entry](../../build/reference/entry-entry-point-symbol.md) параметры.