---
title: Целевые объекты
ms.date: 11/04/2016
helpviewer_keywords:
- targets, specifying in NMAKE
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
ms.openlocfilehash: f2163b6fdbd03c5cc1f5af307b5646f31d8a0c34
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50664222"
---
# <a name="targets"></a>Целевые объекты

В строке зависимость, укажите один или несколько целевых объектов, используя любое допустимое имя файла, имени каталога или [псевдоцелью](../build/pseudotargets.md). Несколько целевых объектов отделяются с один или несколько пробелов или знаков табуляции. Целевые объекты не чувствительны к регистру. Разрешено указание путей с именами файлов. Целевой объект не может превышать 256 символов. Если целевой объект, предшествующую ему один символ, используйте разделяющий пробел. в противном случае NMAKE интерпретирует сочетание знаков как спецификатор диска.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

[Псевдоцелевые объекты](../build/pseudotargets.md)

[Несколько целевых объектов](../build/multiple-targets.md)

[Кумулятивные зависимости](../build/cumulative-dependencies.md)

[Целевые объекты в нескольких блоках описания](../build/targets-in-multiple-description-blocks.md)

[Побочные эффекты зависимостей](../build/dependency-side-effects.md)

## <a name="see-also"></a>См. также

[Блоки описания](../build/description-blocks.md)