---
title: __emul, __emulu
ms.date: 11/04/2016
f1_keywords:
- __emulu_cpp
- __emul
- __emul_cpp
- __emulu
helpviewer_keywords:
- __emul intrinsic
- __emulu intrinsic
ms.assetid: 79545236-cca2-40b8-a4e1-8abce9b26311
ms.openlocfilehash: 9144ce4f25d2e8e5554602533c13d5619e15360a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542459"
---
# <a name="emul-emulu"></a>__emul, __emulu

**Блок, относящийся только к системам Microsoft**

Выполняет операции умножения, которые вызывают переполнение 32-разрядное целое число, которое может содержать.

## <a name="syntax"></a>Синтаксис

```
__int64 __emul(
   int a,
   int b
);
unsigned __int64 __emulu(
   unsigned int a,
   unsigned int b
);
```

#### <a name="parameters"></a>Параметры

*a*<br/>
[in] Первый операнд целочисленный результат умножения.

*b*<br/>
[in] Второй операнд целочисленный результат умножения.

## <a name="return-value"></a>Возвращаемое значение

Результат умножения.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__emul`|x86, x64|
|`__emulu`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

`__emul` принимает два 32-разрядных значений со знаком и возвращает результат умножения как 64-разрядное целое число со знаком.

`__emulu` принимает два значения 32-разрядного целого числа без знака и возвращает результат умножения как значение 64-разрядного целого числа без знака.

## <a name="example"></a>Пример

```
// emul.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__emul)
#pragma intrinsic(__emulu)

int main()
{
   int a = -268435456;
   int b = 2;

   __int64 result = __emul(a, b);

   cout << a << " * " << b << " = " << result << endl;

   unsigned int ua = 0xFFFFFFFF; // Dec value: 4294967295
   unsigned int ub = 0xF000000;  // Dec value: 251658240

   unsigned __int64 uresult = __emulu(ua, ub);

   cout << ua << " * " << ub << " = " << uresult << endl;

}
```

## <a name="output"></a>Вывод

```
-268435456 * 2 = -536870912
4294967295 * 251658240 = 1080863910317260800
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)