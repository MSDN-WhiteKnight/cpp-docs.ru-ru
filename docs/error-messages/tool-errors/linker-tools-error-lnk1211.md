---
title: Ошибка средств компоновщика LNK1211
ms.date: 12/05/2017
f1_keywords:
- LNK1211
helpviewer_keywords:
- LNK1211
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
ms.openlocfilehash: 7c918cacb87460c2aad30285b750d9b170425534
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456151"
---
# <a name="linker-tools-error-lnk1211"></a>Ошибка средств компоновщика LNK1211

> сведения о предкомпилированном типе не найден. "*filename*" не скомпонован или перезаписан

*Filename* объектного файла, скомпилированного с помощью [/Yc](../../build/reference/yc-create-precompiled-header-file.md), не был указан в команде LINK или был перезаписан.

При создании отладочной библиотеки, использующей предкомпилированные заголовки, а также если задан **/Yc** и [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), Visual C++ создает файл предкомпилированного объект, который содержит отладочные данные. Эта ошибка возникает только при сохранении файла предкомпилированного объектов в библиотеке, используйте библиотеку, чтобы создавать исполняемый образ и объектных файлов, на которые ссылаются не содержат транзитивных ссылок на любой из функций, которые определяет предварительно скомпилированный объектный файл.

Чтобы обойти эту проблему двумя способами:

- Укажите [/Yd](../../build/reference/yd-place-debug-information-in-object-file.md) параметр компилятора, чтобы добавить отладочную информацию из файла предкомпилированного заголовка в каждый модуль объекта. Этот метод является менее предпочтительным, так как он обычно создает модули больших объектов, которые можно увеличить время, требуемое для компоновки приложения.

- Укажите [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) и передать имя любой произвольной строки, при создании файла предкомпилированного заголовка, который не содержит какие-либо определения функции. В данном случае компилятор для создания символа в файле предварительно скомпилированного объекта и выдает ссылку на этот символ в каждом файле объекта, используемому предкомпилированного файла заголовка, связанный с файлом предкомпилированного объекта.

При компиляции модуля с **/Yc** и **/Yl**, компилятор создает символ, аналогичную `__@@_PchSym_@00@...@symbol_name`, где многоточие (...) представляет строку символов, созданный компилятором и сохраняет его в модуль объекта. Все файлы исходного кода, которая компилируется с предкомпилированного заголовка относится к указанному символу, в результате чего компоновщик включает модуль объекта и его отладочную информацию из библиотеки.
