---
title: /fp (определение поведения с плавающей запятой)
ms.date: 11/09/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.floatingPointModel
- VC.Project.VCCLWCECompilerTool.FloatingPointExceptions
- /fp
- VC.Project.VCCLWCECompilerTool.floatingPointModel
- VC.Project.VCCLCompilerTool.FloatingPointExceptions
helpviewer_keywords:
- -fp compiler option [C++]
- /fp compiler option [C++]
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
ms.openlocfilehash: c571bf104fd7e8f6a287c3dd35c444d904b4b7e8
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54894098"
---
# <a name="fp-specify-floating-point-behavior"></a>/fp (определение поведения с плавающей запятой)

Указывает, как компилятор обрабатывает выражения с плавающей запятой, оптимизации и исключения. **/FP** параметры определяют ли созданный код позволяет среду с плавающей запятой изменяется на режим округления, маски исключения и subnormal поведение и ли проверки состояний с плавающей запятой возвращают текущее, точный результаты. Он управляет ли компилятор создает код, который поддерживает операцию источника и выражение упорядочивания и соответствует стандарту для распространения NaN, или если вместо этого он создает более эффективный код, который может изменить порядок или объединить операций и использовать упрощение алгебраические преобразования, которые не допускаются в стандарте.

## <a name="syntax"></a>Синтаксис

> **/ fp:**[**точное** | **strict** | **быстрый** | **за исключением**[ **-**]]

### <a name="arguments"></a>Аргументы

#### <a name="precise"></a>Точный

По умолчанию компилятор использует **/fp: точное** поведение.

В разделе **/fp: точное** компилятор сохраняет исходное выражение упорядочения и округления свойства код с плавающей запятой, когда он создает и оптимизирует код объекта для целевого компьютера. Компилятор выполняет округление исходной точности кода в четырех точках, определенных во время вычисления выражения: в назначения, при приведении типов, при вызове функции передается аргумент с плавающей запятой, а в том случае, когда значение с плавающей запятой возвращается из вызова функции. Промежуточные результаты вычислений может выполняться в точности машины. Приведении типов можно использовать для явного округление промежуточных вычислений.

Компилятор не выполняет алгебраические преобразования выражений с плавающей запятой, например повторного связывания или распространения, пока преобразование гарантированно побитовое идентичные результат.
Выражения, включающие специальных значений (NaN, + бесконечность, - infinity, -0.0) обрабатываются в соответствии со спецификациями IEEE-754. Например `x != x` принимает значение **true** Если x имеет значение NaN. С плавающей запятой *сокращения*, то есть машинных инструкций, которые объединяют операции с плавающей запятой, может быть создан в разделе **/fp: точное**.

Компилятор создает код предназначен для выполнения в [среду с плавающей запятой по умолчанию](#the-default-floating-point-environment) и предполагается, что среду с плавающей запятой не получить доступ и не изменяются во время выполнения. То есть он предполагает, что код не снять маску исключения с плавающей запятой, чтения или записи регистров с плавающей запятой состояние или изменить режимы округления.

Если ваш код с плавающей запятой зависит от порядка операций и выражений в инструкциях с плавающей запятой (например, в том случае, если не важен ли `a * b + a * c` вычисляется как `(b + c) * a` или `2 * a` как `a + a`), рассмотрите возможность [/fp:fast](#fast) параметр, который может создавать код быстрее. Если ваш код и зависит от порядка операций и выражений и обращается к или изменяет среду с плавающей запятой (например, для изменения режима округления или для перехвата исключения с плавающей запятой), используйте [/fp: strict](#strict).

#### <a name="strict"></a>strict

**/ fp: strict** имеет поведения, схожего с **/fp: точное**, то есть компилятор сохраняет порядок источника и округления свойства код с плавающей запятой, когда он создает и оптимизирует объекта кода для целевого компьютера , а также отслеживается стандарте при обработке специальных значений. Кроме того программа может безопасно получить доступ к или изменить среду с плавающей запятой во время выполнения.

В разделе **/fp: strict**, компилятор создает код, который позволяет программе безопасно снять маску исключения с плавающей запятой, чтения или записи регистров с плавающей запятой состояние или изменить режимы округления. Оно округляется до точности исходного кода в четырех точках, определенных во время вычисления выражения: в назначения, при приведении типов, при вызове функции передается аргумент с плавающей запятой, а в том случае, когда значение с плавающей запятой возвращается из вызова функции. Промежуточные результаты вычислений может выполняться в точности машины. Приведении типов можно использовать для явного округление промежуточных вычислений. Компилятор не выполняет алгебраические преобразования выражений с плавающей запятой, например повторного связывания или распространения, пока преобразование гарантированно побитовое идентичные результат. Выражения, включающие специальных значений (NaN, + бесконечность, - infinity, -0.0) обрабатываются в соответствии со спецификациями IEEE-754. Например `x != x` принимает значение **true** Если x имеет значение NaN. С плавающей запятой сокращения не создаются в **/fp: strict**.

**/ fp: strict** большим дороже, чем **/fp: точное** потому, что компилятор должен вставлять дополнительные инструкции для обработки исключений и разрешить программам доступ или изменение среду с плавающей запятой в Среда выполнения. Если код не использует эту возможность, но требует упорядочения исходного кода и округления или зависит от специальных значений, используйте **/fp: точное**. В противном случае рассмотрите возможность использования **/fp:fast**, который может создавать код быстрее и занимает меньше места.

#### <a name="fast"></a>Быстрая

**/Fp:fast** параметр позволяет компилятору переупорядочить, объединения или упрощения операций с плавающей запятой, чтобы оптимизировать код с плавающей запятой для скорости и пространства. Компилятор может опускаться округление в операторах присваивания, приведении типов или вызовы функций. Он может изменять порядок операций или выполнять алгебраические преобразования, например, с помощью ассоциативности и дистрибутивности законы, даже если таких преобразований приведут заметно округления по-разному. Из-за такой оптимизации улучшенные результат некоторых вычислений с плавающей запятой может отличаться от созданных другими **/FP** параметры. Специальные значения (NaN, + бесконечность, - infinity, -0.0) не могут быть распространены или ведут себя строго в соответствии со стандартом IEEE-754. С плавающей запятой сокращения, которые могут быть созданы в разделе **/fp:fast**. Компилятор по-прежнему ограничивается базовой архитектуры в разделе **/fp:fast**, и Дополнительная оптимизация могут быть доступны посредством использования платформы [/arch](../../build/reference/arch-minimum-cpu-architecture.md) параметр.

В разделе **/fp:fast**, компилятор создает код, должен работать в среде с плавающей запятой по умолчанию и предполагается, что среду с плавающей запятой не обращаться и изменять во время выполнения. То есть он предполагает, что код не снять маску исключения с плавающей запятой, чтения или записи регистров с плавающей запятой состояние или изменить режимы округления.

**/fp:fast** предназначен для программ, которые не требуют строгой упорядочение кода и округление выражений с плавающей запятой, а не следует полагаться на стандартные правила для обработки специальных значений, таких как значение NaN. Если ваш код с плавающей запятой требуется обеспечение сохранности исходного кода, упорядочение и округления или зависит от стандартного поведения специальных значений, используйте [/fp: точное](#precise). Если ваш код открывает или изменяет среду с плавающей запятой для изменения режима округления, снять маску исключения с плавающей запятой, или проверить состояние с плавающей запятой, используйте [/fp: strict](#strict).

#### <a name="except"></a>except

**/Fp: except** параметр создает код для гарантирует возникновения любой немаскированные исключения с плавающей запятой в точке они встречаются, и что вызываются без дополнительных исключений с плавающей запятой. По умолчанию **/fp: strict** позволяет **/fp: except**, и **/fp: точное** не поддерживает. **/Fp: except** параметр не совместим с **/fp:fast**. Параметр можно отключить явным образом, нам о **/fp: except-**.

Обратите внимание, что **/fp: except** не приводит к включению любые исключения с плавающей запятой сама по себе, но он необходим для исключения с плавающей запятой в программах. См. в разделе [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) сведения о том, как включить исключения с плавающей запятой.

## <a name="remarks"></a>Примечания

Несколько **/FP** параметры можно указать в одной командной строке компилятора. Только один из **/fp: strict**, **/fp:fast**, и **/fp: точное** параметры могут быть фактически за раз. Если более чем один из этих параметров указан в командной строке, приоритет имеет параметр более поздней версии, и компилятор выдает предупреждение. **/Fp: strict** и **/fp: except** параметры несовместимы с **/CLR**.

[/Za](../../build/reference/za-ze-disable-language-extensions.md) (совместимости с ANSI) параметр не совместим с **/FP**.

### <a name="using-pragmas-to-control-floating-point-behavior"></a>С помощью директивы pragma, для управления поведением с плавающей запятой

Компилятор предоставляет три директивы pragma для переопределения поведения с плавающей запятой, указанные в командной строке: [float_control](../../preprocessor/float-control.md), [fenv_access](../../preprocessor/fenv-access.md), и [fp_contract](../../preprocessor/fp-contract.md). Эти директивы pragma можно использовать для контроля поведения с плавающей запятой на уровне функции, не внутри функции. Обратите внимание, что эти директивы pragma не соответствуют непосредственно к **/FP** параметры. В этой таблице показаны как **/FP** прагмы и параметры сопоставляются друг с другом. Дополнительные сведения см. в документации для отдельных параметров и директивы pragma.

||float_control(precise)|float_control(except)|fenv_access|fp_contract|
|-|-|-|-|-|
|**/fp:fast**|Отключение|Отключение|Отключение|вкл.|
|**/ fp: точное**|вкл.|Отключение|Отключение|вкл.|
|**/ fp: strict**|вкл.|вкл.|вкл.|Отключение|

### <a name="the-default-floating-point-environment"></a>Точка среда с плавающей запятой по умолчанию

При инициализации процесса *плавающей точки среды по умолчанию* имеет значение. Эта среда маскирует исключений для всех с плавающей запятой, задает режим округления в округление до ближайшего (`FE_TONEAREST`), сохраняет subnormal (denormal) значений, используется точность по умолчанию значащей части числа (мантиссы) для **float**, **двойные**, и **long double** значений, а там, где поддерживается, задает элемент управления, бесконечность режим по умолчанию аффинной.

### <a name="floating-point-environment-access-and-modification"></a>Среду с плавающей запятой доступа и изменения

Среда выполнения Microsoft Visual C++ предоставляет несколько функций для доступа и изменения среду с плавающей запятой. К ним относятся [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md), [_clearfp](../../c-runtime-library/reference/clear87-clearfp.md), и [_statusfp](../../c-runtime-library/reference/status87-statusfp-statusfp2.md) и их вариантов. Для обеспечения правильной программы поведения в том случае, когда ваш код открывает или изменяет среду с плавающей запятой, `fenv_access` должна быть включена, либо путем **/fp: strict** параметр или с помощью `fenv_access` директивы pragma, для этих функций для иметь эффекта. При `fenv_access` — не включено, доступ или изменение среду с плавающей запятой может привести непредвиденное поведение программы: код не может учитывать запрошенные изменения в среду с плавающей запятой; могут не разглашать регистры состояний с плавающей запятой Ожидаемое или текущего результатов; и может возникнуть непредвиденные исключения с плавающей запятой, или ожидаемые исключения с плавающей запятой может не произойти.

Когда ваш код открывает или изменяет среду с плавающей запятой, будьте внимательны при объединении кода где `fenv_access` включено с кодом, который не имеет `fenv_access` включена. В коде где `fenv_access` не включена, компилятор предполагает, что он фактически являлся среду с плавающей запятой по умолчанию платформы и состояний с плавающей запятой не получить доступ и не изменяются. Рекомендуется сохранять и восстанавливать локальную среду с плавающей запятой в состояние по умолчанию, прежде чем управление передается в функцию, которая не имеет `fenv_access` включена. В этом примере показано, как `float_control` директивы pragma можно задать и восстановить:

```cpp
#pragma float_control(strict, on, push)
// Code that uses /fp:strict mode
#pragma float_control(pop)
```

### <a name="floating-point-rounding-modes"></a>С плавающей запятой режима округления

В разделе оба **/fp: точное** и **/fp:fast** компилятор создает код, должен работать в среде с плавающей запятой по умолчанию и предполагается, что среда не обращаться и изменять во время выполнения. То есть он предполагает, что код не снять маску исключения с плавающей запятой, чтения или записи регистров с плавающей запятой состояние или изменить режимы округления.  Тем не менее некоторые программы необходимо изменить среду с плавающей запятой. Например этот пример вычисляет границы ошибка умножения с плавающей запятой путем изменения с плавающей запятой режима округления:

```cpp
// fp_error_bounds.cpp
#include <iostream>
#include <limits>
using namespace std;

int main(void)
{
    float a = std::<float>::max();
    float b = -1.1;
    float cLower = 0.0;
    float cUpper = 0.0;
    unsigned int control_word = 0;
    int err = 0;

    // compute lower error bound.
    // set rounding mode to -infinity.
    err = _controlfp_s(&control_word, _RC_DOWN, _MCW_RC);
    if (err)
    {
        cout << "_controlfp_s(&control_word, _RC_DOWN, _MCW_RC) failed with error:" << err << endl;
    }  
    cLower = a * b;

    // compute upper error bound.
    // set rounding mode to +infinity.
    err = _controlfp_s(&control_word, _RC_UP, _MCW_RC);
    if (err)
    {
        cout << "_controlfp_s(&control_word, _RC_UP, _MCW_RC) failed with error:" << err << endl;
    }
    cUpper = a * b;

    // restore default rounding mode.
    err = _controlfp_s(&control_word, _CW_DEFAULT, _MCW_RC);
    if (err)
    {
        cout << "_controlfp_s(&control_word, _CW_DEFAULT, _MCW_RC) failed with error:" << err << endl;
    }
    // display error bounds.
    cout << "cLower = " << cLower << endl;
    cout << "cUpper = " << cUpper << endl;
    return 0;
}
```

Так как компилятор предполагает, что по умолчанию с плавающей запятой среда точки в разделе **/fp:fast** и **/fp: точное** бесплатно игнорирует вызовы к `_controlfp_s`. Например, при компиляции с помощью обоих **/O2** и **/fp: точное** для x86 архитектуры, границы не вычисляются и пример программы выводится следующий результат:

```Output
cLower = -inf
cUpper = -inf
```

При компиляции с использованием как **/O2** и **/fp: strict** для x86 архитектуры, пример программы выводится следующий результат:

```Output
cLower = -inf
cUpper = -3.40282e+38
```

### <a name="floating-point-special-values"></a>Специальные значения с плавающей запятой

В разделе **/fp: точное** и **/fp: strict**, выражения, включающие специальных значений (NaN, + бесконечность, - infinity, -0.0) ведут себя в соответствии со спецификациями IEEE-754. В разделе **/fp:fast**, поведение этих специальных значений может не соответствовать IEEE-754.

В этом примере показано различное поведение специальные значения в разделе **/fp: точное**, **/fp: strict** и **/fp:fast**:

```cpp
// fp_special_values.cpp
#include <stdio.h>
#include <cmath>

float gf0 = -0.0;

int main()
{
    float f1 = INFINITY;
    float f2 = NAN;
    float f3 = -INFINITY;
    bool a, b;
    float c, d, e;
    a = (f1 == f1);
    b = (f2 == f2);
    c = (f1 - f1);
    d = (f2 - f2);
    printf("INFINITY == INFINITY : %d\n", a);
    printf("NAN == NAN           : %d\n", b);
    printf("INFINITY - INFINITY  : %f\n", c);
    printf("NAN - NAN            : %f\n", d);

    e = gf0 / abs(f3);
    printf("std::signbit(-0.0/-INFINITY): %d\n", std::signbit(c));
    return 0;
}
```

При компиляции с **/O2** **/fp: точное** или **/O2** **/fp: strict** для x86 архитектуры, выходные данные будут согласованы с IEEE-754 Спецификация:

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 0
INFINITY - INFINITY  : -nan(ind)
NAN - NAN            : -nan(ind)
std::signbit(-0.0/-INFINITY): 1
```

При компиляции с **/O2** **/fp:fast** для x86 архитектуры, выходные данные не согласованы с IEEE-754:

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 1
INFINITY - INFINITY  : 0.000000
NAN - NAN            : 0.000000
std::signbit(-0.0/-INFINITY): 0
```

### <a name="floating-point-algebraic-transformations"></a>С плавающей запятой алгебраические преобразования

В разделе **/fp: точное** и **/fp: strict**, компилятор не выполняет математические преобразований, пока преобразование гарантированно побитовое идентичные результат. Компилятор может выполнять такие преобразования в разделе **/fp:fast**. Например, выражение `a * b + a * c` в образец функции `algebraic_transformation` может быть скомпилирован в `a * (b + c)` под **/fp:fast**. Такие преобразования не выполняются в разделе **/fp: точное** или **/fp: strict**, и компилятор создает `a * b + a * c`.

```cpp
float algebraic_transformation (float a, float b, float c)
{
    return a * b + a * c;
}
```

### <a name="floating-point-explicit-casting-points"></a>Точки с плавающей запятой явное приведение типов

В разделе **/fp: точное** и **/fp: strict**, компилятор округляется до точности исходного кода в четырех точках, определенных во время вычисления выражения: в назначения, при приведении типов, когда аргумент с плавающей запятой передается, вызов функции, а при вызове функции возвращается значение с плавающей запятой. Приведении типов можно использовать для явного округление промежуточных вычислений. В разделе **/fp:fast**, компилятор не создает явные приведения в этих точках, чтобы гарантировать точность исходного кода. В этом образце демонстрируется поведение в разных **/FP** параметры:

```cpp
float casting(float a, float b)
{
    return 5.0*((double)(a+b));
}
```

При компиляции с помощью **/O2** **/fp: точное** или **/O2** **/fp: strict**, вы увидите, что в обоих вставляются явное приведение типов приведение типа и на функции возвращают точки в созданном коде для x64 архитектуры:

```asm
        addss    xmm0, xmm1
        cvtss2sd xmm0, xmm0
        mulsd    xmm0, QWORD PTR __real@4014000000000000
        cvtsd2ss xmm0, xmm0
        ret      0
```

В разделе **/O2** **/fp:fast** упростит создаваемый код, поскольку оптимизации всех приведения типов:

```asm
        addss    xmm0, xmm1
        mulss    xmm0, DWORD PTR __real@40a00000
        ret      0
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **создание кода** страницу свойств.

1. Изменить **модель с плавающей запятой** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](compiler-options.md)<br/>
[Настройка параметров компилятора](setting-compiler-options.md)<br/>
[Microsoft Visual C++ с плавающей запятой оптимизация](floating-point-optimization.md)<br/>
