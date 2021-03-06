---
title: Альтернативные варианты ввода вывода
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
ms.openlocfilehash: bc595b64c991ada8e958e71e13f8cb9d134adb8a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439693"
---
# <a name="inputoutput-alternatives"></a>Альтернативные варианты ввода и вывода

Visual C++ предоставляет несколько альтернатив для программирования ввода-вывода:

- Прямой ввод-вывод без буферизации на основе библиотеки времени выполнения С.

- Потоковый ввод-вывод на основе библиотеки времени выполнения ANSI C.

- Прямой ввод-вывод на консоль и в порт.

- Библиотека MFC.

- Стандартная библиотека Microsoft C++.

Классы iostream полезны для ввода-вывода форматированного текста с буферизацией. Они также могут использоваться для ввода-вывода без буферизации или двоичного ввода-вывода, если требуется интерфейс программирования C++ и принято решение отказаться от использования библиотеки Microsoft Foundation Class (MFC). Классы iostream — это объектно-ориентированная альтернатива вводу-выводу с помощью функций времени выполнения С.

Классы iostream можно использовать с операционной системой Microsoft Windows. Потоки строк и файлов работают без ограничений, но объекты потока символьного режима `cin`, `cout`, `cerr`, и `clog` не совместимы с графическим интерфейсом пользователя Windows. Также можно получать производные пользовательские классы потоков, которые взаимодействуют непосредственно со средой Windows.

## <a name="see-also"></a>См. также

[Что такое поток](../standard-library/what-a-stream-is.md)<br/>
