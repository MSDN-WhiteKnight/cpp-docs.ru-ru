---
title: Ошибка средств компоновщика LNK1256
ms.date: 11/04/2016
f1_keywords:
- xml
- LNK1256
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
ms.openlocfilehash: 9d969d1e5bbae92ed49747f761c1b89d1910d4e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492883"
---
# <a name="linker-tools-error-lnk1256"></a>Ошибка средств компоновщика LNK1256

Ошибка операции ALINK : причина

Наиболее частая причина LNK1256 — неверный номер версии сборки. Значение 65535 не может быть использовано в любой части номера версии сборки. Допустимый диапазон версий сборок: 0 – 65534.

LNK1256 может возникнуть в случае, если ALINK не удается найти именованный контейнер ключа. Удалите контейнер ключа и снова добавить его в CSP строгое имя с помощью [Sn.exe (средство строгих имен)](/dotnet/framework/tools/sn-exe-strong-name-tool).

Еще одна возможная причина ошибки LNK1256 — несовпадение версий компоновщика и Alink.dll. Это может быть вызвано поврежденной установкой Visual Studio. Используйте **программы и компоненты** на панели управления Windows для восстановления или переустановки Visual Studio.

Следующий пример приводит к возникновению ошибки LNK1256:

```
// LNK1256.cpp
// compile with: /clr /LD
// LNK1256 expected
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];
public class CMyClass {
public:
   int value;
};
```