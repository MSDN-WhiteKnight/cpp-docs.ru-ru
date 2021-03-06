---
title: longjmp
ms.date: 08/14/2018
apiname:
- longjmp
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- longjmp
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
ms.openlocfilehash: e5189ff7cb850acd9c9a1280f47fc9a1270f8b68
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211008"
---
# <a name="longjmp"></a>longjmp

Восстанавливает стека среды и выполнение языковому стандарту, установленному `setjmp` вызова.

## <a name="syntax"></a>Синтаксис

```C
void longjmp(
   jmp_buf env,
   int value
);
```

### <a name="parameters"></a>Параметры

*env*<br/>
Переменная, в которой хранится среда.

*value*<br/>
Значение, возвращаемое в вызов `setjmp`.

## <a name="remarks"></a>Примечания

**Longjmp** функция восстанавливает стека среды и языковой стандарт выполнения ранее сохраненных в *env* по `setjmp`. `setjmp` и **longjmp** предоставляют способ выполнения нелокальной команды **goto**; обычно они используются для передачи управления выполнением в код обработки ошибок или восстановления в вызванной ранее подпрограмме без использования обычных вызовов и соглашениями о возвратах.

Вызов `setjmp` вызывает текущую среду стека должен быть сохранен в *env*. Последующий вызов **longjmp** восстанавливает сохраненную среду и возвращает управление в точку, в следующую сразу за соответствующим `setjmp` вызова. Выполнение возобновляется так, как если бы параметр *value* был только что возвращен в результате вызова функции `setjmp`. Значения всех переменных (за исключением регистровых переменных), доступные для получившей управление подпрограммы, содержат те значения, они имели при **longjmp** был вызван. Значения регистровых переменных непредсказуемы. Значение, возвращаемое функцией `setjmp`, должно быть ненулевым. Если переданный параметр *value* равен 0, фактическое возвращаемое значение будет равно 1.

**Блок, относящийся только к системам Microsoft**

В коде Microsoft C++ в Windows **longjmp** использует ту же семантику, развертывание стека как код обработки исключений. Его можно безопасно использовать в тех же расположениях, возникновения исключения C++. Однако такое использование не является переносимым и поставляется с некоторые важные предупреждения.

Вызывать только **longjmp** перед функции, вызвавшей `setjmp` возвращает; в противном случае результаты непредсказуемы.

Соблюдайте следующие ограничения при использовании **longjmp**:

- Не рассчитывайте на то, что значения регистровых переменных останутся теми же. Значения регистровых переменных в подпрограмму, вызывающем `setjmp` не могут быть восстановлены по соответствующими значениями после **longjmp** выполняется.

- Не используйте **longjmp** для передачи управления из подпрограммы обработки прерываний, если прерывание не вызвано с исключением плавающей запятой. В этом случае программа может выполнять возврат из обработчика прерываний посредством **longjmp** если она сначала повторно инициализирует пакет вычисления с плавающей запятой путем вызова [_fpreset](fpreset.md).

- Не используйте **longjmp** для передачи управления из подпрограммы обратного вызова, вызываемые кодом, Windows прямо или косвенно.

- Если код компилируется с помощью **/EHs** или **/EHsc** и функции, которая содержит **longjmp** вызов **noexcept** затем локальных объектов в том, что функция не может быть уничтожены во время очистки стека.

**Завершение блока, относящегося только к системам Майкрософт**

> [!NOTE]
> В переносимом коде C++, нельзя рассчитывать на `setjmp` и `longjmp` поддерживают семантику объекта C++. В частности `setjmp` / `longjmp` пары приводит к неопределенному поведению замены вызова `setjmp` и `longjmp` по **catch** и **throw** вызовет нетривиальные деструкторы для любой автоматически создаваемых объектов. В программах на C++ мы рекомендуем использовать механизм обработки исключений C++.

Дополнительные сведения см. в разделе [Использование setjmp и longjmp](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**longjmp**|\<setjmp.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [_fpreset](fpreset.md).

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[setjmp](setjmp.md)
