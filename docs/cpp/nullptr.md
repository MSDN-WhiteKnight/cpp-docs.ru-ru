---
title: nullptr
ms.date: 11/04/2016
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: fc210679553c393143c7e94121dd75e19b934dd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637116"
---
# <a name="nullptr"></a>nullptr

Обозначает константу-указатель NULL типа `std::nullptr_t`, которая может быть преобразована к любому типу необработанного указателя.  Несмотря на то, что можно использовать ключевое слово **nullptr** без включения любые заголовки, если код использует тип `std::nullptr_t`, а затем необходимо определить его, включая заголовок `<cstddef>`.

> [!NOTE]
>  **Nullptr** ключевое слово также определяется в C + +/ CLI для приложений управляемого кода и оно не взаимозаменяемо с ключевым словом языка C++ стандарта ISO. Если ваш код может компилироваться с помощью [/CLR](../build/reference/clr-common-language-runtime-compilation.md) параметр компилятора, который нацелен на управляемый код, затем с помощью `__nullptr` в любую строку кода, где необходимо обеспечить, чтобы компилятор использовал собственную интерпретацию C++. Дополнительные сведения см. в разделе [nullptr](../windows/nullptr-cpp-component-extensions.md).

## <a name="remarks"></a>Примечания

Старайтесь не использовать значение NULL или нуль (`0`) как константа указателя null; **nullptr** менее уязвимо для неправильного использования и лучше работает в большинстве ситуаций.  Например, если для функции `func(std::pair<const char *, double>)` произвести вызов `func(std::make_pair(NULL, 3.14))`, возникнет ошибка компилятора.  Макрос NULL разворачивается в `0`, поэтому вызов `std::make_pair(0, 3.14)` возвращает значение `std::pair<int, double>`, которое невозможно преобразовать к типу параметра `std::pair<const char *, double>` функции func().  Вызов `func(std::make_pair(nullptr, 3.14))` успешно компилируется, поскольку `std::make_pair(nullptr, 3.14)` возвращает значение `std::pair<std::nullptr_t, double>`, которое допускает преобразование в тип `std::pair<const char *, double>`.

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[nullptr](../windows/nullptr-cpp-component-extensions.md)