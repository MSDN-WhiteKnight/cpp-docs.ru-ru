---
title: Ошибка компилятора C3489
ms.date: 11/04/2016
f1_keywords:
- C3489
helpviewer_keywords:
- C3489
ms.assetid: 47b58d69-459d-4499-abc7-5f0b9303d773
ms.openlocfilehash: a3ea5fa30a54603d15da8e515dab672c0e058e60
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660737"
---
# <a name="compiler-error-c3489"></a>Ошибка компилятора C3489

Переменная "var" обязательна, если режимом по умолчанию является передача параметров по значению

Если вы указываете, что для лямбда-выражения режимом по умолчанию является передача по значению, то в предложение передачи этого выражения нельзя передать переменную по значению.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Не передавайте переменную в предложение передачи явным образом или

- не указывайте режим передачи по значению в качестве режима по умолчанию.

- Укажите в качестве режима по умолчанию режим передачи по ссылке.

- Передайте переменную в предложение передачи по ссылке. (Это может изменить поведение лямбда-выражения.)

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3489, так как переменная `n` передается по значению в предложение передачи лямбда-выражения, режим передачи по умолчанию которого — по значению:

```
// C3489a.cpp

int main()
{
   int n = 5;
   [=, n]() { return n; } (); // C3489
}
```

## <a name="example"></a>Пример

В следующем примере показано четыре возможных способа устранения ошибки C3489.

```
// C3489b.cpp

int main()
{
   int n = 5;

   // Possible resolution 1:
   // Do not explicitly pass n to the capture clause.
   [=]() { return n; } ();

   // Possible resolution 2:
   // Do not specify by-value as the default capture mode.
   [n]() { return n; } ();

   // Possible resolution 3:
   // Specify by-reference as the default capture mode.
   [&, n]() { return n; } ();

   // Possible resolution 4:
   // Pass n by reference to the capture clause.
   [&n]() { return n; } ();
}
```

## <a name="see-also"></a>См. также

[Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)