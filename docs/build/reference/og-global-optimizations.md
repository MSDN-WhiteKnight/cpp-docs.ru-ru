---
title: /Og (Виды глобальной оптимизации)
ms.date: 09/22/2017
f1_keywords:
- VC.Project.VCCLCompilerTool.GlobalOptimizations
- /og
helpviewer_keywords:
- -Og compiler option [C++]
- global optimizations compiler option [C++]
- automatic register allocation
- /Og compiler option [C++]
- loop structures, optimizing
- common subexpression elimination
- Og compiler option [C++]
ms.assetid: d10630cc-b9cf-4e97-bde3-8d7ee79e9435
ms.openlocfilehash: d6913be5bc02755730ffb6205e9f34811c9a5dbb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431945"
---
# <a name="og-global-optimizations"></a>/Og (Виды глобальной оптимизации)

Не рекомендуется. Предоставляет локальные и глобальные оптимизации, автоматическое выделение регистров и оптимизацию цикла. Мы рекомендуем использовать либо [/O1 (минимизировать размер)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) или [/O2 (максимизировать скорость)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) вместо этого.

## <a name="syntax"></a>Синтаксис

> /Og

## <a name="remarks"></a>Примечания

**/Og** является устаревшим. Эти оптимизации обычно включены по умолчанию. Дополнительные сведения об оптимизации, см. в разделе [/O1, / O2 (минимизировать размер, максимизировать скорость)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) или [/Ox (Включение наиболее видов оптимизации скорости)](../../build/reference/ox-full-optimization.md).

Следующие оптимизации можно найти в разделе **/Og**:

- Локальные и глобальные исключение общей части выражения

   В этой оптимизации значение общей части выражения вычисляется один раз. В следующем примере если значения `b` и `c` не изменяются для трех выражений, компилятор может назначить вычисление `b + c` во временную переменную и заменить переменную для `b + c`:

    ```C
    a = b + c;
    d = b + c;
    e = b + c;
    ```

   Для локального оптимизации общей части выражения компилятор проверяет короткие участки кода для общих частей выражения. Для глобальной оптимизации общей части выражения компилятор выполняет поиск всего функций для общих частей выражения.

- Автоматическое выделение регистров

   Эта оптимизация позволяет компилятору хранения часто используемых переменных и подвыражений в регистрах; `register` ключевого слова пропускается.

- Оптимизации цикла

   Эта оптимизация удаляет инвариантного частей выражения из тела цикла. Оптимальной цикл содержит только выражения, значения которых изменяются через каждого выполнения цикла. В следующем примере выражение `x + y` остается неизменным в теле цикла:

    ```C
    i = -100;
    while( i < 0 ) {
        i += x + y;
    }
    ```

   После оптимизации `x + y` вычисляется один раз, а не при каждом выполнении цикла:

    ```C
    i = -100;
    t = x + y;
    while( i < 0 ) {
        i += t;
    }
    ```

   Оптимизации цикла является значительно более эффективной, если компилятор может предположить отсутствие псевдонимов, что заданное с помощью [__restrict](../../cpp/extension-restrict.md), [noalias](../../cpp/noalias.md), или [ограничить](../../cpp/restrict.md).

   > [!NOTE]
   > Можно включить или отключить глобальная оптимизация для отдельных функций, функции с помощью `optimize` pragma вместе с `g` параметр.

Дополнительные сведения см. в разделе [/Oi (Создание встроенных функций)](../../build/reference/oi-generate-intrinsic-functions.md) и [/Ox (Включение наиболее видов оптимизации скорости)](../../build/reference/ox-full-optimization.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в **Дополнительные параметры** поле.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)

[Параметры компилятора](../../build/reference/compiler-options.md)

[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)