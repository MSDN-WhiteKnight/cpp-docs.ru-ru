---
title: Новые возможности C++ в Visual Studio 2019
ms.date: 04/02/2019
ms.technology: cpp-ide
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 493b96a8ce3359cc18287adbae8cbd6c374671ec
ms.sourcegitcommit: b72a10a7b12e722fd91a17406b91b270026f763a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2019
ms.locfileid: "58899410"
---
<!--NOTE all https:// links to docs.microsoft.com need to be converted to site-relative links prior to publishing-->

# <a name="whats-new-for-c-in-visual-studio-2019"></a>Новые возможности C++ в Visual Studio 2019

В Visual Studio 2019 реализовано множество изменений и исправлений для среды Microsoft C++. Мы исправили множество ошибок и сообщили о проблемах с компилятором и средствами, многие из которых были отправлены клиентами с помощью инструментов [Сообщить о проблеме](/visualstudio/how-to-report-a-problem-with-visual-studio-2017) и [Отправить предложение](https://developercommunity.visualstudio.com/spaces/62/index.html) в разделе **Отправить отзыв**. Спасибо, что сообщаете нам об ошибках! Дополнительные сведения о новых возможностях всех компонентов Visual Studio см. на странице [Новые возможности в Visual Studio](/visualstudio/ide/whats-new-visual-studio-2019).

## <a name="c-compiler"></a>компилятор C++

- Параметр `/std:c++latest` теперь включает в себя 20 функций C ++, которые не обязательно завершены, включая начальную поддержку оператора C ++ 20 <=> ("космический корабль") для трехстороннего сравнения.

- [P0941R2 — макросы тестирования функций](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html) завершены с поддержкой `__has_cpp_attribute`. Макросы для тестирования функций поддерживаются во всех стандартных режимах.

- [C++ 20 P1008R1 — запрет агрегирования с объявленными пользователем конструкторами](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf) также завершен.

- Улучшенная поддержка функций C++ 17, а также экспериментальная поддержка функций C++ 20, таких как модули и сопрограммы. Подробные сведения см. в статье [Улучшения соответствия C++ в Visual Studio 2019](../cpp-conformance-improvements.md).

- Параметр компилятора C++ `/Gm` теперь считается устаревшим. Рекомендуется отключить параметр `/Gm` в скриптах сборки, если он задан явно. Можно просто проигнорировать предупреждение об устаревании `/Gm`, так как оно не считается ошибкой при использовании режима "Обрабатывать предупреждения как ошибки" (`/WX`).

- Предкомпилированные заголовки больше не создаются по умолчанию для консоли C++ и настольных приложений.

### <a name="codegen-security-diagnostics-and-versioning"></a>Создание кода, безопасность, диагностика и управления версиями

Доступен параметр `/Qspectre` для более эффективного анализа и устранения рисков, связанных с уязвимостью Spectre 1-го варианта (CVE-2017-5753). Дополнительные сведения см. в записи блога [Устранение рисков Spectre в MSVC](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/).

## <a name="c-standard-library-improvements"></a>Улучшения стандартной библиотеки C++

- [C++ 20 P0550R2 \(remove_cvref)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf) завершена.

- C ++ 17 \<charconv > число с плавающей запятой to_chars() улучшено: кратчайший chars_format::fixed на 60–80 % быстрее, и кратчайший/точный chars_format::hex завершен.

- Дополнительные алгоритмы имеют параллельную реализацию: is_sorted(), is_sorted_until(), is_partitioned(), set_difference(), set_intersection(), is_heap(), is_heap_until().

- Усовершенствован `std::variant` для более удобной работы с оптимизатором, что приводит к улучшению сформированного кода. Встраивание кода теперь гораздо лучше с `std::visit`.

- Мы применили clang-format в заголовках стандартной библиотеки C++ для улучшения читаемости кода.

- Повышенная пропускная способность, если несколько функций стандартной библиотеки компилируются с помощью `if constexpr`.

- Оптимизирована физическая структура стандартной библиотеки, чтобы избежать компиляции частей стандартной библиотеки не #include, что в два раза ускоряет время сборки пустого файла, включающего только \<vector>.

## <a name="performancethroughput-fixes"></a>Исправления производительности и пропускной способности

- Реализованы усовершенствования пропускной способности сборки, включая обработку компоновщиком ввода-вывода файлов и время компоновки при объединении и создании типа PDB.

- Добавлена базовая поддержка векторизации OpenMP SIMD. Вы можете включить ее с помощью нового переключателя CL `-openmp:experimental`. Эта опция позволяет при необходимости векторизовать циклы, аннотированные с `#pragma omp simd`. Векторизация не гарантируется, и циклы с аннотацией, но без векторизации, будут выдавать предупреждение. Предложения SIMD не поддерживаются, они просто игнорируются с предупреждением.

- Добавлен новый параметр встраивания командной строки `-Ob3`, который представляет собой более активную версию `-Ob2`. `-O2` (оптимизация двоичного файла для скорости) по-прежнему подразумевает `-Ob2` по умолчанию. Если обнаружится, что компилятор недостаточно активно встраивает, попробуйте передать `-O2 -Ob3`.

- Для поддержки векторизации циклов вручную с вызовами функций математической библиотеки и некоторыми другими операциями, такими как целочисленное деление, мы добавили поддержку встроенных функций Short Vector Math Library (SVML). Эти функции вычисляют 128-разрядные, 256-разрядные или 512-разрядные векторные эквиваленты. См. раздел [Руководство по встроенным функциям Intel](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#!=undefined&techs=SVML) с определениями поддерживаемых функций.

- Новые и улучшенные оптимизации:

  - Свертывание констант и арифметические упрощения для выражений с помощью встроенных функций SIMD (вектор) для чисел с плавающей запятой и целых чисел.

  - Более эффективный анализ для извлечения данных из потока управления (инструкции if/else/switch) для удаления ветвей, которые всегда имеют значение true или false.

  - Улучшенное развертывание memset для использования векторных инструкций SSE2.

  - Улучшенное удаление бесполезных копий структур или классов, особенно для программ C++, которые передают по значению.

  - Улучшена оптимизация кода с использованием `memmove`, например конструкции `std::copy` или `std::vector` и `std::string`.

## <a name="c-ide"></a>IDE C++

### <a name="live-share-c-support"></a>Поддержка Live Share C++

[Live Share](/visualstudio/liveshare/) теперь поддерживает C++, позволяя разработчикам, использующим Visual Studio или Visual Studio Code, сотрудничать в режиме реального времени. Дополнительные сведения см. в статьях [Объявление Live Share для C++: общий доступ и совместная работа в режиме реального времени](https://devblogs.microsoft.com/cppblog/cppliveshare/)

### <a name="intellicode-for-c"></a>IntelliCode для C++

IntelliCode — это дополнительное расширение, которое использует обучение и контекст кода для вывода тех вариантов, которые вы чаще всего используете, в верхней части списка завершения. Он также часто устраняет необходимость прокручивать список. В C++ IntelliCode наиболее эффективно работает при использовании популярных библиотек, таких как стандартная библиотека. Дополнительные сведения см. в разделе [Рекомендации по завершению кода на базе ИИ в C++ через IntelliCode](https://devblogs.microsoft.com/cppblog/cppintellicode/).

### <a name="template-intellisense"></a>Шаблон IntelliSense

В **строке шаблона** теперь используется пользовательский интерфейс **Окно просмотра**, а не модальное окно, поддерживаются вложенные шаблоны и автоматически заполняются аргументы по умолчанию в **Окне просмотра**. Дополнительные сведения см. в статье [Усовершенствования шаблона IntelliSense для Visual Studio 2019, предварительная версия 2](https://devblogs.microsoft.com/cppblog/template-intellisense-improvements-for-visual-studio-2019-preview-2/). Раскрывающийся список **Недавно использовавшиеся** в **строке шаблона** позволяет быстро переключаться между предыдущими наборами аргументов шаблона.

### <a name="new-start-window-experience"></a>Новый интерфейс начального окна

При запуске интегрированной среды разработки откроется новое начальное окно с параметрами, которые позволяют открыть последние проекты, клонировать код из системы управления версиями, открыть локальный код как решение или папку или создать новый проект. Диалоговое окно создания проекта также теперь ориентировано на поиск и фильтрацию.

### <a name="new-names-for-some-project-templates"></a>Новые имена для некоторых шаблонов проектов

Мы изменили несколько имен и описаний шаблонов проектов в соответствии с обновленным диалоговым окном создания проекта.

### <a name="various-productivity-improvements"></a>Различные улучшения производительности

Visual Studio 2019 включает в себя следующие возможности, которые помогут сделать процесс кодирования более простым и интуитивным:

- Быстрые исправления для:
  - Добавление недостающих #include
  - NULL и nullptr
  - Добавление недостающих точек с запятой.
  - Разрешение отсутствующего пространства имен или области
  - Замена неправильных операндов косвенного обращения (\* на & и & на \*)
- Краткие сведения для блока при наведении указателя на закрывающую скобку
- Просмотреть файл заголовка или кода
- "Перейти к определению" для #include открывает файл

Дополнительные сведения см. в статье [Улучшения производительности C++ в Visual Studio 2019, предварительная версия 2](https://devblogs.microsoft.com/cppblog/c-productivity-improvements-in-visual-studio-2019-preview-2/).

## <a name="cmake-support"></a>Поддержка CMake

- Visual Studio теперь может открыть существующие кэши CMake, созданные внешними средствами, например CMakeGUI или пользовательскими системами мета-сборки, или создать скрипты, которые сами вызывают cmake.exe.

- Усовершенствование производительности IntelliSense.

- Новый редактор параметров предоставляет альтернативу редактированию файла CMakeSettings.json вручную и частичное равенство с CMakeGUI.

- Visual Studio помогает начать разработку на C++ с помощью CMake в Linux, определяя наличие совместимой версии CMake на компьютере Linux, а если она отсутствует, предлагает ее установить.

- Несовместимые параметры в CMakeSettings, например несоответствие архитектур или несовместимые параметры генератора CMake, выделены волнистыми линиями в редакторе JSON и отображаются в списке ошибок.

- Цепочка инструментов vcpkg автоматически обнаруживается и включается для проектов CMake, которые открыты в интегрированной среде разработки, после запуска `vcpkg integrate install`. Это поведение можно отключить, указав пустой файл цепочки инструментов в CMakeSettings.

- Проекты CMake теперь включают отладку "Только мой код" по умолчанию.

- Предупреждения статического анализа теперь могут обрабатываться в фоновом режиме и отображаться в редакторе для проектов CMake.

- Более понятные сообщения о конце и начале сборки и конфигурации для проектов CMake и поддержка пользовательского интерфейса хода сборки Visual Studio. Кроме того, теперь есть параметр детализации CMake в разделе **Сервис > Параметры** для настройки уровня детализации сообщений о сборке и конфигурации CMake в окне вывода.

- Параметр `cmakeToolchain` теперь поддерживается в CMakeSettings.json для указания цепочек инструментов без изменения командной строки CMake вручную.

- Новое сочетание клавиш для меню **Собрать все** — **CTRL+SHIFT+B**.

## <a name="debugging"></a>Отладка

- Для приложений на C++, работающих в Windows, PDB-файлы теперь загружаются в отдельном 64-разрядном процессе. Это изменение позволяет устранить ряд сбоев из-за нехватки памяти при отладке приложений, которые содержат большое количество модулей и PDB-файлов.

## <a name="windows-desktop-development-with-c"></a>Разработка классических приложений для Windows на C++

- Следующие мастера C++, ATL и MFC больше не доступны:

  - Мастер компонентов ATL COM+ 1.0
  - Мастер компонентов ATL ASP
  - Мастер поставщика ATL OLE DB
  - Мастер страницы свойств ATL
  - Мастер потребителя ATL OLE DB
  - Потребитель ODBC MFC
  - Класс MFC из элемента управления ActiveX
  - Класс MFC из TypeLib.

  Пример кода для этих технологий находится в архиве в документации Майкрософт и репозитории VCSamples на GitHub.

- Пакет SDK Windows 8.1 больше не доступен в установщике Visual Studio. Обновите проекты C++ до последней версии пакета SDK для Windows 10. Если у вас есть жесткая зависимость от версии 8.1, ее можно скачать из архива Windows SDK.

- Windows XP больше нельзя выбрать в качестве целевой платформы для последнего набора инструментов C++. XP для библиотек и компилятора MSVC уровня VS 2017 по-прежнему поддерживается и может устанавливаться через раздел "Отдельные компоненты".

- В нашей документации настоятельно не рекомендуется использовать модули слияния для развертывания среды выполнения Visual C++. В этом выпуске мы принимаем дополнительные меры, чтобы отметить MSM как нерекомендуемые. Возможно, следует перенести центральное развертывание VCRuntime из MSM в распространяемый пакет.

## <a name="mobile-development-with-c-android-and-ios"></a>Разработка мобильных приложений на C++ (для iOS и Android)

C++ для Android теперь по умолчанию равняется на Android SDK 25 и пакет NDK для Android 16b.

## <a name="clangc2-platform-toolset"></a>Набор средств платформы Clang/C2

Экспериментальный компонент Clang/C2 удален. Для обеспечения полного соответствия стандартам C++ используйте набор инструментов MSVC с параметрами `/permissive-` и `/std:c++17` или же цепочку инструментов Clang/LLVM для Windows.

## <a name="code-analysis"></a>Анализ кода

- Анализ кода теперь выполняется автоматически в фоновом режиме. Предупреждения отображаются зелеными волнистыми линиями в редакторе при вводе. Дополнительные сведения см. в разделе [Анализа кода в редакторе в Visual Studio 2019, предварительная версия 2](https://devblogs.microsoft.com/cppblog/in-editor-code-analysis-in-visual-studio-2019-preview-2/).

- Новые экспериментальные правила ConcurrencyCheck для хорошо известных типов стандартной библиотеки из заголовка \<mutex>. Дополнительные сведения см. в разделе [Параллельный анализ кода в Visual Studio 2019](https://devblogs.microsoft.com/cppblog/concurrency-code-analysis-in-visual-studio-2019/).

- Обновленная частичная реализация [инструмента проверки профиля времени существования](https://herbsutter.com/2018/09/20/lifetime-profile-v1-0-posted/) для обнаружения висячих указателей и ссылок. Дополнительные сведения см. в разделе [Обновление профиля времени существования в Visual Studio 2019, предварительная версия 2](https://devblogs.microsoft.com/cppblog/lifetime-profile-update-in-visual-studio-2019-preview-2/).

- Дополнительные проверки сопрограмм, включая C26138, C26810, C26811 и экспериментальное правило C26800. Дополнительные сведения см. в разделе [Новые проверки анализа кода в Visual Studio 2019: использование после перемещения и сопрограмма](https://devblogs.microsoft.com/cppblog/new-code-analysis-checks-in-visual-studio-2019-use-after-move-and-coroutine/).

## <a name="unit-testing"></a>Модульное тестирование

Шаблон управляемого тестового проекта C++ больше не доступен. Вы можете продолжить использование платформы управляемых тестов C++ в существующих проектах. Но для новых модульных тестов мы рекомендуем использовать собственные тестовые платформы, для которых Visual Studio предоставляет шаблоны (MSTest, Google Test), или шаблон управляемого тестового проекта C#.