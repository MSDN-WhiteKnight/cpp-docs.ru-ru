---
title: Свойства копирования источников проекта (Linux C++)
ms.date: 9/26/2017
ms.assetid: 1a44230d-5dd8-4d33-93b4-e77e03e00150
ms.openlocfilehash: dd0a26db58265724f0a0e46c31365c97c00ff568
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477250"
---
# <a name="copy-sources-project-properties-linux-c"></a>Свойства копирования источников проекта (Linux C++)

Свойства, заданные на этой странице свойств, применяются ко всем файлам в проекте, за исключением тех, свойства уровня файла которых уже заданы.

Свойство. | Описание:
--- | ---
Источники для копирования | Задает источники для копирования в удаленную систему. Изменение этого списка может сдвинуть или иным способом повлиять на структуру каталогов, в которые файлы будут копироваться на удаленной системе.
Копирование источников | Определяет, требуется ли копировать источники в удаленную систему.
Дополнительные источники для копирования | Задает дополнительные источники для копирования в удаленную систему. При необходимости можно указать список в виде пар сопоставлений локальной и удаленной версии со следующим синтаксисом: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2, где локальный файл можно скопировать в указанное удаленное расположение в удаленной системе.
