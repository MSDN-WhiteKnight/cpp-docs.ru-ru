---
title: '&lt;c&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- <c>
helpviewer_keywords:
- <c> C++ XML tag
- c C++ XML tag
ms.assetid: 3b23fc0f-e10d-4dd0-b197-48a46cbddd9f
ms.openlocfilehash: 1efb411537e07ae9a5c2e4a70b5fa3ac319d79c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431100"
---
# <a name="ltcgt-visual-c"></a>&lt;c&gt; (Visual C++)

С помощью тега \<c> можно указать, что текст в описании нужно пометить как код. Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](../ide/code-visual-cpp.md).

## <a name="syntax"></a>Синтаксис

```
<c>text</c>
```

#### <a name="parameters"></a>Параметры

*текст*<br/>
Текст, который нужно указать в качестве кода.

## <a name="remarks"></a>Примечания

Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).

## <a name="example"></a>Пример

```cpp
// xml_c_tag.cpp
// compile with: /doc /LD
// post-build command: xdcmake xml_c_tag.xdc

/// Text for class MyClass.
class MyClass {
public:
   int m_i;
   MyClass() : m_i(0) {}

   /// <summary><c>MyMethod</c> is a method in the <c>MyClass</c> class.
   /// </summary>
   int MyMethod(MyClass * a) {
      return a -> m_i;
   }
};
```

## <a name="see-also"></a>См. также

[Документация XML](../ide/xml-documentation-visual-cpp.md)