---
title: / Validate/CharSet (Проверка совместимости символов)
ms.date: 02/06/2019
f1_keywords:
- /validate-charset
- validate-charset
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
ms.openlocfilehash: 69b43b603ef4711e1acc0bd612e0e1c949722dc9
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850082"
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/ Validate/CharSet (Проверка совместимости символов)

Проверяет, что исходный текст файла содержит только символы можно представить как UTF-8.

## <a name="syntax"></a>Синтаксис

```
/validate-charset[-]
```

## <a name="remarks"></a>Примечания

Можно использовать **/Validate/CharSet** параметр, чтобы проверить, что исходный код содержит только набор символов, которые могут быть представлены в исходной кодировки и кодировки выполнения. Эта проверка включается автоматически при указании **кодировки/Source**, **/Execution-CharSet**, или **/UTF-8** параметры компилятора. Можно явно отключить эту проверку, указав **/ validate-charset -** параметр.

По умолчанию Visual Studio определяет метку порядка байтов, чтобы определить, если исходный файл в кодировке Юникод, например, UTF-16 или UTF-8. При обнаружении нет метка порядка байтов предполагается исходный файл закодирован при помощи текущей кодовой странице пользователя, пока не задана кодовая страница с помощью **/UTF-8** или **кодировки/Source** параметр. Visual Studio позволяет сохранить исходный код C++ с помощью любого из несколькими кодировками символов. Сведения об источнике и кодировка выполнения, см. в разделе [кодировки](../../cpp/character-sets.md) в документации по языкам. Для получения списка поддерживаемых идентификаторы кодовой страницы и кодировка имен, см. в разделе [идентификаторы кодовой страницы](/windows/desktop/Intl/code-page-identifiers).

Visual Studio использует UTF-8 в качестве внутренней кодировки при преобразовании между исходная кодировка и кодировка выполнения. Если символ в исходном файле невозможно представить в кодировке выполнения, преобразования UTF-8 заменяет знак вопроса "?" символов. **/Validate/CharSet** предписывает компиляция отправлять предупреждение, если это происходит.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните **свойства конфигурации**, **C/C++**, **командной строки** папки.

1. В **Дополнительные параметры**, добавьте **/Validate/CharSet** и задайте предпочтительной кодировки.

1. Выберите **ОК** для сохранения внесенных изменений.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[/ Execution-CharSet (задать выполнение кодировки)](../../build/reference/execution-charset-set-execution-character-set.md)<br/>
[/source/charset (задание исходной кодировки)](../../build/reference/source-charset-set-source-character-set.md)<br/>
[/utf/8 (указание UTF/8 в качестве исходной кодировки и кодировки исполняемого файла)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)