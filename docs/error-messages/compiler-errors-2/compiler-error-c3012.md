---
title: Ошибка компилятора C3012
ms.date: 11/04/2016
f1_keywords:
- C3012
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
ms.openlocfilehash: 9fe0ac7d3637cad3a5571c4631345dac1a0021bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503102"
---
# <a name="compiler-error-c3012"></a>Ошибка компилятора C3012

> "*внутренние*": встроенная функция, не допускается непосредственно внутри параллельной области

[Встроенная функция компилятора](../../intrinsics/compiler-intrinsics.md) не может находиться в области `omp parallel` . Чтобы устранить эту проблему, встроенные функции можно вывести из области или замените невстроенный эквиваленты.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3012 и показан один из способов ее устранения:

```cpp
// C3012.cpp
// compile with: /openmp
#ifdef __cplusplus
extern "C" {
#endif
void* _ReturnAddress();
#ifdef __cplusplus
}
#endif

int main()
{
   #pragma omp parallel
   {
      _ReturnAddress();   // C3012
   }
   _ReturnAddress();      // OK
}
```