---
title: Класс task (среда выполнения с параллелизмом)
ms.date: 07/30/2019
f1_keywords:
- task
- PPLTASKS/concurrency::task
- PPLTASKS/concurrency::task::task
- PPLTASKS/concurrency::task::get
- PPLTASKS/concurrency::task::is_apartment_aware
- PPLTASKS/concurrency::task::is_done
- PPLTASKS/concurrency::task::scheduler
- PPLTASKS/concurrency::task::then
- PPLTASKS/concurrency::task::wait
helpviewer_keywords:
- task class
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
ms.openlocfilehash: d42c7fbd3e065fc295027b7c56e207b2a49221bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358738"
---
# <a name="task-class-concurrency-runtime"></a>Класс task (среда выполнения с параллелизмом)

Класс `task` библиотеки параллельных шаблонов (PPL). Объект `task` представляет работу, которая может выполняться асинхронно и одновременно с другими задачами и параллельной работой, производимой параллельными алгоритмами в параллельном Runtime. При успешном завершении он выводи результат типа `_ResultType`. Задачи типа `task<void>` никакого результата не дают. Задачи можно ожидать и отменять независимо от других задач. Он также может быть составлен с `then`другими задачами, используя продолжения (), и присоединиться ( `when_all`) и выбор () `when_any`шаблоны. Когда объект задачи присваивается новой переменной, поведение является `std::shared_ptr`поведением; другими словами, оба объекта представляют одну и ту же основную задачу.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
class task<void>;

template<typename _ResultType>
class task;
```

### <a name="parameters"></a>Параметры

*_ResultType*<br/>
Тип результата, который производит задача.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`result_type`|Тип результата, выводимого объектом этого класса.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Задача](#ctor)|Перегружен. Формирует объект `task`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[get](#get)|Перегружен. Возвращает результат, созданный этой задачей. Если задача не находится в конечном состоянии, вызов `get` будет ожидать завершения задачи. Этот метод не возвращает значение при вызове для задачи с параметром `result_type`, имеющим значение `void`.|
|[is_apartment_aware](#is_apartment_aware)|Определяет, распаковывает ли задача интерфейс среды выполнения Windows `IAsyncInfo` или происходит от такой задачи.|
|[is_done](#is_done)|Определяет, завершена ли задача.|
|[Планировщик](#scheduler)|Возвращает планировщик для этой задачи|
|[Затем](#then)|Перегружен. Добавляет задачу продолжения к этой задаче.|
|[Подожди](#wait)|Ожидает, когда эта задача достигнет конечного состояния. У `wait` существует возможность выполнения задачи встроенным образом, если все зависимости задач удовлетворены, и она еще не взята для выполнения фоновым рабочим процессом.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператора!](#operator_neq)|Перегружен. Определяет, представляют ли два объекта `task` различные внутренние задачи.|
|[оператора](#operator_eq)|Перегружен. Заменяет содержимое одного объекта `task` другим.|
|[оператора](#operator_eq_eq)|Перегружен. Определяет, представляют ли два объекта `task` одну и ту же внутреннюю задачу.|

## <a name="remarks"></a>Remarks

Для получения дополнительной информации [см.](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`task`

## <a name="requirements"></a>Требования

**Заголовок:** ppltasks.h

**Название:** параллелизм

## <a name="get"></a><a name="get"></a>Получить

Возвращает результат, созданный этой задачей. Если задача не находится в конечном состоянии, вызов `get` будет ожидать завершения задачи. Этот метод не возвращает значение при вызове для задачи с параметром `result_type`, имеющим значение `void`.

```cpp
_ResultType get() const;

void get() const;
```

### <a name="return-value"></a>Возвращаемое значение

Результат задачи.

### <a name="remarks"></a>Remarks

Если задача отменена, вызов, который `get` будет task_canceled исключением. [task_canceled](task-canceled-class.md) Если задача встретила другое исключение или исключение было распространено на нее из предшествующей задачи, вызов `get` создаст это исключение.

> [!IMPORTANT]
> В приложении Universal Windows Platform (UWP) не звоните в `get` [параллел::task::wait](#wait) или (звонки) `wait` `get`в коде, который работает на потоке пользовательского интерфейса. В противном случае время выполнения бросает [параллель::invalid_operation,](invalid-operation-class.md) потому что эти методы блокируют текущий поток и могут привести к тому, что приложение станет безответным. Тем не менее, `get` можно вызвать метод для получения результата предшествующей задачи в продолжении задачи, поскольку результат сразу же доступен.

## <a name="is_apartment_aware"></a><a name="is_apartment_aware"></a>is_apartment_aware

Определяет, распаковывает ли задача интерфейс среды выполнения Windows `IAsyncInfo` или происходит от такой задачи.

```cpp
bool is_apartment_aware() const;
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если задача разворачивает `IAsyncInfo` интерфейс или происходит от такой задачи, **ложно** в противном случае.

## <a name="taskis_done-method-concurrency-runtime"></a><a name="is_done"></a>задача::is_done метод (Время выполнения параллели)

Определяет, завершена ли задача.

```cpp
bool is_done() const;
```

### <a name="return-value"></a>Возвращаемое значение

Правда, если задача выполнена, ложное в противном случае.

### <a name="remarks"></a>Remarks

Функция возвращается, если задача выполнена или отменена (с исключением пользователя или без него).

## <a name="operator"></a><a name="operator_neq"></a>оператора!

Определяет, представляют ли два объекта `task` различные внутренние задачи.

```cpp
bool operator!= (const task<_ResultType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Задача для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если объекты относятся к различным базовым задачам, и **ложные** в противном случае.

## <a name="operator"></a><a name="operator_eq"></a>оператора

Заменяет содержимое одного объекта `task` другим.

```cpp
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Исходный объект `task`.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

Поскольку `task` действует как интеллектуальный указатель, после назначения копии эти объекты `task` представляют ту же фактическую задачу, что и `_Other`.

## <a name="operator"></a><a name="operator_eq_eq"></a>оператора

Определяет, представляют ли два объекта `task` одну и ту же внутреннюю задачу.

```cpp
bool operator== (const task<_ResultType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Задача для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если объекты относятся к той же основной задаче, и **ложные** в противном случае.

## <a name="taskscheduler-method-concurrency-runtime"></a><a name="scheduler"></a>задача::планер ный метод (Курсна терпясь по времени выполнения)

Возвращает планировщик для этой задачи

```cpp
scheduler_ptr scheduler() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на планировщик

## <a name="task"></a>Задача <a name="ctor"></a>

Формирует объект `task`.

```cpp
task();

template<typename T>
__declspec(
    noinline) explicit task(T _Param);

template<typename T>
__declspec(
    noinline) explicit task(T _Param, const task_options& _TaskOptions);

task(
    const task& _Other);

task(
    task&& _Other);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип параметра, из которого будет создаваться задача.

*_Param*<br/>
Параметр, из которого будет создаваться задача. Это может быть лямбда, объект `task_completion_event<result_type>` функции, объект или Windows::Foundation:::IAsyncInfo, если вы используете задачи в приложении Windows Runtime. Lambda или объект функции должен `std::function<X(void)>`быть тип эквивалентно , `result_type`где `task<result_type>`X может быть переменной типа , или Windows::Основа::IAsyncInfo в Windows Runtime приложений.

*_TaskOptions*<br/>
Параметры задачи включают токен отмены, планировщик и др.

*_Other*<br/>
Исходный объект `task`.

### <a name="remarks"></a>Remarks

Конструктор по умолчанию для `task` присутствует только для того, чтобы задачи могли использоваться внутри контейнеров. Собранную задачу по умолчанию невозможно использовать до тех пор, пока ей не будет присвоена допустимая задача. Такие методы, `wait` `then` как `get`, или будет бросать [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение при вызове на задачу построена по умолчанию.

Задача, которая создается из `task_completion_event`, завершится (и ее продолжения будут запланированы), если событие завершения задачи установлено.

Версия конструктора, принимающего токен отмены, создает задачу, которую можно отменить с помощью `cancellation_token_source`, из которого был получен токен. Задачи, созданные без токена отмены, не могут быть отменены.

Задачи, созданные из интерфейса `Windows::Foundation::IAsyncInfo` или лямбда-выражения, которое возвращает интерфейс `IAsyncInfo`, достигают своего конечного состояния при завершении вложенной асинхронной операции или действия среды выполнения Windows. Аналогичным образом, задачи, созданные из `task<result_type>` лямбды, которая возвращает достичь своего конечного состояния, когда внутренняя задача достигает своего конечного состояния, а не когда лямбда возвращается.

`task` ведет себя подобно интеллектуальному указателю, и ее можно безопасно передавать по значению. К ней также может быть получен доступ несколькими потоками без необходимости использования блокировки.

Конструктор перегружает, которые принимают Windows::Foundation::::IAsyncInfo интерфейс или lambda возвращения такого интерфейса, доступны только для Windows Runtime приложений.

Для получения дополнительной информации [см.](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)

## <a name="then"></a><a name="then"></a>Затем

Добавляет задачу продолжения к этой задаче.

```cpp
template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func) const -> typename details::_ContinuationTypeTraits<_Function,
    _ResultType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions) const -> typename details::_ContinuationTypeTraits<_Function,
    _ResultType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    _ResultType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions = task_options()) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;
```

### <a name="parameters"></a>Параметры

*_Function*<br/>
Тип объекта функции, который будет вызываться этой задачей.

*_func*<br/>
Функция продолжения, которая должна быть выполнена по завершении этой задачи. Эта функция продолжения должна принимать в качестве входных данных переменную типа `result_type` или `task<result_type>`, где `result_type` — тип результата, который создает эта задача.

*_TaskOptions*<br/>
Параметры задачи включают токен отмены, планировщик и контекст продолжения. По умолчанию предыдущие 3 параметра наследуются от предшествующей задачи

*_CancellationToken*<br/>
Токен отмены, который необходимо связать с задачей продолжения. Задача продолжения, созданная без токена отмены, унаследует токен своей предшествующей задачи.

*_ContinuationContext*<br/>
Переменная, указывающая, где должно выполняться продолжение. Эта переменная полезна только при использовании в приложении UWP. Для получения дополнительной информации см [task_continuation_context.](task-continuation-context-class.md)

### <a name="return-value"></a>Возвращаемое значение

Вновь созданная задача продолжения. Тип результата возвращаемой задачи определяется значением, возвращаемым `_Func`.

### <a name="remarks"></a>Remarks

`then` Перегрузки, которые принимают lambda или functor, который возвращает Windows::Основа:::IAsyncInfo интерфейс, доступны только для Windows Runtime приложений.

Для получения дополнительной информации о том, как использовать продолжение задач для составления асинхронной работы, [см.](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)

## <a name="wait"></a><a name="wait"></a>Подожди

Ожидает, когда эта задача достигнет конечного состояния. У `wait` существует возможность выполнения задачи встроенным образом, если все зависимости задач удовлетворены, и она еще не взята для выполнения фоновым рабочим процессом.

```cpp
task_status wait() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение `task_status`, которое может быть `completed` или `canceled`. Если задача встретила исключение во время выполнения или исключение было распространено на нее из предшествующей задачи, `wait` вызывает это исключение.

### <a name="remarks"></a>Remarks

> [!IMPORTANT]
> В приложении Universal Windows Platform (UWP) не вызывайте `wait` код, который работает на потоке пользовательского интерфейса. В противном случае среда выполнения создает [concurrency::invalid_operation](invalid-operation-class.md) так как этот метод блокирует текущий поток и может вызвать зависание приложения. Тем не менее можно вызвать метод [concurrency::task::get](#get) для получения результата из предшествующей задачи в потоке задач.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
