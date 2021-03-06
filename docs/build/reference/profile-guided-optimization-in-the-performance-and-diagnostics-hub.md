---
title: Профильная оптимизация в концентраторе производительности и диагностики
ms.date: 11/19/2018
ms.assetid: dc3a1914-dbb6-4401-bc63-10665a8c8943
ms.openlocfilehash: a8c0467e1a3051609f52053894ea59064e40a3ac
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176202"
---
# <a name="profile-guided-optimization-in-the-visual-studio-2013-performance-and-diagnostics-hub"></a>Профильная оптимизация в Visual Studio 2013 Центр производительности и диагностики

Если вы используете Visual Studio 2013, Профильная оптимизация подключаемого модуля в концентраторе производительности и диагностики Visual c++ ускоряет взаимодействие профильной оптимизации для разработчиков. Вы можете [загрузить подключаемый модуль](https://marketplace.visualstudio.com/items?itemName=ProfileGuidedOptimizationTeam.ProfileGuidedOptimizationforVisualC) с веб-сайта Visual Studio. Подключаемый модуль не поддерживается в более поздних версиях Visual Studio.

Благодаря профильной оптимизации (PGO) можно создать сборки x86 и x64 собственные приложения, оптимизированные для способа, которым пользователи взаимодействуют с ними. Профильная Оптимизация — это многоэтапный процесс: создайте выполняется сборка приложения, которое инструментировано для профилирования и затем проводится «обучение». То есть вы Инструментированное приложение запускается с распространенными сценариями взаимодействия пользователя. Собранные данные профилирования сохраняются, затем происходит перестроение приложения с использованием результатов, которые направят оптимизацию всей программы. Хотя вы можете выполнить следующие действия по отдельности в Visual Studio или из командной строки, подключаемый модуль профильной оптимизации централизует и упрощает процесс. Подключаемый модуль профильной оптимизации задает все необходимые параметры, руководит каждым шагом, показывает анализ, а затем использует результаты для настройки сборки, чтобы оптимизировать каждую функцию по размеру и скорости. Подключаемый модуль профильной оптимизации также упрощает повторное обучение приложения и обновление данных для оптимизации сборки по мере внесения изменений в код.

## <a name="prerequisites"></a>Предварительные требования

Вы должны [загрузить подключаемый модуль профильной Оптимизации](https://marketplace.visualstudio.com/items?itemName=ProfileGuidedOptimizationTeam.ProfileGuidedOptimizationforVisualC) и установите его в Visual Studio, прежде чем можно будет использовать в концентраторе производительности и диагностики.

## <a name="walkthrough-using-the-pgo-plug-in-to-optimize-an-app"></a>Пошаговое руководство: Использование подключаемых модулей профильной оптимизации для оптимизации приложения

Сначала создайте простое настольное приложение Win32 в Visual Studio. Если у вас уже есть собственное приложение, которое нужно оптимизировать, то его можно использовать и пропустить этот шаг.

### <a name="to-create-an-app"></a>Создание приложения

1. В строке меню выберите **Файл**, **Создать**, **Проект**.

1. В левой области **новый проект** диалогового окна последовательно раскройте элементы **установленные**, **шаблоны**, **Visual C++**, а затем выберите  **MFC**.

1. В центральной области выберите **приложения MFC**.

1. Укажите имя для проекта — например, **SamplePGOProject**— в **имя** поле. Нажмите кнопку **ОК** .

1. На **Обзор** странице **мастер приложений MFC** диалоговое окно, выберите **Готово** кнопки.

Затем задайте конфигурацию сборки приложения в "Выпуск" для подготовки его для действий сборки и обучения профильной оптимизации.

### <a name="to-set-the-build-configuration"></a>Чтобы задать конфигурацию сборки

1. В строке меню последовательно выберите пункты **Сборка**и **Диспетчер конфигураций**.

1. В **Configuration Manager** диалоговое окно, выберите **активная конфигурация решения** кнопку раскрывающегося списка и выберите **выпуска**. Выберите **закрыть** кнопки.

Откройте Центр производительности и диагностики, в строке меню выберите **анализ**, **производительность и диагностика**. Откроется страница сеанса диагностики со средствами анализа, доступными для данного типа проекта.

![Профильная Оптимизация в концентраторе производительности и диагностики](../../build/reference/media/pgofig0hub.png "Профильная Оптимизация в концентраторе производительности и диагностики")

В **доступные инструменты**выберите **профильной оптимизации** "флажок". Выберите **запустить** кнопку, чтобы запустить подключаемый модуль профильной Оптимизации.

![Вводная страница профильной Оптимизации](../../build/reference/media/pgofig1start.png "Вводная страница профильной Оптимизации")

**Профильной оптимизации** страница описывает шаги подключаемый модуль, который используется для повышения производительности приложения. Выберите **запустить** кнопки.

![Страница инструментирования профильной Оптимизации](../../build/reference/media/pgofig2instrument.png "страница инструментирования профильной Оптимизации")

В **инструментирования** использовании разделе **обучение изначально включено** возможность выбирать, следует ли включать на этапе запуска приложения в процессе обучения. Если этот параметр не установлен, данные обучения не записываются в запущенное инструментированное приложение, пока обучение не будет явно включено.

Выберите **инструментирования** кнопку для создания приложения со специальным набором параметров компилятора. Компилятор вставляет инструкции зонда в созданный код. Эти инструкции записывают данные профилирования на этапе обучения.

![Страница инструментированной сборки профильной Оптимизации](../../build/reference/media/pgofig3build.PNG "страница инструментированной сборки профильной Оптимизации")

По завершению сборки инструментированного приложения оно запускается автоматически.

В случае ошибки или предупреждения во время сборки, исправьте их, а затем выберите **перезапуск сборки** Чтобы перезапустить инструментированную сборку.

При запуске приложения, можно использовать **начать обучение** и **приостановить Обучение** ссылок в **обучения** раздел, чтобы контролировать, когда записью информации профилирования. Можно использовать **остановить приложение** и **простое приложение** ссылки, чтобы остановить и перезапустить приложение.

![Страница обучения профильной Оптимизации](../../build/reference/media/pgofig4training.PNG "страница обучения профильной Оптимизации")

Во время обучения просматривайте сценарии пользователя сбора, чтобы захватить данные профилирования, которые нужны подключаемому модулю профильной оптимизации для оптимизации кода. После завершения обучения закройте приложение, или выберите **остановить приложение** ссылку. Выберите **анализ** кнопку, чтобы запустить шаг анализа.

После завершения анализа **Analysis** отображается отчет данных профилирования, собранных на этапе обучения пользовательским сценариям. Этот отчет можно использовать для исследования того, какие функции приложения были вызваны чаще всех и на какие из них было потрачено больше времени. Подключаемый модуль профильной оптимизации использует эти сведения, чтобы определить, какие функции приложения требуют оптимизации быстродействия, а какие — оптимизации по размеру. Подключаемый модуль профильной оптимизации настраивает оптимизации сборки для создания наименьшего, наиболее быстрого приложения для сценариев пользователя, записанных в ходе обучения.

![Страница анализа профильной Оптимизации](../../build/reference/media/pgofig5analyze.png "страница анализа профильной Оптимизации")

Если обучение зафиксировало ожидаемые данные профилирования, вы можете выбрать **сохранить изменения** сохранение проанализированных данных профилирования проекта, чтобы оптимизировать последующие сборки. Чтобы отменить данные профилирования и начать обучение с самого начала, выберите **повторить Обучение**.

Файл данных профилирования сохраняется в проекте в **обучающие данные PGO** папки. Эти данные используются для управления параметрами компилятора по оптимизации сборки в приложении.

![Файл данных профильной Оптимизации в обозревателе решений](../../build/reference/media/pgofig6data.png "файл данных профильной Оптимизации в обозревателе решений")

После анализа, подключаемый модуль профильной оптимизации настраивает параметры сборки в проекте так, чтобы использовать данные профилирования для выборочной оптимизации приложения во время компиляции. Можно продолжить изменение и выполнение сборки приложения с теми же данными профилирования. После сборки приложения в выходных данных сборки сообщается, сколько функций и инструкций было оптимизировано с использованием данных профилирования.

![PGO выходных данных диагностики](../../build/reference/media/pgofig7diagnostics.png "профильной Оптимизации выходных данных диагностики")

Если во время разработки выполняется значительное изменение кода, вы можете повторить обучение, чтобы получить лучшие показатели оптимизации приложения. Рекомендуется повторить обучение приложения, если в выходных данных сборки сообщается, что с помощью данных профилирования было оптимизировано менее 80 процентов функций и инструкций.