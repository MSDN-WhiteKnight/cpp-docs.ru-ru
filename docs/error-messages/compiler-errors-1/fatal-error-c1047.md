---
title: Неустранимая ошибка C1047
ms.date: 11/04/2016
f1_keywords:
- C1047
helpviewer_keywords:
- C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
ms.openlocfilehash: 053c4d828b3583d0e16ab8f4fe03a4b0bbed96f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663199"
---
# <a name="fatal-error-c1047"></a>Неустранимая ошибка C1047

Файл объекта или библиотеки "файл" был создан с более старой версией компилятора, чем другие объекты; выполните заново построение старых объектов и библиотек

Ошибка C1047 возникает в процессе компоновки файлов объектов или библиотек, собранных с помощью **/LTCG** , но только в тех случаях, когда для сборки этих объектных файлов или библиотек использовались разные версии набора инструментов Visual C++.

Это может произойти, если перейти к использованию новой версии компилятора, не выполнив заново сборку существующих объектных файлов или библиотек.

Чтобы устранить ошибку C1047, необходимо заново выполнить сборку всех объектных файлов и библиотек.