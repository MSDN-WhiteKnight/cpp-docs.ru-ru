---
title: Общие вопросы использования Visual C++ для 64-разрядных систем
ms.date: 11/04/2016
helpviewer_keywords:
- 64-bit programming [C++], migration
- 64-bit compiler [C++], migration
- porting 32-bit code to 64-bit code
- upgrading Visual C++ applications, 32-bit code
- migration [C++], 64-bit code issues
- 32-bit code porting [C++]
- 64-bit applications [C++]
- 64-bit compiler [C++], porting 32-bit code
- Win64 [C++]
ms.assetid: d17fb838-7513-4e2d-8b27-a1666f17ad76
ms.openlocfilehash: 1eb5a7f8d708d16241f1637269f31563378f084d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468774"
---
# <a name="common-visual-c-64-bit-migration-issues"></a>Общие вопросы использования Visual C++ для 64-разрядных систем

При использовании Visual C++ для создания приложений, запуск которых планируется в 64-разрядной версии ОС Windows, следует знать следующее.

- В 64-разрядных версиях Windows `int` и `long` являются 32-разрядными значениями. В программах, которые планируется компилировать для 64-разрядных платформ, не следует назначать указателям 32-разрядные переменные. В 64-разрядных платформах указатели являются 64-разрядными, поэтому значение указателя будет усечено, если назначить ему 32-разрядную переменную.

- `size_t`, `time_t`, и `ptrdiff_t` являются 64-разрядными значениями в операционных системах Windows 64-разрядной.

- В версиях Visual C++ до Visual C++ 2005 `time_t` является 32-разрядным значением в 32-разрядных версиях Windows. Теперь `time_t` по умолчанию представляет собой 64-разрядное целое число. Дополнительные сведения см. в разделе [управление временем](../c-runtime-library/time-management.md).

   Следует знать, где ваш код принимает значение `int` и обрабатывает его как значение `size_t` или `time_t`. Разрядность может превысить 32 бита. В этом случае данные будут усечены при их возвращении в хранилище `int`.

Модификатор %x `printf` (шестнадцатеричный формат `int`) не будет действовать в 64-разрядных версиях Windows ожидаемым образом. Он будет обрабатывать только первые 32 бита передаваемого ему значения.

- Для отображения 32-разрядных целочисленных типов в шестнадцатеричном формате используйте модификатор %I32x.

- Для отображения 64-разрядных целочисленных типов в шестнадцатеричном формате используйте модификатор %I64x.

- Модификатор %p (шестнадцатеричный формат для указателя) в 64-разрядных версиях Windows действует правильно.

Дополнительные сведения:

- [Параметры компилятора](../build/reference/compiler-options.md)

- [Советы по миграции](/windows/desktop/WinProg64/migration-tips)

## <a name="see-also"></a>См. также

[Настройка Visual C++ для 64-разрядных целевых объектов с архитектурой x64](../build/configuring-programs-for-64-bit-visual-cpp.md)<br/>
[Руководство по переносу и обновлению Visual C++](../porting/visual-cpp-porting-and-upgrading-guide.md)