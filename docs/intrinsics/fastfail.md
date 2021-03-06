---
title: __fastfail
ms.date: 11/04/2016
ms.assetid: 9cd32639-e395-4c75-9f3a-ac3ba7f49921
ms.openlocfilehash: e96d981be5c5186d6cc472cc8f4dffcbf1c2b7bf
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849480"
---
# <a name="fastfail"></a>__fastfail

**Блок, относящийся только к системам Microsoft**

Немедленно завершает вызывающий процесс с минимальными издержками.

## <a name="syntax"></a>Синтаксис

```
void __fastfail(unsigned int code);
```

#### <a name="parameters"></a>Параметры

*код*<br/>
[in] Объект `FAST_FAIL_<description>` символьную константу из winnt.h или wdm.h, указывающая на причину завершения процесса.

## <a name="return-value"></a>Возвращаемое значение

Встроенная `__fastfail` не возвращается.

## <a name="remarks"></a>Примечания

`__fastfail` Предоставляет механизм для *быстрый сбой* запроса — это способ для потенциально поврежденный процесс запрашивает немедленное завершение процесса. Критические сбои, которые могут привести к повреждению состояния программы и стека после восстановления, не могут быть обработаны обычным механизмом обработки исключений. Используйте `__fastfail` для завершения процесса с минимальными издержками.

Внутренне `__fastfail` реализуется с помощью несколько механизмов в зависимости от конкретной архитектуры:

|Архитектура|Инструкция|Расположение аргумента кода|
|------------------|-----------------|-------------------------------|
|x86|int 0x29|ecx|
|X64|int 0x29|rcx|
|ARM|Код операции 0xDEFB|r0|
|ARM64|Код операции 0xF003|x0|

Запрос быстрого сбоя является самодостаточным и обычно требует только две команды для выполнения. После выполнения запроса быстрого сбоя ядро предпринимает соответствующие действия. В коде пользовательского режима отсутствуют зависимости памяти за пределами самого указателя инструкций, когда происходит событие быстрого сбоя. Это увеличивает его надежность, даже в случае серьезного повреждения памяти.

Аргумент `code` — одна из символьных констант `FAST_FAIL_<description>`  из winnt.h или wdm.h — описывает тип состояния ошибки и включается в отчеты об ошибке в соответствии с конкретной средой.

Запросы пользовательского режима быстрого сбоя отображаются как второй экземпляр не допускающее исключения с кодом исключения 0xC0000409 и исключение по крайней мере один параметр. Первый параметр исключения — значение `code` . Этот код исключения указывает  Windows Error Reporting (WER) и инфраструктуре отладки, что процесс поврежден и минимальные действия внутри процесса необходимы в ответ на сбой. Запросы быстрого сбоя в режиме ядра реализованы с помощью особого отладочного кода, `KERNEL_SECURITY_CHECK_FAILURE` (0x139). В обоих случаях обработчики исключений не вызываются, поскольку программа предположительно в поврежденном состоянии. Если отладчик присутствует, ему дается возможность проверки состояния программы перед завершением.

Поддержка собственного механизма быстрого сбоя началась с Windows 8. Операционные системы Windows, которые изначально не поддерживают инструкцию быстрого сбоя, обычно будут рассматривать запрос на быстрый сбой как нарушение прав доступа или как код отладки `UNEXPECTED_KERNEL_MODE_TRAP`. В этих случаях программа по-прежнему завершается, но не обязательно как можно быстрее.

`__fastfail` доступна только как встроенная.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__fastfail`|x86, x 64, ARM, ARM64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)
