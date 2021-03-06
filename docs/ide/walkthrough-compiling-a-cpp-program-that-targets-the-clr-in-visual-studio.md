---
title: Компиляция программы C++, предназначенной для среды CLR
ms.date: 09/17/2018
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
ms.openlocfilehash: 51e8b234792dea8dd7d61e4ac4b97a55bd5ea4e9
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524635"
---
# <a name="walkthrough-compiling-a-c-program-that-targets-the-clr-in-visual-studio"></a>Пошаговое руководство. Компиляция программы на языке C++, предназначенной для среды CLR, в Visual Studio

Вы можете создавать программы Visual C++, использующие классы .NET и компилирующие их с помощью среды разработки Visual Studio.

Для выполнения этой процедуры вы можете указать собственную программу на Visual C++ или использовать один из примеров. Пример программы, используемый в этой процедуре, создает текстовый файл textfile.txt и сохраняет его в каталог проекта.

## <a name="prerequisites"></a>Предварительные требования

Эти разделы предполагают знание основ языка C++.

### <a name="to-create-a-new-project-in-visual-studio-and-add-a-new-source-file"></a>Создание проекта в Visual Studio и добавление нового исходного файла

1. Создайте новый проект. В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.

1. В списке типов проектов Visual C++ щелкните **CLR**, а затем — **Пустой проект CLR**.

   > [!NOTE]
   > Если тип **Пустой проект CLR** не отображается (только в Visual Studio 2017) выберите ссылку **Открыть Visual Studio Installer** в левой области диалогового окна **Новый проект**. Установите флажок **Поддержка C++/CLI**, расположенный в области **Разработка классических приложений C++** в разделе **необязательных компонентов**.<br/>

1. Введите имя проекта.

   По умолчанию содержащее проект решение имеет то же имя, что и новый проект, но можно ввести другое имя. При необходимости можно ввести другое расположение для проекта.

   Нажмите кнопку **ОК** для создания проекта.

1. Если **обозреватель решений** не отображается, в меню **Вид** выберите пунукт **Обозреватель решений**.

1. Добавьте новый исходный файл в проект:

   - Щелкните правой кнопкой мыши папку **Исходные файлы** в **обозревателе решений**, наведите указатель мыши на пункт **Добавить** и щелкните **Новый элемент**.

   - Щелкните элемент **Файл C++ (.cpp)**, введите имя файла и нажмите кнопу **Добавить**.

   Файл с расширением **.cpp** отображается в папке **Исходные файлы** в **обозревателе решений**, а окно с вкладками отображается в месте ввода кода в этом файле.

1. Щелкните только что созданную вкладку в Visual Studio и введите допустимую программу Visual C++ или скопируйте и вставьте один из примеров.

   Например, можно использовать пример [Практическое руководство. Запись данных в текстовый файл (C++/CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md) (в узле **File Handling and I/O** (Работа с файлами и операции ввода-вывода) руководства по программированию).

   При использовании примера обратите внимание, что при создании объекта .NET используется ключевое слово `gcnew`, а не `new`, и что `gcnew` возвращает дескриптор (`^`) вместо указателя (`*`).

   `StreamWriter^ sw = gcnew StreamWriter(fileName);`

   Дополнительные сведения о новом синтаксисе Visual C++ см. в разделе [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md).

1. В меню **Сборка** выберите **Собрать решение**.

   Окно **Вывод** отображает сведения о ходе компиляции, такие как расположение журнала сборки и сообщение о состоянии сборки.

   Если внести изменения и запустить программу, не выполняя сборку, диалоговое окно может сообщить, что проект устарел. Установите флажок в этом диалоговом окне, прежде чем нажимать кнопку **ОК**, если вы хотите, чтобы Visual Studio всегда использовала актуальные версии файлов вместо того, чтобы выводить запрос при каждой сборке приложения.

1. В меню **Отладка** выберите команду **Запуск без отладки**.

1. Если использовался пример программы, при выполнении программы отображается командное окно, указывающее, что текстовый файл был создан.

   Теперь текстовый файл **textfile.txt** находится в каталоге проекта. Этот файл можно открыть с помощью Блокнота.

   > [!NOTE]
   > При выборе пустого шаблона проекта CLR автоматически задается параметр компилятора `/clr`. Чтобы проверить это, щелкните правой кнопкой мыши проект в **обозревателе решений** и выберите **Свойства**, а затем установите флажок **Поддержка общеязыковой среды выполнения (CLR)** в узле  **Общие** окна **Свойства конфигурации**.

## <a name="whats-next"></a>Что дальше?

**Предыдущая статья:** [Пошаговое руководство. Компиляция машинной программы на языке C++ из командной строки](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
**Следующая статья:** [Пошаговое руководство. Компиляция машинной программы на языке C в командной строке](../build/walkthrough-compile-a-c-program-on-the-command-line.md)<br/>

## <a name="see-also"></a>См. также

[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Сборка программ C/C++](../build/building-c-cpp-programs.md)<br/>
