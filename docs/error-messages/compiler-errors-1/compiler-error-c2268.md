---
title: Ошибка компилятора C2268
ms.date: 11/04/2016
f1_keywords:
- C2268
helpviewer_keywords:
- C2268
ms.assetid: 0ed055c9-3c6f-4df2-a5b6-85cf0e01a249
ms.openlocfilehash: cfdb22be92e0d80cddbaca74b12b7af60b2e302d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545734"
---
# <a name="compiler-error-c2268"></a>Ошибка компилятора C2268

"функция" представляет определяемый компилятором модуль поддержки библиотеки. Модули поддержки библиотек не поддерживаются с параметром /GL; компилируйте объектный файл "файл" без параметра /GL.

Имя функции, определенной в исходном коде, совпадает с именем внутренней функции компилятора. Скомпилируйте модуль, содержащий функцию, без параметра [/GL](../../build/reference/gl-whole-program-optimization.md).

Следующий пример приводит к возникновению ошибки C2268:

```
// C2268.c
// compile with: /c
// processor: x86
extern int SHFusionLoadLibrary(int lpLibFileName);

int __cdecl _except_handler3(void) {
   return SHFusionLoadLibrary(0);
}

extern int main(void);

void* mainCRTStartup(void* p) {
   p = main;
   return p;
}
```

затем:

```
// C2268b.c
// compile with: C2268.c /EHsc /GL /Ob0 /O2 /Fa /GS- /link /nodefaultlib
// processor: x86
extern int SHFusionLoadLibrary(int lpLibFileName);

extern int __cdecl _except_handler3(void);
extern void mainCRTStartup(void*);
int g = 2;

#define ENTERCONTEXT(fail) \
   int ulCookie = 0;\
   if (!SHActivateContext(&ulCookie)) \
      return fail;\
   __try {

#define LEAVECONTEXT \
    } __finally {SHDeactivateContext(ulCookie);}

int SHActivateContext(int* a) {
    return *a == g || !*a ||_except_handler3();
}

void SHDeactivateContext(int a) {
    g = a;
}

int SHFusionLoadLibrary(int lpLibFileName) {   // C2268
    ENTERCONTEXT(0)
    g = lpLibFileName;
    LEAVECONTEXT

    return lpLibFileName;
}

int main(void) {
    g = SHFusionLoadLibrary(10);
    return 0;
}
```