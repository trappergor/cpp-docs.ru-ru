---
title: Класс task (среда выполнения с параллелизмом)
ms.date: 11/04/2016
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
ms.openlocfilehash: 99676ac0fff9584cd8453562f8918f6cadd66666
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385210"
---
# <a name="task-class-concurrency-runtime"></a>Класс task (среда выполнения с параллелизмом)

Класс `task` библиотеки параллельных шаблонов (PPL). Объект `task` представляет работу, которая может быть выполнена асинхронно и параллельно с другими задачами и параллельной работой, созданной параллельными алгоритмами в среде выполнения с параллелизмом. При успешном завершении он выводи результат типа `_ResultType`. Задачи типа `task<void>` никакого результата не дают. Задачи можно ожидать и отменять независимо от других задач. Он также может быть создан с другими задачами с помощью продолжений ( `then`) и соединения ( `when_all`) и выбор ( `when_any`) шаблоны.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class task;

template <>
class task<void>;

template<typename _ReturnType>
class task;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта задачи.

*_ReturnType*<br/>
Результирующий тип задачи.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|`result_type`|Тип результата, выводимого объектом этого класса.|

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[task](#ctor)|Перегружен. Создает объект `task`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[get](#get)|Перегружен. Возвращает результат, созданный этой задачей. Если задача не находится в конечном состоянии, вызов `get` будет ожидать завершения задачи. Этот метод не возвращает значение при вызове для задачи с параметром `result_type`, имеющим значение `void`.|
|[is_apartment_aware](#is_apartment_aware)|Определяет, распаковывает ли задача интерфейс среды выполнения Windows `IAsyncInfo` или происходит от такой задачи.|
|[is_done](#is_done)|Определяет, завершена ли задача.|
|[scheduler](#scheduler)|Возвращает планировщик для этой задачи|
|[Затем](#then)|Перегружен. Добавляет задачу продолжения к этой задаче.|
|[wait](#wait)|Ожидает, когда эта задача достигнет конечного состояния. У `wait` существует возможность выполнения задачи встроенным образом, если все зависимости задач удовлетворены, и она еще не взята для выполнения фоновым рабочим процессом.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[operator!=](#operator_neq)|Перегружен. Определяет, представляют ли два объекта `task` различные внутренние задачи.|
|[оператор=](#operator_eq)|Перегружен. Заменяет содержимое одного объекта `task` другим.|
|[operator==](#operator_eq_eq)|Перегружен. Определяет, представляют ли два объекта `task` одну и ту же внутреннюю задачу.|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`task`

## <a name="requirements"></a>Требования

**Заголовок:** ppltasks.h

**Пространство имен:** concurrency

##  <a name="get"></a> Получить

Возвращает результат, созданный этой задачей. Если задача не находится в конечном состоянии, вызов `get` будет ожидать завершения задачи. Этот метод не возвращает значение при вызове для задачи с параметром `result_type`, имеющим значение `void`.

```
_ReturnType get() const;

void get() const;
```

### <a name="return-value"></a>Возвращаемое значение

Результат задачи.

### <a name="remarks"></a>Примечания

Если задача отменяется, вызов `get` вызовет [task_canceled](task-canceled-class.md) исключение. Если задача встретила другое исключение или исключение было распространено на нее из предшествующей задачи, вызов `get` создаст это исключение.

> [!IMPORTANT]
>  В приложении универсальной платформы Windows (UWP), не следует вызывать [Concurrency::Task:: wait](#wait) или `get` ( `wait` вызовы `get`) в коде, выполняемом в потоке пользовательского интерфейса. В противном случае среда выполнения создает [concurrency::invalid_operation](invalid-operation-class.md) так, как эти методы блокирует текущий поток и может вызвать зависание приложения. Тем не менее, можно вызвать `get` метод для получения результата из предшествующей задачи в продолжение на основе задач, так как в результат доступен сразу же.

##  <a name="is_apartment_aware"></a> is_apartment_aware

Определяет, распаковывает ли задача интерфейс среды выполнения Windows `IAsyncInfo` или происходит от такой задачи.

```
bool is_apartment_aware() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если задача распаковывает `IAsyncInfo` интерфейс или является потомком такой задачи **false** в противном случае.

##  <a name="is_done"></a>  Task::is_done метод (среда выполнения с параллелизмом)

Определяет, завершена ли задача.

```
bool is_done() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение true, если задача была завершена, значение false в противном случае.

### <a name="remarks"></a>Примечания

Функция возвращает значение true, если задача завершена или отменена (с или без исключения пользователя).

##  <a name="operator_neq"></a> оператор! =

Определяет, представляют ли два объекта `task` различные внутренние задачи.

```
bool operator!= (const task<_ReturnType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Задача для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объекты ссылаются на разные базовые задачи, и **false** в противном случае.

##  <a name="operator_eq"></a> оператор =

Заменяет содержимое одного объекта `task` другим.

```
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
Исходный объект `task`.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Поскольку `task` действует как интеллектуальный указатель, после назначения копии эти объекты `task` представляют ту же фактическую задачу, что и `_Other`.

##  <a name="operator_eq_eq"></a> оператор ==

Определяет, представляют ли два объекта `task` одну и ту же внутреннюю задачу.

```
bool operator== (const task<_ReturnType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Задача для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объекты ссылаются на ту же базовую задачу и **false** в противном случае.

##  <a name="scheduler"></a>  Task::Scheduler метод (среда выполнения с параллелизмом)

Возвращает планировщик для этой задачи

```
scheduler_ptr scheduler() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на планировщик

##  <a name="ctor"></a> Задача

Создает объект `task`.

```
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
Параметр, из которого будет создаваться задача. Это может быть лямбда-выражение, объект функции `task_completion_event<result_type>` объекта или Windows::Foundation:: iasyncinfo, если задачи используются в приложении среды выполнения Windows. Лямбда-выражение или объект функции должен быть к типу, эквивалентному `std::function<X(void)>`, где X может быть переменная типа `result_type`, `task<result_type>`, или Windows::Foundation:: iasyncinfo в приложениях среды выполнения Windows.

*_TaskOptions*<br/>
Параметры задачи включают токен отмены, планировщик и др.

*_Другое*<br/>
Исходный объект `task`.

### <a name="remarks"></a>Примечания

Конструктор по умолчанию для `task` присутствует только для того, чтобы задачи могли использоваться внутри контейнеров. Собранную задачу по умолчанию невозможно использовать до тех пор, пока ей не будет присвоена допустимая задача. Методы, такие как `get`, `wait` или `then` вызовет [invalid_argument](../../../standard-library/invalid-argument-class.md) возникло исключение при вызове для задачи создаваемый по умолчанию.

Задача, которая создается из `task_completion_event`, завершится (и ее продолжения будут запланированы), если событие завершения задачи установлено.

Версия конструктора, принимающего токен отмены, создает задачу, которую можно отменить с помощью `cancellation_token_source`, из которого был получен токен. Задачи, созданные без токена отмены, не могут быть отменены.

Задачи, созданные из интерфейса `Windows::Foundation::IAsyncInfo` или лямбда-выражения, которое возвращает интерфейс `IAsyncInfo`, достигают своего конечного состояния при завершении вложенной асинхронной операции или действия среды выполнения Windows. Аналогично, задачи, созданные из лямбда-выражения, которое возвращает `task<result_type>`, достигают своего конечного состояния, когда внутренняя задача достигает своего конечного состояние, а не когда лямбда-выражение выполняет возврат.

`task` ведет себя подобно интеллектуальному указателю, и ее можно безопасно передавать по значению. К ней также может быть получен доступ несколькими потоками без необходимости использования блокировки.

Перегрузки конструктора, которые принимают интерфейс Windows::Foundation:: iasyncinfo или лямбда-выражение возвращает такой интерфейс, доступны только для приложений среды выполнения Windows.

Дополнительные сведения см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

##  <a name="then"></a> Затем

Добавляет задачу продолжения к этой задаче.

```
template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

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

*_Func*<br/>
Функция продолжения, которая должна быть выполнена по завершении этой задачи. Эта функция продолжения должна принимать в качестве входных данных переменную типа `result_type` или `task<result_type>`, где `result_type` — тип результата, который создает эта задача.

*_TaskOptions*<br/>
Параметры задачи включают токен отмены, планировщик и контекст продолжения. По умолчанию предыдущие 3 параметра наследуются от предшествующей задачи

*_CancellationToken*<br/>
Токен отмены, который необходимо связать с задачей продолжения. Задача продолжения, созданная без токена отмены, унаследует токен своей предшествующей задачи.

*_ContinuationContext*<br/>
Переменная, указывающая, где должно выполняться продолжение. Эта переменная полезна только в том случае, при использовании в приложении универсальной платформы Windows. Дополнительные сведения см. в разделе [task_continuation_context](task-continuation-context-class.md)

### <a name="return-value"></a>Возвращаемое значение

Вновь созданная задача продолжения. Тип результата возвращаемой задачи определяется значением, возвращаемым `_Func`.

### <a name="remarks"></a>Примечания

Перегрузки `then` , которые принимают лямбда-выражение или функтор, возвращающий интерфейс Windows::Foundation:: iasyncinfo, доступны только для приложений среды выполнения Windows.

Дополнительные сведения об использовании продолжения задач для составления асинхронной работы см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

##  <a name="wait"></a> Подождите

Ожидает, когда эта задача достигнет конечного состояния. У `wait` существует возможность выполнения задачи встроенным образом, если все зависимости задач удовлетворены, и она еще не взята для выполнения фоновым рабочим процессом.

```
task_status wait() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение `task_status`, которое может быть `completed` или `canceled`. Если задача встретила исключение во время выполнения или исключение было распространено на нее из предшествующей задачи, `wait` вызывает это исключение.

### <a name="remarks"></a>Примечания

> [!IMPORTANT]
>  В приложении универсальной платформы Windows (UWP), не следует вызывать `wait` в коде, выполняемом в потоке пользовательского интерфейса. В противном случае среда выполнения создает [concurrency::invalid_operation](invalid-operation-class.md) так как этот метод блокирует текущий поток и может вызвать зависание приложения. Тем не менее можно вызвать метод [concurrency::task::get](#get) для получения результата из предшествующей задачи в потоке задач.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
