---
title: Редактор сведений о версии (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.version.F1
- vc.editors.version
helpviewer_keywords:
- Version Information editor [C++], about Version Information editor
- editors, Version Information
- resource editors [C++], Version Information editor
- version information resources [C++]
- resources [C++], editing version information
- languages, version information
- New Version Info Block
- blocks, adding
- resources [C++], adding version information
- version information, adding for languages
- blocks, deleting
- version information, deleting blocks
- resources [C++], deleting version information
- VerQueryValue
- version information, accessing from within programs
- GetFileVersionInfo
- version information
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
ms.openlocfilehash: 8382371acfd423f8c6864e816b0357e3ef11718e
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210982"
---
# <a name="version-information-editor-c"></a>Редактор сведений о версии (C++)

Сведения о версии включают идентификационные данные о компании и продукте, номер версии продукта и уведомление об авторских правах и товарных знаках. С помощью **редактор сведений о версии**, можно создать и поддерживать эти данные, которые хранятся в ресурсе сведений о версии. Ресурс сведений о версии не требуется приложением, но он удобен для сбора сведений, идентифицирующий приложение. Сведения о версии также используются API-интерфейсами настройки.

> [!NOTE]
> Стандарт Windows разрешает наличие только одного ресурса сведений о версии, который называется VS_VERSION_INFO.

Ресурс сведений о версии содержит верхний блок и один или несколько нижних блоков: один блок фиксированных сведений вверху и один или несколько блоков сведений о версии внизу (для других языков или кодировок). Верхний блок содержит как редактируемые числовые поля, так и раскрывающиеся списки с вариантами для выбора. Нижние блоки содержат только редактируемые текстовые поля.

> [!NOTE]
> При использовании **редактор сведений о версии**, во многих случаях можно щелкнуть правой кнопкой мыши для отображения контекстное меню связанных с ресурсом команд. Например, если выбрана при указании заголовке блока, контекстное меню показано **новый блок сведений о версии** и **удалить блок сведений о версии** команды.

## <a name="how-to"></a>Практические руководства

**Редактор сведений о версии** позволяет:

### <a name="to-edit-a-string-in-a-version-information-resource"></a>Изменение строки в ресурсе сведений о версии

Выберите элемент один раз, чтобы затем еще раз выберите его, чтобы приступить к редактированию. Внести изменения непосредственно в **сведения о версии** таблицы или в [окно "Свойства"](/visualstudio/ide/reference/properties-window). Внесенные изменения будут отображаться и там, и там.

При редактировании `FILEFLAGS` в **редактор сведений о версии**, обратите внимание, что нельзя задать **Отладка**, **Private Build**, или **Special Build**  свойств в **свойства** окно для RC-файлов:

   - **Редактор сведений о версии** задает **Отладка** свойство с `#ifdef` в сценарии ресурса, на основе `_DEBUG` флага сборки.

  - Если `Private Build` ключ имеет **значение** в **сведения о версии** таблицы, соответствующий **Private Build** свойство в **свойства**  окно для `FILEFLAGS` ключ будет **True**. Если **значение** является пустой, это свойство будет иметь **False**. Аналогичным образом **Special Build** в **сведения о версии** таблицы привязан к **Special Build** свойство для `FILEFLAGS` ключ.

Вы можно отсортировать строки в блоке, выбирая **ключ** или **значение** заголовки столбцов. В результате сведения автоматически будут отображаться в порядке, заданном сортировкой.

### <a name="to-add-version-information-for-another-language-new-version-info-block"></a>Добавление сведений о версии для другого языка (новый блок сведений о версии)

1. Откройте ресурс сведений о версии, дважды щелкнув его в [представлении ресурсов](../windows/resource-view-window.md).

1. Щелкните правой кнопкой мыши внутри таблицы сведений о версии и выберите **новый блок сведений о версии**.

   Эта команда добавляет дополнительный блок сведений в текущий ресурс сведений о версии и открывает его соответствующие свойства в [окне "Свойства"](/visualstudio/ide/reference/properties-window).

1. В окне **Свойства** выберите для нового блока соответствующие язык и кодировку.

### <a name="to-delete-a-version-information-block"></a>Удаление блока сведений о версии

1. Откройте ресурс сведений о версии, дважды щелкнув его значок в [представлении ресурсов](../windows/resource-view-window.md).

1. Щелкните правой кнопкой мыши заголовок удаляемого блока, который вы хотите удалить и выберите **удалить блок сведений о версии**.

   Эта команда удаляет выбранный заголовок и оставляет оставшиеся сведения о версии нетронутыми. Действие нельзя отменить.

### <a name="to-access-version-information-from-within-your-program"></a>Доступ к сведениям о версии из создаваемой программы

Если нужно получить доступ к сведениям о версии из создаваемой программы, используйте функции [GetFileVersionInfo](/windows/desktop/api/winver/nf-winver-getfileversioninfoa) и [VerQueryValue](/windows/desktop/api/winver/nf-winver-verqueryvaluea) .

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редакторы ресурсов](../windows/resource-editors.md)<br/>
<!--
[Menus and Other Resources](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)<br/>
[Version Information (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)-->
