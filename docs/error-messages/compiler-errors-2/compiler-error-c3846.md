---
title: Ошибка компилятора C3846
ms.date: 11/04/2016
f1_keywords:
- C3846
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
ms.openlocfilehash: 788f03e4364404ad5c30b7edcba8b743c7f201ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651221"
---
# <a name="compiler-error-c3846"></a>Ошибка компилятора C3846

«символ»: не удается импортировать символ из «сборка2»: «символ» уже был импортирован из другой сборки «сборка1»

Не удалось импортировать символ в указанной сборке, так как он ранее был импортирован из указанной сборки.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3846:

```
// C3846a.cpp
// compile with: /LD /clr
public ref struct G
{
};
```

И затем Скомпилируйте следующий:

```
// C3846b.cpp
// compile with: /clr
#using "c3846a.dll"
#using "c3846a.obj"   // C3846

int main()
{
}
```
