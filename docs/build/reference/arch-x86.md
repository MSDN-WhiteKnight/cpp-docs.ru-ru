---
title: /arch (x86)
ms.date: 11/04/2016
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
ms.openlocfilehash: fb115d564ca24ff29e120e0d8c25e0dbe28024cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549712"
---
# <a name="arch-x86"></a>/arch (x86)

Задает архитектуру для создания кода на платформе x86. Также см. в разделе [/arch (x64)](../../build/reference/arch-x64.md) и [/arch (ARM)](../../build/reference/arch-arm.md).

## <a name="syntax"></a>Синтаксис

```
/arch:[IA32|SSE|SSE2|AVX|AVX2]
```

## <a name="arguments"></a>Аргументы

**/ arch: IA32**<br/>
Указывает на то, что расширенные инструкции не используются. Также указывает на использование инструкций x87 для вычислений с плавающей запятой.

**/arch:SSE**<br/>
Позволяет использовать инструкции SSE.

**/ arch: SSE2**<br/>
Позволяет использовать инструкции SSE2. Это инструкция по умолчанию на x86 платформ, если не **/arch** параметра.

**/ arch: AVX**<br/>
Позволяет использовать инструкции Intel AVX.

**/ arch: avx2**<br/>
Позволяет использовать инструкции Intel AVX 2.

## <a name="remarks"></a>Примечания

Наборы инструкций SSE и SSE2 имеются в различных процессорах Intel и AMD. Инструкции AVX существуют в процессорах Intel Sandy Bridge и процессорах AMD Bulldozer. Инструкции AVX2 поддерживаются процессорами Intel Haswell и Broadwell, а также процессорами на основе AMD Excavator.

`_M_IX86_FP`, `__AVX__` И `__AVX2__` макросы указывают, какой, если таковые имеются, **/arch** использовался параметр компилятора. Для получения дополнительной информации см. [Predefined Macros](../../preprocessor/predefined-macros.md). **/Arch: avx2** параметр и `__AVX2__` макрос появились в Visual Studio 2013 с обновлением 2 версии 12.0.34567.1.

Оптимизатор выбирает, где и как использовать SSE и SSE2 при **/arch** указан. Наборы инструкций SSE и SSE2 будут использоваться при некоторых скалярных вычислениях с плавающей запятой, если будет обнаружено, что регистры и инструкции SSE или SSE2 дают выигрыш во времени по сравнению со стеком регистров с плавающей запятой x87. В результате код будет использовать для вычислений с плавающей запятой как инструкции x87, так и SSE/SSE2. Кроме того, с помощью **/arch: SSE2**, инструкции SSE2 может использоваться для некоторых операций 64-разрядное целое число.

В дополнение к наборам инструкций SSE и SSE2 компилятор также использует другие инструкции, имеющиеся в редакциях процессоров, поддерживающих SSE и SSE2. Примером может служить инструкция CMOV, которая впервые появилась в редакции Pentium Pro процессоров Intel.

Поскольку x86 компилятор создает код, использующий инструкции SSE2 по умолчанию, необходимо указать **/arch: IA32** Чтобы отключить создание инструкций SSE и SSE2 для x86 процессоров.

**/ arch** только влияет на создание кода для собственных функций. При использовании [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) для компиляции, **/arch** не влияет на создание кода для управляемых функций.

**/ arch** и [/QIfist](../../build/reference/qifist-suppress-ftol.md) нельзя применять к одной единице компиляции. В частности, если вы не используете `_controlfp` для изменения контрольного слова FP, то код запуска времени выполнения установит 53 бита для поля управления точностью контрольного слова FPU x87. Поэтому каждая операция с типами float и double в выражении выполняется с 53-разрядной мантиссой и 15-разрядной экспонентой. Тем не менее, все операции SSE одиночной точности используют 24-разрядную значащую часть и 8-разрядную экспоненту, а операции SSE2 двойной точности используют 53-разрядную значимую часть и 11-разрядную экспоненту. Дополнительные сведения см. в разделе [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md). Подобные отличия возможны в пределах одного дерева выражения, но не в том случае, когда после каждой части выражения стоит пользовательское присваивание. Рассмотрим следующий пример.

```cpp
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.
```

Сравните:

```cpp
t = f1 * f2;   // Do f1 * f2, round to the type of t.
r = t + d;     // This should produce the same overall result
               // whether x87 stack is used or SSE/SSE2 is used.
```

### <a name="to-set-this-compiler-option-for-avx-avx2-ia32-sse-or-sse2-in-visual-studio"></a>Установка параметра компилятора для AVX, AVX2, IA32, SSE или SSE2 в Visual Studio

1. Откройте **страницы свойств** диалоговое окно для проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации**, **C/C++** папки.

1. Выберите **создание кода** страницу свойств.

1. Изменить **включить расширенный набор инструкций** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>См. также

[/arch (минимальная архитектура ЦПУ)](../../build/reference/arch-minimum-cpu-architecture.md)<br/>
[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)