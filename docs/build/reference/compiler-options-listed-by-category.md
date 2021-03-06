---
title: Параметры компилятора, упорядоченные по категориям
ms.date: 11/12/2018
helpviewer_keywords:
- compiler options, C++
ms.assetid: c4750dcf-dba0-4229-99b6-45cdecc11729
ms.openlocfilehash: 63b621bf99a1aeada10706badfe19cde417d7233
ms.sourcegitcommit: e540706f4e2675e7f597cfc5b4f8dde648b007bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56676504"
---
# <a name="compiler-options-listed-by-category"></a>Параметры компилятора, упорядоченные по категориям

Эта статья содержит сортированный по категориям список параметров компилятора. Сортированный в алфавитном порядке список см. в разделе [Compiler Options Listed Alphabetically](compiler-options-listed-alphabetically.md).

## <a name="optimization"></a>Оптимизация

|Параметр|Цель|
|------------|-------------|
|[/O1](o1-o2-minimize-size-maximize-speed.md)|Уменьшает размер кода.|
|[/O2](o1-o2-minimize-size-maximize-speed.md)|Создает быстрый код.|
|[/Ob](ob-inline-function-expansion.md)|Управляет подстановкой подставляемых функций.|
|[/Od](od-disable-debug.md)|Отключает оптимизацию.|
|[/Og](og-global-optimizations.md)|Не рекомендуется. Использует глобальную оптимизацию.|
|[/Oi](oi-generate-intrinsic-functions.md)|Создает встроенные функции.|
|[/Os](os-ot-favor-small-code-favor-fast-code.md)|Отдает приоритет уменьшению размера кода.|
|[/Ot](os-ot-favor-small-code-favor-fast-code.md)|Отдает приоритет быстрому коду.|
|[/Ox](ox-full-optimization.md)|Использует максимальную оптимизацию (/Ob2gity /Gs).|
|[/Oy](oy-frame-pointer-omission.md)|Пропускает указатель на фрейм. (только x86)|
|[/favor](favor-optimize-for-architecture-specifics.md)|Создает код, который оптимизирован для конкретной архитектуры или диапазона архитектур.|

## <a name="code-generation"></a>Создание кода

|Параметр|Цель|
|------------|-------------|
|[/arch](arch-x86.md)|Использование инструкций SSE или SSE2 при создании кода. (только x86)|
|[/clr](clr-common-language-runtime-compilation.md)|Создает выходной файл, предназначенный для выполнения в среде CLR.|
|[/EH](eh-exception-handling-model.md)|Задает модель обработки исключений.|
|[/fp](fp-specify-floating-point-behavior.md)|Указывает поведение чисел с плавающей запятой.|
|[/GA](ga-optimize-for-windows-application.md)|Выполняет оптимизацию для приложений Windows.|
|[/Gd](gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__cdecl` . (только x86)|
|[/Ge](ge-enable-stack-probes.md)|Не рекомендуется. Включает стековые зонды.|
|[/GF](gf-eliminate-duplicate-strings.md)|Включает объединение строк.|
|[/Gh](gh-enable-penter-hook-function.md)|Вызывает функцию-обработчик `_penter`.|
|[/GH](gh-enable-pexit-hook-function.md)|Вызывает функцию-обработчик `_pexit`.|
|[/GL](gl-whole-program-optimization.md)|Включает оптимизацию всей программы.|
|[/Gm](gm-enable-minimal-rebuild.md)|Не рекомендуется. Включает минимальное перепостроение.|
|[/GR](gr-enable-run-time-type-information.md)|Включает информацию о типах во время выполнения (RTTI).|
|[/Gr](gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__fastcall` . (только x86)|
|[/GS](gs-buffer-security-check.md)|Проверяет безопасность буфера.|
|[/Gs](gs-control-stack-checking-calls.md)|Управляет стековыми зондами.|
|[/GT](gt-support-fiber-safe-thread-local-storage.md)|Поддерживает безопасность волокон для данных, размещаемых с помощью статической локальной памяти потока.|
|[/guard:cf](guard-enable-control-flow-guard.md)|Добавление проверок безопасности для защиты потока управления.|
|[/Gv](gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__vectorcall` . (только x86 и x64)|
|[/Gw](gw-optimize-global-data.md)|Включает глобальную оптимизацию данных всей программы.|
|[/GX](gx-enable-exception-handling.md)|Не рекомендуется. Включает синхронную обработку исключений. Используйте вместо этого параметр [/EH](eh-exception-handling-model.md) .|
|[/Gy](gy-enable-function-level-linking.md)|Включает компоновку на уровне функций.|
|[/GZ](gz-enable-stack-frame-run-time-error-checking.md)|Не рекомендуется. Включает быстрые проверки. (Аналогично [/RTC1](rtc-run-time-error-checks.md))|
|[/Gz](gd-gr-gv-gz-calling-convention.md)|Использует соглашение о вызовах `__stdcall` . (только x86)|
|[/homeparams](homeparams-copy-register-parameters-to-stack.md)|Принудительная запись параметров, переданных в регистрах, в соответствующие места в стеке при вхождении в функцию. Этот параметр компилятора предназначен только для x64 компиляторы (собственные и кросс-компиляция).|
|[/hotpatch](hotpatch-create-hotpatchable-image.md)|Создает образ, допускающий горячее обновление.|
|[/Qfast_transcendentals](qfast-transcendentals-force-fast-transcendentals.md)|Создает быстрые трансцендентные функции.|
|[/QIfist](qifist-suppress-ftol.md)|Не рекомендуется. Подавляет вызов вспомогательной функции `_ftol` при необходимости преобразования из типа с плавающей запятой в целочисленный тип. (только x86)|
|[/Qimprecise_fwaits](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Удаляет команды `fwait` внутри блоков `try` .|
|[/Qpar](qpar-auto-parallelizer.md)|Включает автоматическую параллелизацию циклов.|
|[/Qpar-report](qpar-report-auto-parallelizer-reporting-level.md)|Включает уровни отчетов для автоматической параллелизации.|
|[/Qsafe_fp_loads](qsafe-fp-loads.md)|Использует целочисленные инструкции перемещения значений с плавающей запятой и отключает определенные оптимизации загрузки значений с плавающей запятой.|
|[/Qspectre](qspectre.md)|Включите способы устранения рисков для CVE 2017-5753 для класса Spectre атак.|
|[/ Qvec-report](qvec-report-auto-vectorizer-reporting-level.md)|Включает уровни отчетов для автоматической векторизации.|
|[/RTC](rtc-run-time-error-checks.md)|Включает проверку ошибок во время выполнения.|
|[/volatile](volatile-volatile-keyword-interpretation.md)|Выбирает способ интерпретации ключевого слова volatile.|

## <a name="output-files"></a>Выходные файлы

|Параметр|Назначение|
|------------|-------------|
|[/doc](doc-process-documentation-comments-c-cpp.md)|Обрабатывает комментарии к документации в XML-файл.|
|[/FA](fa-fa-listing-file.md)|Настраивает файл списка сборки.|
|[/Fa](fa-fa-listing-file.md)|Создает файл списка сборки.|
|[/Fd](fd-program-database-file-name.md)|Переименовывает файл базы данных программы.|
|[/Fe](fe-name-exe-file.md)|Переименовывает исполняемый файл.|
|[/Fi](fi-preprocess-output-file-name.md)|Задает предобработанное имя выходного файла.|
|[/Fm](fm-name-mapfile.md)|Создает файл сопоставления.|
|[/Fo](fo-object-file-name.md)|Создает объектный файл.|
|[/Fp](fp-name-dot-pch-file.md)|Задает имя файла предкомпилированного заголовка.|
|[/ FR, /Fr](fr-fr-create-dot-sbr-file.md)|Создать имя SBR-файлы браузера.|

## <a name="preprocessor"></a>Препроцессор

|Параметр|Цель|
|------------|-------------|
|[/AI](ai-specify-metadata-directories.md)|Указывает каталог поиска для разрешения ссылок на файлы, указанные в директиве [#using](../../preprocessor/hash-using-directive-cpp.md) .|
|[/C](c-preserve-comments-during-preprocessing.md)|Сохраняет комментарии на этапе предварительной обработки.|
|[/D](d-preprocessor-definitions.md)|Определяет константы и макросы.|
|[/E](e-preprocess-to-stdout.md)|Копирует выходные данные препроцессора в стандартный вывод.|
|[/EP](ep-preprocess-to-stdout-without-hash-line-directives.md)|Копирует выходные данные препроцессора в стандартный вывод.|
|[/FI](fi-name-forced-include-file.md)|Выполняет предварительную обработку указанного включаемого файла.|
|[/FU](fu-name-forced-hash-using-file.md)|Обеспечивает принудительное использование имени файла, как если бы оно было указано в директиве [#using](../../preprocessor/hash-using-directive-cpp.md) .|
|[/Fx](fx-merge-injected-code.md)|Выполняет слияние введенного кода с исходным файлом.|
|[/I](i-additional-include-directories.md)|Осуществляет поиск включаемых файлов в каталоге.|
|[/P](p-preprocess-to-a-file.md)|Записывает выходные данные препроцессора в файл.|
|[/U](u-u-undefine-symbols.md)|Удаляет предварительно определенный макрос.|
|[/u](u-u-undefine-symbols.md)|Удаляет все предварительно определенные макросы.|
|[/X](x-ignore-standard-include-paths.md)|Пропускает стандартный каталог включаемых файлов.|

## <a name="language"></a>Язык

|Параметр|Цель|
|------------|-------------|
|[/constexpr](constexpr-control-constexpr-evaluation.md)|Управлять вычислением constexpr во время компиляции.|
|[/openmp](openmp-enable-openmp-2-0-support.md)|Включает прагма-директиву [#pragma omp](../../preprocessor/omp.md) в исходном коде.|
|[/vd](vd-disable-construction-displacements.md)|Подавляет или включает скрытые члены класса `vtordisp` .|
|[/vmb](vmb-vmg-representation-method.md)|Использует оптимальное основание для указателей на члены.|
|[/vmg](vmb-vmg-representation-method.md)|Использует полное обобщение для указателей на члены.|
|[/vmm](vmm-vms-vmv-general-purpose-representation.md)|Объявляет множественное наследование.|
|[/vms](vmm-vms-vmv-general-purpose-representation.md)|Объявляет одиночное наследование.|
|[/vmv](vmm-vms-vmv-general-purpose-representation.md)|Объявляет виртуальное наследование.|
|[/Z7](z7-zi-zi-debug-information-format.md)|Приводит к возникновению ошибки совместимости с C 7.0 отладочную информацию.|
|[/Za](za-ze-disable-language-extensions.md)|Отключает расширения языка.|
|[/Zc](zc-conformance.md)|Задает стандартное поведение при использовании параметра [/Ze](za-ze-disable-language-extensions.md).|
|[/Ze](za-ze-disable-language-extensions.md)|Не рекомендуется. Включает расширения языка.|
|[/Zf](zf.md)|Улучшает время создания в параллельные сборки PDB-файла.|
|[/ZI](z7-zi-zi-debug-information-format.md)|Включает отладочную информацию в базу данных программы, совместимую с функцией "Изменить и продолжить". (только x86)|
|[/Zi](z7-zi-zi-debug-information-format.md)|Создает полную отладочную информацию.|
|[/Zl](zl-omit-default-library-name.md)|Удаляет имя библиотеки по умолчанию из OBJ-файла.|
|[/Zp](zp-struct-member-alignment.md) *n*|Упаковывает члены структур.|
|[/Zs](zs-syntax-check-only.md)|Проверяет только синтаксис.|
|[/ZW](zw-windows-runtime-compilation.md)|Создает выходной файл для запуска в среде выполнения Windows.|

## <a name="linking"></a>Компоновка

|Параметр|Цель|
|------------|-------------|
|[/F](f-set-stack-size.md)|Задает размер стека.|
|[/LD](md-mt-ld-use-run-time-library.md)|Создает библиотеку динамической компоновки.|
|[/LDd](md-mt-ld-use-run-time-library.md)|Создает отладочную библиотеку динамической компоновки.|
|[/link](link-pass-options-to-linker.md)|Передает указанный параметр в программу LINK.|
|[/LN](ln-create-msil-module.md)|Создает модуль MSIL.|
|[/MD](md-mt-ld-use-run-time-library.md)|Компилирует для создания многопотоковой библиотеки DLL с помощью библиотеки MSVCRT.lib.|
|[/MDd](md-mt-ld-use-run-time-library.md)|Компилирует для создания отладочной многопотоковой библиотеки DLL с помощью библиотеки MSVCRTD.lib.|
|[/MT](md-mt-ld-use-run-time-library.md)|Компилирует для создания многопотокового исполняемого файла с помощью библиотеки LIBCMT.lib.|
|[/MTd](md-mt-ld-use-run-time-library.md)|Компилирует для создания отладочного многопотокового исполняемого файла с помощью библиотеки LIBCMTD.lib.|

## <a name="miscellaneous"></a>Прочее

|Параметр|Цель|
|------------|-------------|
|[/?](help-compiler-command-line-help.md)|Отображает список параметров компилятора.|
|[@](at-specify-a-compiler-response-file.md)|Указывает файл ответа.|
|[/analyze](analyze-code-analysis.md)|Включает анализ кода|
|[/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md)|Увеличивает число адресуемых секций в OBJ-файле.|
|[/c](c-compile-without-linking.md)|Задает компиляцию без компоновки.|
|[/cgthreads](cgthreads-code-generation-threads.md)|Задает число потоков cl.exe, используемых для оптимизации и создания кода.|
|[/errorReport](errorreport-report-internal-compiler-errors.md)|Разрешает передавать данные о внутренних ошибках компилятора (ICE) непосредственно в группу Visual C++.|
|[/FC](fc-full-path-of-source-code-file-in-diagnostics.md)|Отображает полный путь файлов исходного кода, переданных программе cl.exe, в диагностическом тексте.|
|[/FS](fs-force-synchronous-pdb-writes.md)|Обеспечивает принудительную сериализацию записей в файл базы данных программы (PDB) с помощью MSPDBSRV.EXE.|
|[/H](h-restrict-length-of-external-names.md)|Не рекомендуется. Ограничивает длину внешних (открытых) имен.|
|[/HELP](help-compiler-command-line-help.md)|Отображает список параметров компилятора.|
|[/J](j-default-char-type-is-unsigned.md)|Изменяет тип `char` по умолчанию.|
|[/JMC](jmc.md)|Поддерживает отладку собственного C++ Just My Code.|
|[/kernel](kernel-create-kernel-mode-binary.md)|Компилятор и компоновщик создадут двоичный файл для выполнения в ядре Windows.|
|[/MP](mp-build-with-multiple-processes.md)|Параллельное построение нескольких исходных файлов.|
|[/nologo](nologo-suppress-startup-banner-c-cpp.md)|Подавление отображения приветствия.|
|[/sdl](sdl-enable-additional-security-checks.md)|Включает дополнительные функции безопасности и предупреждения.|
|[/showIncludes](showincludes-list-include-files.md)|Отображает список всех включаемых файлов во время компиляции.|
|[/Tc](tc-tp-tc-tp-specify-source-file-type.md)|Указывает исходный файл на языке C.|
|[/TC](tc-tp-tc-tp-specify-source-file-type.md)|Указывает, что все исходные файлы, C.|
|[/Tp](tc-tp-tc-tp-specify-source-file-type.md)|Указывает исходный файл на языке C++.|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|Указывает, что все исходные файлы C++.|
|[/V](v-version-number.md)|Не рекомендуется. Задает строку версии.|
|[/w](compiler-option-warning-level.md)|Отключает все предупреждения.|
|[/W0, /W1, /W2, /W3, /W4](compiler-option-warning-level.md)|Задает уровень выходного предупреждения.|
|[/w1, /w2, /w3, /w4](compiler-option-warning-level.md)|Задает уровень для указанного предупреждения.|
|[/Wall](compiler-option-warning-level.md)|Включает все предупреждения, в том числе предупреждения, отключенные по умолчанию.|
|[/wd](compiler-option-warning-level.md)|Отключает указанное предупреждение.|
|[/we](compiler-option-warning-level.md)|Обрабатывает указанное предупреждение как ошибку.|
|[/WL](wl-enable-one-line-diagnostics.md)|Включает однострочные диагностические сообщения об ошибках и предупреждения в ходе компиляции исходного кода C++ из командной строки.|
|[/wo](compiler-option-warning-level.md)|Отображает указанное предупреждение только один раз.|
|[/Wv](compiler-option-warning-level.md)|Отключает предупреждения, появившиеся в более поздних версиях компилятора.|
|[/WX](compiler-option-warning-level.md)|Обрабатывает предупреждения как ошибки.|
|[/Yc](yc-create-precompiled-header-file.md)|Создаете. PCH-файл.|
|[/Yd](yd-place-debug-information-in-object-file.md)|Не рекомендуется. Размещает полную отладочную информацию во всех объектных файлах. Используйте вместо этого параметр [/Zi](z7-zi-zi-debug-information-format.md) .|
|[/Yl](yl-inject-pch-reference-for-debug-library.md)|Вставляет ссылку PCH при создании отладочной библиотеки.|
|[/Yu](yu-use-precompiled-header-file.md)|Использует файл предкомпилированного заголовка при построении.|
|[/Y-](y-ignore-precompiled-header-options.md)|Пропускает все прочие параметры компилятора, относящиеся к предварительно скомпилированным заголовкам, в текущем построении.|
|[/Zm](zm-specify-precompiled-header-memory-allocation-limit.md)|Указывает предел выделения памяти для предкомпилированного заголовка.|
|[/ await](await-enable-coroutine-support.md)|Включите расширения сопрограммы (возобновляемые функции).|
|[кодировки/Source](source-charset-set-source-character-set.md)|Задание исходной кодировки.|
|[/ Execution-CharSet](execution-charset-set-execution-character-set.md)|Задание набора символов исполнения.|
|[/utf-8](utf-8-set-source-and-executable-character-sets-to-utf-8.md)|Набор источника и выполнения кодировки UTF-8.|
|[/validate-charset](validate-charset-validate-for-compatible-characters.md)|Проверка файлов UTF-8 только совместимости символов.|
|[/ Diagnostics](diagnostics-compiler-diagnostic-options.md)|Определяет формат диагностических сообщений.|
|[/ permissive-](permissive-standards-conformance.md)|Режим соответствия standard.|
|[/std](std-specify-language-standard-version.md)|Селектор совместимости стандартной версии C++.|

## <a name="deprecated-and-removed-compiler-options"></a>Нерекомендуемые и удаленные параметры компилятора

|Параметр|Цель|
|------------|-------------|
|[/clr:noAssembly](clr-common-language-runtime-compilation.md)|Не рекомендуется. Взамен рекомендуется использовать [/LN (Create MSIL Module)](ln-create-msil-module.md) .|
|[/Fr](fr-fr-create-dot-sbr-file.md)|Не рекомендуется. Создает файл информации об исходном коде без локальных переменных.|
|[/Ge](ge-enable-stack-probes.md)|Не рекомендуется. Включает стековые зонды. По умолчанию включен.|
|[/Gm](gm-enable-minimal-rebuild.md)|Не рекомендуется. Включает минимальное перепостроение.|
|[/GX](gx-enable-exception-handling.md)|Не рекомендуется. Включает синхронную обработку исключений. Используйте вместо этого параметр [/EH](eh-exception-handling-model.md) .|
|[/GZ](gz-enable-stack-frame-run-time-error-checking.md)|Не рекомендуется. Включает быстрые проверки. Используйте вместо этого параметр [/RTC1](rtc-run-time-error-checks.md) .|
|[/H](h-restrict-length-of-external-names.md)|Не рекомендуется. Ограничивает длину внешних (открытых) имен.|
|[/Og](og-global-optimizations.md)|Не рекомендуется. Использует глобальную оптимизацию.|
|[/QIfist](qifist-suppress-ftol.md)|Не рекомендуется. Используется один раз для указания способа преобразования типа с плавающей запятой в целочисленный тип.|
|[/V](v-version-number.md)|Не рекомендуется. Задает строку версии OBJ-файла.|
|[/Wp64](wp64-detect-64-bit-portability-issues.md)|Является устаревшей. Выявляет проблемы 64-битной переносимости.|
|[/Yd](yd-place-debug-information-in-object-file.md)|Не рекомендуется. Размещает полную отладочную информацию во всех объектных файлах. Используйте вместо этого параметр [/Zi](z7-zi-zi-debug-information-format.md) .|
|[/Zc:forScope-](zc-forscope-force-conformance-in-for-loop-scope.md)|Не рекомендуется. Отключает согласование видимости переменных, объявленных в заголовке оператора for.|
|[/Ze](za-ze-disable-language-extensions.md)|Не рекомендуется. Включает расширения языка.|
|[/Zg](zg-generate-function-prototypes.md)|Удален в Visual C++ 2015. Создает прототипы функций.|

## <a name="see-also"></a>См. также

[Справочные сведения о сборке C/C++](c-cpp-building-reference.md)<br/>
[Параметры компилятора](compiler-options.md)<br/>
[Настройка параметров компилятора](setting-compiler-options.md)<br/>
