---
title: '/ Zc: referencebinding (принудительное применение правил привязки ссылок)'
ms.date: 03/06/2018
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
ms.openlocfilehash: baf2106f015a4e8557cb8469d300709694e06d84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428331"
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/ Zc: referencebinding (принудительное применение правил привязки ссылок)

Когда **/Zc: referencebinding** параметр указан, компилятор не разрешает ссылку lvalue неконстантной для привязки к временной.

## <a name="syntax"></a>Синтаксис

> **/ Zc: referencebinding**[**-**]

## <a name="remarks"></a>Примечания

Если **/Zc: referencebinding** указан, компилятор следует разделу 8.5.3 C ++ 11 standard и не поддерживает выражения, привязывающие определяемого пользователем типа временный ссылки lvalue, отличный от const. По умолчанию или если **/Zc:referenceBinding-** указан, компилятор позволяет использовать выражения, такие как расширение Microsoft, но выдается предупреждение уровня 4. Для безопасности кода, обеспечения переносимости и совместимости, мы рекомендуем использовать **/Zc: referencebinding**.

**/Zc: referencebinding** параметр отключен по умолчанию. [/ Permissive-](permissive-standards-conformance.md) параметр компилятора неявно задает этот параметр, но его можно переопределить с помощью **/Zc:referenceBinding-**.

## <a name="example"></a>Пример

В этом примере показано расширение Microsoft, которое обеспечивает создается временный определяемого пользователем типа привязываться к неконстантной lvalue ссылку.

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

void main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство **/Zc: referencebinding** и выберите **ОК**.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (соответствие)](../../build/reference/zc-conformance.md)<br/>
