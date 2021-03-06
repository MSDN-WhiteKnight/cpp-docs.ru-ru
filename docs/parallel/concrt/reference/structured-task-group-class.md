---
title: Класс structured_task_group
ms.date: 11/04/2016
f1_keywords:
- structured_task_group
- PPL/concurrency::structured_task_group
- PPL/concurrency::structured_task_group::structured_task_group
- PPL/concurrency::structured_task_group::cancel
- PPL/concurrency::structured_task_group::is_canceling
- PPL/concurrency::structured_task_group::run
- PPL/concurrency::structured_task_group::run_and_wait
- PPL/concurrency::structured_task_group::wait
helpviewer_keywords:
- structured_task_group class
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
ms.openlocfilehash: 27610539ab500a113ea41021744c55425fe9cd9b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299300"
---
# <a name="structuredtaskgroup-class"></a>Класс structured_task_group

Класс `structured_task_group` представляет коллекцию параллельной работы со сложной структурой. Можно поместить в очередь `structured_task_group` отдельные параллельные задачи с помощью объектов `task_handle` и ожидать их выполнения или отменить группу задач до завершения выполнения, что приведет к отмене всех задач, которые не начали выполнение.

## <a name="syntax"></a>Синтаксис

```
class structured_task_group;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[structured_task_group](#ctor)|Перегружен. Создает новый `structured_task_group` объекта.|
|[~ structured_task_group деструктор](#dtor)|Уничтожает объект `structured_task_group`. Вы должны вызвать либо метод `wait` или `run_and_wait` метода объекта до выполнения деструктора, если деструктор не выполняется в результате использования стека из-за исключения.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Отмена](#cancel)|Делает гарантируется и осуществляется попытка отменить поддерево с корнем в эту группу задач работы. Все задачи, запланированные в группе задач отменяются транзитивно, если это возможно.|
|[is_canceling](#is_canceling)|Сообщает вызывающей стороне, находится ли группа задач состоянии отмены. Это не обязательно означает, что `cancel` метод был вызван для `structured_task_group` объекта (хотя это определенно позволяет этот метод для возврата **true**). Может оказаться так, `structured_task_group` объекта выполняется встроено и в группу задач вверх в дереве рабочего была отменена. В случаях, например сред, среда выполнения может определить заранее, что отмена будет передаваться через этот `structured_task_group` объекта, **true** будет возвращено.|
|[run](#run)|Перегружен. Планирует задачу на `structured_task_group` объекта. Вызывающий объект управляет временем существования `task_handle` переданный объект `_Task_handle` параметра. Версия, которая принимает параметр `_Placement`, заставляет задачу стремиться к выполнению в расположении, указанном этим параметром.|
|[run_and_wait](#run_and_wait)|Перегружен. Планирует задачу для выполнения встроено в контексте вызова с помощью `structured_task_group` объекта для поддержки полной отмены. Если `task_handle` объект передается в качестве параметра `run_and_wait`, вызывающий объект отвечает за управление временем существования `task_handle` объекта. Функция затем ожидает, пока все работают на `structured_task_group` объекта завершена или отменена.|
|[wait](#wait)|Ожидает, пока все работают на `structured_task_group` завершена или отменена.|

## <a name="remarks"></a>Примечания

Существует ряд серьезных ограничений, налагаемых на использование `structured_task_group` объекта с целью повышения производительности:

- Один `structured_task_group` объект не может использоваться несколькими потоками. Все операции в `structured_task_group` должен выполнить объект потока, в котором был создан объект. Два исключения из этого правила являются функции-члены `cancel` и `is_canceling`. Объект не может быть в списке записи лямбда-выражения и использоваться в задаче, если задача не использует одну из операций отмены.

- Все задачи, запланированные для `structured_task_group` объект планируются помощи `task_handle` которого необходимо явно управлять временем существования объектов.

- Несколько групп могут использоваться только абсолютно вложенных порядку. Если два `structured_task_group` объявляются объекты, второй объявляемого (внутреннее тот) необходимо уничтожения перед вызовом любого метода, за исключением `cancel` или `is_canceling` вызывается в первый из них (один внешний). Это условие справедливо и в случае простого объявления нескольких `structured_task_group` объектов в том же или функционально вложенных областей, а также в случае задачу, которая поставлено в очередь `structured_task_group` через `run` или `run_and_wait` методы.

- В отличие от общих `task_group` класса, все состояния в `structured_task_group` класса являются окончательными. После помещения задач в очередь группы и ожидания их завершения невозможно использовать ту же группу снова.

Дополнительные сведения см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`structured_task_group`

## <a name="requirements"></a>Требования

**Заголовок:** ppl.h

**Пространство имен:** concurrency

##  <a name="cancel"></a> Отмена

Делает гарантируется и осуществляется попытка отменить поддерево с корнем в эту группу задач работы. Все задачи, запланированные в группе задач отменяются транзитивно, если это возможно.

```
void cancel();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [отмены](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

##  <a name="is_canceling"></a> is_canceling

Сообщает вызывающей стороне, находится ли группа задач состоянии отмены. Это не обязательно означает, что `cancel` метод был вызван для `structured_task_group` объекта (хотя это определенно позволяет этот метод для возврата **true**). Может оказаться так, `structured_task_group` объекта выполняется встроено и в группу задач вверх в дереве рабочего была отменена. В случаях, например сред, среда выполнения может определить заранее, что отмена будет передаваться через этот `structured_task_group` объекта, **true** будет возвращено.

```
bool is_canceling();
```

### <a name="return-value"></a>Возвращаемое значение

Указание, следует ли `structured_task_group` объекта, в процессе отмены (или гарантированно будет вскоре).

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [отмены](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

##  <a name="run"></a> запустить

Планирует задачу на `structured_task_group` объекта. Вызывающий объект управляет временем существования `task_handle` переданный объект `_Task_handle` параметра. Версия, которая принимает параметр `_Placement`, заставляет задачу стремиться к выполнению в расположении, указанном этим параметром.

```
template<class _Function>
void run(
    task_handle<_Function>& _Task_handle);

template<class _Function>
void run(
    task_handle<_Function>& _Task_handle,
    location& _Placement);
```

### <a name="parameters"></a>Параметры

*_Function*<br/>
Тип объекта функции, который будет вызываться для выполнения основной дескриптор задач.

*_Task_handle*<br/>
Дескриптор запланированных работ. Обратите внимание, что вызывающий объект отвечает за время существования этого объекта. Среда выполнения будет продолжать ожидать, что его срок жизни либо до `wait` или `run_and_wait` об этом будет вызван метод `structured_task_group` объекта.

*Р_азмещения*<br/>
Ссылка на расположение, в котором должна выполняться задача, представленная параметром `_Task_handle`.

### <a name="remarks"></a>Примечания

Среда выполнения создает копию рабочей функции, который передается этому методу. Изменения состояния, которые происходят в объект функции, который передается этому методу будет отсутствовать в копии этого объекта функции.

Если `structured_task_group` destructs в результате очистки стека из исключения, вы не обязательно должны гарантировать, что вызовы выполнялись либо `wait` или `run_and_wait` метод. В этом случае деструктор будет соответствующим образом отменить и ожидать задачу, представленную `_Task_handle` параметра, чтобы завершить.

Создает [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) исключение, если задача обрабатывать предоставленное `_Task_handle` параметр уже был запланирован на объектом группы задач с помощью `run` метода и не промежуточным вызовом либо `wait` или `run_and_wait` метод для этой группы задач.

##  <a name="run_and_wait"></a> run_and_wait

Планирует задачу для выполнения встроено в контексте вызова с помощью `structured_task_group` объекта для поддержки полной отмены. Если `task_handle` объект передается в качестве параметра `run_and_wait`, вызывающий объект отвечает за управление временем существования `task_handle` объекта. Функция затем ожидает, пока все работают на `structured_task_group` объекта завершена или отменена.

```
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```

### <a name="parameters"></a>Параметры

*_Function*<br/>
Тип объекта функции, который будет вызываться для выполнения задачи.

*_Task_handle*<br/>
Дескриптор задачу, которая будет запускаться встроенной в контексте вызова. Обратите внимание, что вызывающий объект отвечает за время существования этого объекта. Среда выполнения будет продолжать ожидать доживают до `run_and_wait` метод завершает выполнение.

*_Func*<br/>
Функция, которая будет вызываться для вызова тела часть работы. Это может быть лямбда-выражение или другой объект, который поддерживает версию оператора вызова функции с сигнатурой `void operator()()`.

### <a name="return-value"></a>Возвращаемое значение

Указание того, было ли выполнено ожидания или группа задач была отменена, из-за явного Отмена операции или к возникновению исключения из одной из задач. Дополнительные сведения см. в разделе [task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>Примечания

Обратите внимание, что один или несколько задач, запланированных к этому `structured_task_group` объекта может выполняться встроено в контекст вызова.

Если один или несколько задач, назначенных данному `structured_task_group` объекта создает исключение, среда выполнения выбирает одно такое исключение и распространить из вызова `run_and_wait` метод.

После возврата этой функции объект `structured_task_group` находится в конечном состоянии и не должен использоваться. Обратите внимание, что использование после `run_and_wait` метод возвращает приведет к неопределенному поведению.

В пути выполнения без поддержки исключений, имеется обязательное требование для вызова либо этот метод или `wait` метод до деструктора `structured_task_group` выполняет.

##  <a name="ctor"></a> structured_task_group

Создает новый `structured_task_group` объекта.

```
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```

### <a name="parameters"></a>Параметры

*_CancellationToken*<br/>
Токен отмены, чтобы связать с этой группы структурированных задач. Группы структурированных задач отменяется при отмене токена.

### <a name="remarks"></a>Примечания

Конструктор, который принимает токен отмены, создает `structured_task_group`, которая будет отменена, когда будет отменен источник, связанный с этим токеном. Предоставление явного токена отмены также изолирует этой группы структурированных задач из участия в неявной отмене из родительской группы с другим токеном или без токена.

##  <a name="dtor"></a> ~structured_task_group

Уничтожает объект `structured_task_group`. Вы должны вызвать либо метод `wait` или `run_and_wait` метода объекта до выполнения деструктора, если деструктор не выполняется в результате использования стека из-за исключения.

```
~structured_task_group();
```

### <a name="remarks"></a>Примечания

Если деструктор выполняется как результат обычного выполнения (например, не очистки стека из-за исключения) и ни `wait` , ни `run_and_wait` был вызван метод, деструктор может вызвать [missing_wait](missing-wait-class.md) исключение.

##  <a name="wait"></a> Подождите

Ожидает, пока все работают на `structured_task_group` завершена или отменена.

```
task_group_status wait();
```

### <a name="return-value"></a>Возвращаемое значение

Указание того, было ли выполнено ожидания или группа задач была отменена, из-за явного Отмена операции или к возникновению исключения из одной из задач. Дополнительные сведения см. в разделе [task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>Примечания

Обратите внимание, что один или несколько задач, запланированных к этому `structured_task_group` объекта может выполняться встроено в контекст вызова.

Если один или несколько задач, назначенных данному `structured_task_group` объекта создает исключение, среда выполнения выбирает одно такое исключение и распространить из вызова `wait` метод.

После возврата этой функции объект `structured_task_group` находится в конечном состоянии и не должен использоваться. Обратите внимание, что использование после `wait` метод возвращает приведет к неопределенному поведению.

В пути выполнения без поддержки исключений, имеется обязательное требование для вызова либо этот метод или `run_and_wait` метод до деструктора `structured_task_group` выполняет.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс task_group](task-group-class.md)<br/>
[Класс task_handle](task-handle-class.md)
