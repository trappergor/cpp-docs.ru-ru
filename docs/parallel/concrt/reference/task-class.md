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
ms.openlocfilehash: e0f876b3c0971e70763f36622fb72a3dea671461
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682521"
---
# <a name="task-class-concurrency-runtime"></a>Класс task (среда выполнения с параллелизмом)

Класс `task` библиотеки параллельных шаблонов (PPL). `task` Объект представляет работу, которая может быть выполнена асинхронно и параллельно с другими задачами, а также параллелизмом, созданными параллельными алгоритмами в среда выполнения с параллелизмом. При успешном завершении он выводи результат типа `_ResultType`. Задачи типа `task<void>` никакого результата не дают. Задачи можно ожидать и отменять независимо от других задач. Он также может состоять из других задач, использующих `then`шаблоны продолжения () и `when_all`объединения () и `when_any`Choice (). Когда объект Task назначается новой переменной, поведение состоит в том, что, `std::shared_ptr`иными словами, оба объекта представляют одну и ту же базовую задачу.

## <a name="syntax"></a>Синтаксис

```
template <>
class task<void>;

template<typename _ResultType>
class task;
```

#### <a name="parameters"></a>Параметры

*_ResultType*<br/>
Тип результата, который создает задача. 

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
|[этого](#then)|Перегружен. Добавляет задачу продолжения к этой задаче.|
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

**Заголовок:** из ppltasks. h

**Пространство имен:** concurrency

##  <a name="get"></a>Получить

Возвращает результат, созданный этой задачей. Если задача не находится в конечном состоянии, вызов `get` будет ожидать завершения задачи. Этот метод не возвращает значение при вызове для задачи с параметром `result_type`, имеющим значение `void`.

```
_ResultType get() const;

void get() const;
```

### <a name="return-value"></a>Возвращаемое значение

Результат задачи.

### <a name="remarks"></a>Примечания

Если задача отменена, вызов метода `get` вызывает исключение [task_canceled](task-canceled-class.md) . Если задача встретила другое исключение или исключение было распространено на нее из предшествующей задачи, вызов `get` создаст это исключение.

> [!IMPORTANT]
>  В приложении универсальная платформа Windows (UWP) не вызывайте [Concurrency:: Task:: wait](#wait) или `get` ( `wait` Calls `get`) в коде, который выполняется в потоке пользовательского интерфейса. В противном случае среда выполнения создает [Concurrency:: invalid_operation](invalid-operation-class.md) , так как эти методы блокируют текущий поток и могут привести к тому, что приложение перестанет отвечать на запросы. Однако можно вызвать `get` метод, чтобы получить результат предшествующей задачи в продолжении на основе задачи, так как результат сразу же доступен.

##  <a name="is_apartment_aware"></a>is_apartment_aware

Определяет, распаковывает ли задача интерфейс среды выполнения Windows `IAsyncInfo` или происходит от такой задачи.

```
bool is_apartment_aware() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если задача разворачивает `IAsyncInfo` интерфейс или в порядке убывания от такой задачи; в противном случае — **значение false** .

##  <a name="is_done"></a>Метод Task:: is_done (среда выполнения с параллелизмом)

Определяет, завершена ли задача.

```
bool is_done() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение true, если задача завершена; в противном случае — значение false.

### <a name="remarks"></a>Примечания

Функция возвращает значение true, если задача завершена или отменена (с исключением пользователя или без него).

##  <a name="operator_neq"></a>operator! =

Определяет, представляют ли два объекта `task` различные внутренние задачи.

```
bool operator!= (const task<_ResultType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Сравниваемая задача.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если объекты ссылаются на разные базовые задачи, и **false** в противном случае.

##  <a name="operator_eq"></a>Оператор =

Заменяет содержимое одного объекта `task` другим.

```
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Исходный объект `task`.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Поскольку `task` действует как интеллектуальный указатель, после назначения копии эти объекты `task` представляют ту же фактическую задачу, что и `_Other`.

##  <a name="operator_eq_eq"></a>Оператор = =

Определяет, представляют ли два объекта `task` одну и ту же внутреннюю задачу.

```
bool operator== (const task<_ResultType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Сравниваемая задача.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если объекты ссылаются на одну и ту же базовую задачу, и **false** в противном случае.

##  <a name="scheduler"></a>Метод Task:: Scheduler (среда выполнения с параллелизмом)

Возвращает планировщик для этой задачи

```
scheduler_ptr scheduler() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на планировщик

##  <a name="ctor"></a>задачи

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
Параметр, из которого будет создаваться задача. Это может быть лямбда, объект функции, `task_completion_event<result_type>` объект или Windows:: Foundation:: иасинЦинфо, если вы используете задачи в приложении среда выполнения Windows. Лямбда-выражение или объект функции должен быть типом `std::function<X(void)>`, эквивалентным, где X может быть переменной типа `result_type`, `task<result_type>`или Windows:: Foundation:: иасинЦинфо в приложениях среда выполнения Windows.

*_TaskOptions*<br/>
Параметры задачи включают токен отмены, планировщик и др.

*_Other*<br/>
Исходный объект `task`.

### <a name="remarks"></a>Примечания

Конструктор по умолчанию для `task` присутствует только для того, чтобы задачи могли использоваться внутри контейнеров. Собранную задачу по умолчанию невозможно использовать до тех пор, пока ей не будет присвоена допустимая задача. Такие методы, `get`как `wait` или `then` , вызовут исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) при вызове в созданной по умолчанию задаче.

Задача, которая создается из `task_completion_event`, завершится (и ее продолжения будут запланированы), если событие завершения задачи установлено.

Версия конструктора, принимающего токен отмены, создает задачу, которую можно отменить с помощью `cancellation_token_source`, из которого был получен токен. Задачи, созданные без токена отмены, не могут быть отменены.

Задачи, созданные из интерфейса `Windows::Foundation::IAsyncInfo` или лямбда-выражения, которое возвращает интерфейс `IAsyncInfo`, достигают своего конечного состояния при завершении вложенной асинхронной операции или действия среды выполнения Windows. Аналогично, задачи, созданные из лямбда-выражения, которое возвращает `task<result_type>`, достигают своего конечного состояния, когда внутренняя задача достигает своего конечного состояние, а не когда лямбда-выражение выполняет возврат.

`task` ведет себя подобно интеллектуальному указателю, и ее можно безопасно передавать по значению. К ней также может быть получен доступ несколькими потоками без необходимости использования блокировки.

Перегрузки конструктора, которые принимают интерфейс Windows:: Foundation:: ИасинЦинфо или лямбда-выражение, возвращающие такой интерфейс, доступны только для среда выполнения Windows приложений.

Дополнительные сведения см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

##  <a name="then"></a>этого

Добавляет задачу продолжения к этой задаче.

```
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

*_Func*<br/>
Функция продолжения, которая должна быть выполнена по завершении этой задачи. Эта функция продолжения должна принимать в качестве входных данных переменную типа `result_type` или `task<result_type>`, где `result_type` — тип результата, который создает эта задача.

*_TaskOptions*<br/>
Параметры задачи включают токен отмены, планировщик и контекст продолжения. По умолчанию предыдущие 3 параметра наследуются от предшествующей задачи

*_CancellationToken*<br/>
Токен отмены, который необходимо связать с задачей продолжения. Задача продолжения, созданная без токена отмены, унаследует токен своей предшествующей задачи.

*_ContinuationContext*<br/>
Переменная, указывающая, где должно выполняться продолжение. Эта переменная полезна только при использовании в приложении UWP. Дополнительные сведения см. в разделе [task_continuation_context](task-continuation-context-class.md)

### <a name="return-value"></a>Возвращаемое значение

Вновь созданная задача продолжения. Тип результата возвращаемой задачи определяется значением, возвращаемым `_Func`.

### <a name="remarks"></a>Примечания

Перегрузки `then` , которые принимают лямбда-выражение или функтор, возвращающие интерфейс Windows:: Foundation:: иасинЦинфо, доступны только для Среда выполнения Windows приложений.

Дополнительные сведения об использовании продолжений задач для создания асинхронной работы см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

##  <a name="wait"></a>ожидания

Ожидает, когда эта задача достигнет конечного состояния. У `wait` существует возможность выполнения задачи встроенным образом, если все зависимости задач удовлетворены, и она еще не взята для выполнения фоновым рабочим процессом.

```
task_status wait() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение `task_status`, которое может быть `completed` или `canceled`. Если задача встретила исключение во время выполнения или исключение было распространено на нее из предшествующей задачи, `wait` вызывает это исключение.

### <a name="remarks"></a>Примечания

> [!IMPORTANT]
>  В приложении универсальная платформа Windows (UWP) не вызывайте `wait` в коде, который выполняется в потоке пользовательского интерфейса. В противном случае среда выполнения создает [concurrency::invalid_operation](invalid-operation-class.md) так как этот метод блокирует текущий поток и может вызвать зависание приложения. Тем не менее можно вызвать метод [concurrency::task::get](#get) для получения результата из предшествующей задачи в потоке задач.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
