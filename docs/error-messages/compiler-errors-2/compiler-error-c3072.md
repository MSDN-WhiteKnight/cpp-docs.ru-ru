---
title: Ошибка компилятора C3072
ms.date: 11/04/2016
f1_keywords:
- C3072
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
ms.openlocfilehash: 34b5cff9191814b2a16a42d9e234bab09f29c117
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490029"
---
# <a name="compiler-error-c3072"></a>Ошибка компилятора C3072

оператор «оператор» не может применяться к экземпляру класса ref

использовать унарный "`operator` " оператор преобразования экземпляра класса ref в тип дескриптора

Тип CLR требуется операторы среды CLR, не операторы собственные (или standard).  Дополнительные сведения см. в разделе [оператор отслеживания ссылок](../../windows/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3072.

```
// C3072.cpp
// compile with: /clr
ref class R {};

int main() {
   R r1;
   R^ r2 = &r1;   // C3072
   R^ r3 = %r1;   // OK
}
```