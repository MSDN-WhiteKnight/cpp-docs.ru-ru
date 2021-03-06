---
title: /QIfist (Suppress _ftol)
ms.date: 11/04/2016
f1_keywords:
- /qifist
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
ms.openlocfilehash: e01ee0b7af68127f3a78b4cfda1d110f6187fa74
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528122"
---
# <a name="qifist-suppress-ftol"></a>/QIfist (Suppress _ftol)

Не рекомендуется. Подавляет вызов вспомогательной функции `_ftol` при необходимости преобразования из типа с плавающей запятой в целочисленный тип.

## <a name="syntax"></a>Синтаксис

```
/QIfist
```

## <a name="remarks"></a>Примечания

> [!NOTE]
>  **/ QIfist** доступна только в компилятор x x86; этого компилятора недоступен в компиляторах, предназначенных для x64 orARM.

Кроме преобразования из типа с плавающей запятой в целочисленный тип `_ftol` функция обеспечивает режим округления с плавающей запятой единицы (FPU) по направлению к нулю (усечение), путем установки битов 10 и 11 контрольного слова. Это гарантирует, что преобразование из типа с плавающей запятой в целочисленный тип происходит, как описано в стандарте ANSI C (дробная часть числа отбрасывается). При использовании **/QIfist**, эта гарантия больше не применяется. Режим округления будет иметь одно из четырех, как описано в Intel справочных руководствах:

- Округление до ближайшего (даже если число равных)

- Округление в направлении минус бесконечности

- Округление в сторону положительной бесконечности

- Округление до нуля

Можно использовать [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) функции времени выполнения C для изменения поведения округления FPU. FPU режим округления по умолчанию — «Округление до ближайшего значения.» С помощью **/QIfist** может повысить производительность приложения, но не без риска. Необходимо тщательно протестировать части кода, которые чувствительны к режимам округления, перед ссылкой на код построены **/QIfist** в рабочих средах.

[/ arch (x86)](../../build/reference/arch-x86.md) и **/QIfist** не может использоваться в одной единице компиляции.

> [!NOTE]
>  **/ QIfist** — не действует по умолчанию поскольку округление битов также влияет на число с плавающей запятой с плавающей запятой точки округления (что происходит после каждого расчета), поэтому при установке флажков для округления в стиле C (к нулю), ваш с плавающей запятой вычисления, может отличаться. **/ QIfist** не должны использоваться, если код зависит от ожидаемого поведения усечения дробной части числа с плавающей запятой. Если вы не уверены, не используйте **/QIfist**.

**/QIfist** параметр является устаревшим, начиная с Visual Studio 2005. Компилятор внес значительные улучшения в число с плавающей запятой в int скорость преобразования. Список параметров компилятора, см. в разделе **нерекомендуемые и удаленные параметры компилятора** в [параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры /Q (низкоуровневые операции)](../../build/reference/q-options-low-level-operations.md)<br/>
[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)