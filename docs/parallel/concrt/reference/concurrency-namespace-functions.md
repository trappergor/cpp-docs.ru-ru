---
title: Функции пространства имен concurrency
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::Alloc
- concrt/concurrency::DisableTracing
- concrt/concurrency::EnableTracing
- concrtrm/concurrency::GetExecutionContextId
- concrtrm/concurrency::GetOSVersion
- concrtrm/concurrency::GetProcessorNodeCount
- concrtrm/concurrency::GetSchedulerId
- agents/concurrency::asend
- ppltasks/concurrency::cancel_current_task
- ppltasks/concurrency::create_async
- ppltasks/concurrency::create_task
- concurrent_vector/concurrency::internal_assign_iterators
- ppl/concurrency::interruption_point
- agents/concurrency::make_choice
- agents/concurrency::make_greedy_join
- ppl/concurrency::make_task
- ppl/concurrency::parallel_buffered_sort
- ppl/concurrency::parallel_for_each
- ppl/concurrency::parallel_invoke
- ppl/concurrency::parallel_reduce
- ppl/concurrency::parallel_sort
- agents/concurrency::receive
- ppl/concurrency::run_with_cancellation_token
- pplconcrt/concurrency::set_ambient_scheduler
- concrt/concurrency::set_task_execution_resources
- ppltasks/concurrency::task_from_exception
- ppltasks/concurrency::task_from_result
- concrt/concurrency::wait
- ppltasks/concurrency::when_all
- ppltasks/concurrency::when_any
ms.assetid: 520a6dff-9324-4df2-990d-302e3050af6a
ms.openlocfilehash: 15b265744640628425502706d69fd98a1c64bda2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374372"
---
# <a name="concurrency-namespace-functions"></a>Функции пространства имен concurrency

||||
|-|-|-|
|[Alloc](#alloc)|[СоздатьРесурсменеджер](#createresourcemanager)|[ОтключитьТрейсы](#disabletracing)|
|[ВключитьТрассировку](#enabletracing)|[Бесплатный](#free)|[GetExecutionКонтекст](#getexecutioncontextid)|
|[GetOSVersion](#getosversion)|[GetProcessorCount](#getprocessorcount)|[GetProcessorNodeCount](#getprocessornodecount)|
|[GetSchedulerId](#getschedulerid)|[Trace_agents_register_name](#trace_agents_register_name)|[асенд](#asend)|
|[cancel_current_task](#cancel_current_task)|[Ясно](#clear)|[create_async](#create_async)|
|[create_task](#create_task)|[get_ambient_scheduler](#get_ambient_scheduler)|[internal_assign_iterators](#internal_assign_iterators)|
|[interruption_point](#interruption_point)|[is_current_task_group_canceling](#is_current_task_group_canceling)|[make_choice](#make_choice)|
|[make_greedy_join](#make_greedy_join)|[make_join](#make_join)|[make_task](#make_task)|
|[parallel_buffered_sort](#parallel_buffered_sort)|[Parallel_for](#parallel_for)|[Parallel_for_each](#parallel_for_each)|
|[parallel_invoke](#parallel_invoke)|[parallel_radixsort](#parallel_radixsort)|[Parallel_reduce](#parallel_reduce)|
|[parallel_sort](#parallel_sort)|[parallel_transform](#parallel_transform)|[Получить](#receive)|
|[run_with_cancellation_token](#run_with_cancellation_token)|[send](#send)|[set_ambient_scheduler](#set_ambient_scheduler)|
|[set_task_execution_resources](#set_task_execution_resources)|[Своп](#swap)|[task_from_exception](#task_from_exception)|
|[task_from_result](#task_from_result)|[try_receive](#try_receive)|[Подожди](#wait)|
|[When_all](#when_all)|[When_any](#when_any)|

## <a name="alloc"></a><a name="alloc"></a>Alloc

Выделяет блок памяти указанного размера из подраспределителя кэширования среды параллелизма.

```cpp
void* __cdecl Alloc(size_t _NumBytes);
```

### <a name="parameters"></a>Параметры

*_NumBytes*<br/>
Количество байтов памяти для выделения.

### <a name="return-value"></a>Возвращаемое значение

Указатель на недавно выделенную память.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о том, какие сценарии в приложении могут быть полезны при использовании Suballocator, [см.](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)

## <a name="asend"></a><a name="asend"></a>асенд

Асинхронная операция отправки, которая планирует задачу для распространения данных в целевой блок.

```cpp
template <class T>
bool asend(
    _Inout_ ITarget<T>* _Trg,
    const T& _Data);

template <class T>
bool asend(
    ITarget<T>& _Trg,
    const T& _Data);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип отправляемых данных.

*_Trg*<br/>
Указатель или ссылка на цель, к которой отправляются данные.

*_Data*<br/>
Ссылка на данные, которые будут отправлены.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если сообщение было принято до того, как метод вернулся, **ложное** в противном случае.

### <a name="remarks"></a>Remarks

Для получения дополнительной [Message Passing Functions](../../../parallel/concrt/message-passing-functions.md)информации см.

## <a name="cancel_current_task"></a><a name="cancel_current_task"></a>cancel_current_task

Отменяет выполняющуюся в данный момент задачу. Эту функцию можно вызывать из тела задачи, чтобы прервать выполнение задачи и перевести ее в состояние `canceled`.

Вызов этой функции является неподдерживаемым сценарием, если вы не находитесь в теле `task`. Такие действия приведут к неопределенному поведению, например сбою или зависанию в приложении.

```cpp
inline __declspec(noreturn) void __cdecl cancel_current_task();
```

## <a name="clear"></a><a name="clear"></a>Ясно

Очищает одновременный утес, уничтожая все элементы, которые в настоящее время окунают. Этот метод не является валютным.

```cpp
template<typename T, class _Ax>
void concurrent_queue<T, _Ax>::clear();
```

### <a name="parameters"></a>Параметры

*T*<br/>

*_Ax*<br/>

## <a name="create_async"></a><a name="create_async"></a>create_async

Создает асинхронную конструкцию среды выполнения Windows на основе предоставленного пользователем лямбда-выражения или объекта функции. Тип возвращаемого значения `create_async` — один из следующих: `IAsyncAction^`, `IAsyncActionWithProgress<TProgress>^`, `IAsyncOperation<TResult>^` или `IAsyncOperationWithProgress<TResult, TProgress>^`, в зависимости от сигнатуры лямбда-выражения, переданного методу.

```cpp
template<typename _Function>
__declspec(noinline) auto create_async(const _Function& _Func)
    -> decltype(ref new details::_AsyncTaskGeneratorThunk<_Function>(_Func));
```

### <a name="parameters"></a>Параметры

*_Function*<br/>
Введите ,

*_func*<br/>
Лямбда-выражение или объект функции, из которого требуется создать асинхронную конструкцию среды выполнения Windows.

### <a name="return-value"></a>Возвращаемое значение

Асинхронная конструкция, представленная IAsyncAction, IAsyncActionProgress\<TProgress>,, IAsyncOperation\<TResult>,или IAsyncOperationWithProgress\<TResult, TProgress>. Возвращаемый интерфейс зависит от сигнатуры лямбда-выражения, переданного функции.

### <a name="remarks"></a>Remarks

Возвращаемый тип лямбда-выражения определяет, чем является конструкция — действием или операцией.

Лямбда-выражения, возвращающие значение void, приводят к созданию действий. Лямбда-выражения, возвращающие результат типа `TResult`, приводят к созданию операций TResult.

Лямбда-выражение может также возвращать объект `task<TResult>`, который инкапсулирует асинхронную работу внутри себя или является продолжением цепочки задач, представляющих асинхронную работу. В этом случае лямбда-выражение само выполняется встроенным образом, поскольку задачами являются те, которые выполняются асинхронно, и возвращаемый тип лямбда-выражения распаковывается для создания асинхронной конструкции, возвращаемой `create_async`. Это означает, что лямбда, которая возвращает задачу\<пустоту> вызовет создание\<действий, и лямбда, которая возвращает задачу TResult> вызовет создание операций TResult.

Лямбда-выражение может принимать ноль, один или два аргумента. Допустимые аргументы — `progress_reporter<TProgress>` и `cancellation_token`, в этом порядке, если используются оба. Лямбда-выражение без аргументов вызывает создание асинхронной конструкции без возможности выдачи отчета о ходе выполнения. Лямбда, которая\<принимает progress_reporter TProgress>, вызовет `create_async` возврат асинхронной конструкции, `report` которая сообщает о ходе выполнения типа TProgress каждый раз, когда метод progress_reporter объекта называется. Лямбда-выражение, которое принимает cancellation_token, может использовать этот токен для проверки отмены или передать создаваемым им задачам, чтобы отмена асинхронной конструкции приводила к отмене этих задач.

Если тело лямбды или функционального объекта возвращает\<результат (а не задачу TResult>), lamdba будет выполнена асинхронно в процессе MTA в контексте задачи Runtime неявно создает для него. Метод `IAsyncInfo::Cancel` вызовет отмену неявной задачи.

Если тело лямбда-выражения возвращает задачу, лямбда-выражение выполняется встроенным образом, и путем объявления, чтобы лямбда-выражение принимало аргумент типа `cancellation_token`, можно привести в действие отмену всех задач, создаваемых внутри лямбда-выражения путем передачи этого токена при их создании. Можно также использовать метод `register_callback` для этого токена, чтобы вызвать выполнение исполняющей средой обратного вызова при вызове `IAsyncInfo::Cancel` для созданной асинхронной операции или действия.

Эта функция доступна только для приложений Windows Runtime.

## <a name="createresourcemanager"></a><a name="createresourcemanager"></a>СоздатьРесурсменеджер

Возвращает интерфейс, который представляет одноэлементный экземпляр диспетчера ресурсов среды выполнения с параллелизмом. Диспетчер ресурсов отвечает за назначение ресурсов планировщикам, которым требуется взаимодействовать друг с другом.

```cpp
IResourceManager* __cdecl CreateResourceManager();
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IResourceManager`.

### <a name="remarks"></a>Remarks

Несколько последующих вызовов к этому методу вернут один и тот же экземпляр диспетчера ресурсов. Каждый вызов метода начисляет ссылку на менеджера ресурсов и должен быть сопоставлен с вызовом в [IResourceManager::Release](iresourcemanager-structure.md) метод, когда ваш планировщик закончил общаться с менеджером ресурсов.

[unsupported_os](unsupported-os-class.md) брошен, если операционная система не поддерживается Concurrency Runtime.

## <a name="create_task"></a><a name="create_task"></a>create_task

Создает объект [задачи](task-class.md) PPL. Функция `create_task` может использоваться в любой ситуации, где бы вы использовали конструктор задач. Она предоставлена главным образом для удобства, поскольку позволяет использовать ключевое слово `auto` при создании задач.

```cpp
template<typename T>
__declspec(noinline) auto create_task(T _Param, const task_options& _TaskOptions = task_options())
    -> task<typename details::_TaskTypeFromParam<T>::T>;

template<typename _ReturnType>
__declspec( noinline) task<_ReturnType> create_task(const task<_ReturnType>& _Task);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип параметра, из которого будет создаваться задача.

*_ReturnType*<br/>
Введите ,

*_Param*<br/>
Параметр, из которого будет создаваться задача. Это может быть ламбда или `task_completion_event` функциональный объект, объект, другой `task` объект или Windows::Foundation:::IAsyncInfo интерфейс, если вы используете задачи в вашем приложении UWP.

*_TaskOptions*<br/>
Параметры задачи.

*_Task*<br/>
Задача, которую требуется создать.

### <a name="return-value"></a>Возвращаемое значение

Новая задача типа `T`, что вывод `_Param`из .

### <a name="remarks"></a>Remarks

Первая перегрузка ведет себя как конструктор задачи, который принимает один параметр.

Вторая перегрузка связывает токен отмены с вновь созданной задачей. При использовании этой перегрузки вам не `task` разрешается проходить в другом объекте в качестве первого параметра.

Тип возвращенной задачи выводит из первого параметра в функцию. Если `_Param` `task_completion_event<T>`это, `task<T>`a , или functor, `T` `task<T>`который возвращает либо типа `task<T>`или , тип созданной задачи.

В приложении UWP, `_Param` если тип Windows::Основа::IAsyncOperation\<T>или Windows::Foundation::IAsyncOperationWithProgress\<T, P>, или functor, который возвращает `task<T>`любой из этих типов, созданная задача будет типа . Если `_Param` тип Windows::Foundation:::IAsyncAction или Windows::Foundation:::IAsyncActionProgress\<P>, или functor, который возвращает любой `task<void>`из этих типов, созданная задача будет иметь тип .

## <a name="disabletracing"></a><a name="disabletracing"></a>ОтключитьТрейсы

Отключает трассировку в среде выполнения с параллелизмом. Эту функция не рекомендуется использовать, поскольку трассировка событий Windows по умолчанию не регистрируется.

```cpp
__declspec(deprecated("Concurrency::DisableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl DisableTracing();
```

### <a name="return-value"></a>Возвращаемое значение

Если трассировка была `S_OK` правильно отключена, возвращается. Если трассировка не была запущена ранее, возвращается `E_NOT_STARTED`

## <a name="enabletracing"></a><a name="enabletracing"></a>ВключитьТрассировку

Включает трассировку в среде выполнения с параллелизмом. Эта функция не рекомендована к использованию, поскольку трассировка событий Windows теперь по умолчанию включена.

```cpp
__declspec(deprecated("Concurrency::EnableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl EnableTracing();
```

### <a name="return-value"></a>Возвращаемое значение

Если трассировка была `S_OK` правильно инициирована, возвращается; в `E_NOT_STARTED` противном случае возвращается.

## <a name="free"></a><a name="free"></a>Бесплатный

Освобождает блок памяти, ранее выделенный методом `Alloc` для подраспределителя кэширования среды выполнения с параллелизмом.

```cpp
void __cdecl Free(_Pre_maybenull_ _Post_invalid_ void* _PAllocation);
```

### <a name="parameters"></a>Параметры

*_PAllocation*<br/>
Указатель на память, ранее `Alloc` выделенную методом, который должен быть освобожден. Если параметр `_PAllocation` установлен в `NULL`значении, этот метод будет игнорировать его и немедленно вернуться.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о том, какие сценарии в приложении могут быть полезны при использовании Suballocator, [см.](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)

## <a name="get_ambient_scheduler"></a><a name="get_ambient_scheduler"></a>get_ambient_scheduler

```cpp
inline std::shared_ptr<::Concurrency::scheduler_interface> get_ambient_scheduler();
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="getexecutioncontextid"></a><a name="getexecutioncontextid"></a>GetExecutionКонтекст

Возвращает уникальный идентификатор, который можно назначить контексту выполнения, реализующему интерфейс `IExecutionContext`.

```cpp
unsigned int __cdecl GetExecutionContextId();
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор для контекста выполнения.

### <a name="remarks"></a>Remarks

Используйте этот метод для получения идентификатора для контекста выполнения перед тем, как передать `IExecutionContext` интерфейс в качестве параметра любому из методов, предлагаемых диспетчером ресурсов.

## <a name="getosversion"></a><a name="getosversion"></a>GetOSVersion

Возвращает версию операционной системы.

```cpp
IResourceManager::OSVersion __cdecl GetOSVersion();
```

### <a name="return-value"></a>Возвращаемое значение

Перечисленное значение, представляющее операционную систему.

### <a name="remarks"></a>Remarks

[unsupported_os](unsupported-os-class.md) брошен, если операционная система не поддерживается Concurrency Runtime.

## <a name="getprocessorcount"></a><a name="getprocessorcount"></a>GetProcessorCount

Возвращает число аппаратных потоков базовой системы.

```cpp
unsigned int __cdecl GetProcessorCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество аппаратных потоков.

### <a name="remarks"></a>Remarks

[unsupported_os](unsupported-os-class.md) брошен, если операционная система не поддерживается Concurrency Runtime.

## <a name="getprocessornodecount"></a><a name="getprocessornodecount"></a>GetProcessorNodeCount

Возвращает число узлов NUMA или пакетов процессора в базовой системе.

```cpp
unsigned int __cdecl GetProcessorNodeCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество узлов NUMA или пакетов процессоров.

### <a name="remarks"></a>Remarks

Если система содержит больше узлов NUMA, чем пакеты процессоров, количество узлов NUMA возвращается, в противном случае количество пакетов процессоров возвращается.

[unsupported_os](unsupported-os-class.md) брошен, если операционная система не поддерживается Concurrency Runtime.

## <a name="getschedulerid"></a><a name="getschedulerid"></a>GetSchedulerId

Возвращает уникальный идентификатор, который можно назначить планировщику, реализующему интерфейс `IScheduler`.

```cpp
unsigned int __cdecl GetSchedulerId();
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор для планировщика.

### <a name="remarks"></a>Remarks

Используйте этот метод для получения идентификатора для планировщика перед тем, как передать `IScheduler` интерфейс в качестве параметра любому из методов, предлагаемых менеджером ресурсов.

## <a name="internal_assign_iterators"></a><a name="internal_assign_iterators"></a>internal_assign_iterators

```cpp
template<typename T, class _Ax>
template<class _I>
void concurrent_vector<T, _Ax>::internal_assign_iterators(
   _I first,
   _I last);
```

### <a name="parameters"></a>Параметры

*T*<br/>

*_Ax*<br/>

*_i*<br/>

*Первый*<br/>

*Последний*<br/>

## <a name="interruption_point"></a><a name="interruption_point"></a>interruption_point

Создает точку прерывания для отмены. Если отмена выполняется в контексте, где вызывается эта функция, это создает внутреннее исключение, которое прерывает текущую выполняемую параллельную работу. Если отмена не выполняется, функция ничего не делает.

```cpp
inline void interruption_point();
```

### <a name="remarks"></a>Remarks

Не следует перехватывать внутреннее исключение отмены, создаваемое функцией `interruption_point()`. Исключение будет перехвачено и обработано средой выполнения, и его перехват может вызвать непредсказуемое поведение программы.

## <a name="is_current_task_group_canceling"></a><a name="is_current_task_group_canceling"></a>is_current_task_group_canceling

Возвращает значение, указывающее, находится ли группа задач, которая в данный момент выполняется в текущем контексте во встроенном режиме, в процессе активной отмены (или вскоре перейдет в это состояние). Обратите внимание, что в отсутствие групп задач, выполняющихся в текущем контексте во встроенном режиме, будет возвращено значение `false`.

```cpp
bool __cdecl is_current_task_group_canceling();
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если задача группы, которая в настоящее время выполнения отменяет, **ложно** в противном случае.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации [см.](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)

## <a name="make_choice"></a><a name="make_choice"></a>make_choice

Конструирует блок сообщений `choice` из необязательного объекта `Scheduler` или `ScheduleGroup` и двух или более источников входных данных.

```cpp
template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    Scheduler& _PScheduler,
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    ScheduleGroup& _PScheduleGroup,
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);
```

### <a name="parameters"></a>Параметры

*T1*<br/>
Тип блока сообщения первого источника.

*T2*<br/>
Тип блокировки сообщения второго источника.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `choice` .

*_Item1*<br/>
Первый источник.

*_Item2*<br/>
Второй источник.

*_Items*<br/>
Дополнительные источники.

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `choice` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="return-value"></a>Возвращаемое значение

Блок сообщений `choice` с двумя или более источниками входных данных.

## <a name="make_greedy_join"></a><a name="make_greedy_join"></a>make_greedy_join

Конструирует блок сообщений `greedy multitype_join` из необязательного объекта `Scheduler` или `ScheduleGroup` и двух или более источников входных данных.

```cpp
template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>,greedy> make_greedy_join(
    Scheduler& _PScheduler,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>, greedy> make_greedy_join(
    ScheduleGroup& _PScheduleGroup,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>, greedy> make_greedy_join(
    T1 _Item1,
    T2 _Items,
    Ts... _Items);
```

### <a name="parameters"></a>Параметры

*T1*<br/>
Тип блока сообщения первого источника.

*T2*<br/>
Тип блокировки сообщения второго источника.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` .

*_Item1*<br/>
Первый источник.

*_Item2*<br/>
Второй источник.

*_Items*<br/>
Дополнительные источники.

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="return-value"></a>Возвращаемое значение

Блок сообщений `greedy multitype_join` с двумя или более источниками входных данных.

## <a name="make_join"></a><a name="make_join"></a>make_join

Конструирует блок сообщений `non_greedy multitype_join` из необязательного объекта `Scheduler` или `ScheduleGroup` и двух или более источников входных данных.

```cpp
template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>>
    make_join(
Scheduler& _PScheduler,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> make_join(
ScheduleGroup& _PScheduleGroup,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> make_join(
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);
```

### <a name="parameters"></a>Параметры

*T1*<br/>
Тип блока сообщения первого источника.

*T2*<br/>
Тип блокировки сообщения второго источника.

*_PScheduler*<br/>
Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` .

*_Item1*<br/>
Первый источник.

*_Item2*<br/>
Второй источник.

*_Items*<br/>
Дополнительные источники.

*_PScheduleGroup*<br/>
Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` . Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="return-value"></a>Возвращаемое значение

Блок сообщений `non_greedy multitype_join` с двумя или более источниками входных данных.

## <a name="make_task"></a><a name="make_task"></a>make_task

Метод фабрики для создания объекта `task_handle`.

```cpp
template <class _Function>
task_handle<_Function> make_task(const _Function& _Func);
```

### <a name="parameters"></a>Параметры

*_Function*<br/>
Тип объекта функции, который будет вызываться для выполнения `task_handle` работы, представленной объектом.

*_func*<br/>
Функция, которая будет использоваться для выполнения работы, представленной объектом. `task_handle` Это может быть фанктор lambda, указатель на функцию, или любой объект, который `void operator()()`поддерживает версию оператора вызова функции с подписью.

### <a name="return-value"></a>Возвращаемое значение

Объект `task_handle` .

### <a name="remarks"></a>Remarks

Эта функция полезна, когда `task_handle` вам нужно создать объект с выражением лямбда, потому что это позволяет создавать объект, не зная истинного типа фанктора lambda.

## <a name="parallel_buffered_sort"></a><a name="parallel_buffered_sort"></a>parallel_buffered_sort

Упорядочив элементы в определенном диапазоне в не-нисходящий порядок, или в соответствии с критерием заказа, указанным двоичным предикатом, параллельно. Эта функция семантически аналогична `std::sort` в том, что она является нестабильной сортировкой на месте на основе сравнения, за исключением того, что ей требуется `O(n)` дополнительного пространства и инициализация по умолчанию для сортируемых элементов.

```cpp
template<typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator,
    typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator,
    typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);
```

### <a name="parameters"></a>Параметры

*_Random_iterator*<br/>
Тип итератора входного диапазона.

*_allocator*<br/>
Тип стандартного разлестьа памяти, совместимый со стандартной библиотекой СЗ.

*_Function*<br/>
Тип двоичного компаратора.

*_begin*<br/>
Итератор произвольного доступа, обращающийся к позиции первого элемента в сортируемом диапазоне.

*_end*<br/>
Итератор произвольного доступа, обращающийся к позиции после последнего элемента в сортируемом диапазоне.

*_Alloc*<br/>
Экземпляр стандартного разлестьа памяти со стандартной библиотеки СЗ.

*_func*<br/>
Определяемый пользователем объект функции предиката, который определяет критерии сравнения, которые должны соблюдаться идущими подряд элементами при упорядочении. Двоичный предикат принимает два аргумента и возвращает **true** , если условие удовлетворено, или **false** , если условие не удовлетворено. Эта функция средства сравнения должна задать строгое слабое упорядочение пар элементов последовательности.

*_Chunk_size*<br/>
Минимальный размер блока, который будет разбит на два для параллельного выполнения.

### <a name="remarks"></a>Remarks

Все перегрузки требуют `n * sizeof(T)` `n` дополнительного пространства, где количество элементов, которые должны быть отсортированы, и `T` тип элемента. В большинстве случаев parallel_buffered_sort покажет улучшение производительности по сравнению с [parallel_sort,](concurrency-namespace-functions.md)и вы должны использовать его в течение parallel_sort если у вас есть память доступна.

Если вы не поставляете двоичный компаратор `std::less` используется в качестве по умолчанию, который требует типа элемента, чтобы обеспечить оператора. `operator<()`

Если вы не поставляете тип или экземпляр выделения, для выделения `std::allocator<T>` буфера используется распределителька стандартной библиотеки C'S Standard Library.

Алгоритм делит входной диапазон на два блока и последовательно делит каждый блок на два подблока для параллельного выполнения. Дополнительный `_Chunk_size` аргумент может быть использован для указания алгоритму, что `_Chunk_size` он должен обрабатывать куски размера < последовательно.

## <a name="parallel_for"></a><a name="parallel_for"></a>Parallel_for

`parallel_for` выполняет итерацию по диапазону индексов и выполняет предоставленную пользователем функцию в каждой итерации параллельно.

```cpp
template <typename _Index_type, typename _Function, typename _Partitioner>
void parallel_for(
    _Index_type first,
    _Index_type last,
    _Index_type _Step,
    const _Function& _Func,
    _Partitioner&& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    _Index_type _Step,
    const _Function& _Func);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const auto_partitioner& _Part = auto_partitioner());

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const static_partitioner& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const simple_partitioner& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    affinity_partitioner& _Part);
```

### <a name="parameters"></a>Параметры

*_Index_type*<br/>
Тип индекса, используемого для итерации.

*_Function*<br/>
Тип функции, которая будет выполняться при каждой итерации.

*_Partitioner*<br/>
Тип перегородки, который используется для раздела поставляемого диапазона.

*Первый*<br/>
Первый индекс, который будет включен в итерацию.

*Последний*<br/>
Индекс один мимо последнего индекса, который будет включен в итерацию.

*_Step*<br/>
Значение, с помощью которого `first` шаг `last`при итерации от . Шаг должен быть положительным. [invalid_argument](../../../standard-library/invalid-argument-class.md) брошен, если шаг меньше 1.

*_func*<br/>
Функция, которая должна быть выполнена при каждой итерации. Это может быть выражение lambda, указатель функции или любой объект, поддерживающий версию оператора вызова функции с подписью. `void operator()(_Index_type)`

*_Part*<br/>
Ссылка на объект-разделитель. Аргумент может быть `const`одним `const`из `const` [auto_partitioner,](auto-partitioner-class.md)`&` [static_partitioner,](static-partitioner-class.md)`&` [simple_partitioner](simple-partitioner-class.md) `&` или [affinity_partitioner](affinity-partitioner-class.md) `&` Если используется [affinity_partitioner](affinity-partitioner-class.md) объект, ссылка должна быть неконсеной ссылкой l-значения, так что алгоритм может хранить состояние для будущих циклов для повторного использования.

### <a name="remarks"></a>Remarks

Для получения дополнительной [информации см.](../../../parallel/concrt/parallel-algorithms.md)

## <a name="parallel_for_each"></a><a name="parallel_for_each"></a>Parallel_for_each

`parallel_for_each` применяет указанную функцию к каждому элементу в диапазоне параллельно. Эта функция семантически эквивалентна функции `for_each` в пространстве имен `std`, за исключением того, что итерация по элементам выполняется параллельно и порядок итерации не определен. Аргумент `_Func` должен поддерживать оператор вызова функции формы `operator()(T)`, где параметр `T` является типом элемента контейнера, для которого выполняется итерация.

```cpp
template <typename _Iterator, typename _Function>
void parallel_for_each(
    _Iterator first,
    _Iterator last,
    const _Function& _Func);

template <typename _Iterator, typename _Function, typename _Partitioner>
void parallel_for_each(
    _Iterator first,
    _Iterator last,
    const _Function& _Func,
    _Partitioner&& _Part);
```

### <a name="parameters"></a>Параметры

*_Iterator*<br/>
Тип итератора используется для итерата над контейнером.

*_Function*<br/>
Тип функции, которая будет применяться к каждому элементу в диапазоне.

*_Partitioner*<br/>
*Первый*<br/>
Итератор, обращающийся к положению первого элемента, который будет включен в параллельную итерацию.

*Последний*<br/>
Итератор, обращающийся к позиции, мимо финального элемента, который будет включен в параллельную итерацию.

*_func*<br/>
Объект функции, определяемый пользователем, который применяется к каждому элементу в диапазоне.

*_Part*<br/>
Ссылка на объект-разделитель. Аргумент может быть `const`одним `const`из `const` [auto_partitioner,](auto-partitioner-class.md)`&` [static_partitioner,](static-partitioner-class.md)`&` [simple_partitioner](simple-partitioner-class.md) `&` или [affinity_partitioner](affinity-partitioner-class.md) `&` Если используется [affinity_partitioner](affinity-partitioner-class.md) объект, ссылка должна быть неконсеной ссылкой l-значения, так что алгоритм может хранить состояние для будущих циклов для повторного использования.

### <a name="remarks"></a>Remarks

[auto_partitioner](auto-partitioner-class.md) будет использоваться для перегрузки без явного разделителя.

Для итераторов, которые не поддерживают случайный доступ, поддерживается только [auto_partitioner.](auto-partitioner-class.md)

Для получения дополнительной [информации см.](../../../parallel/concrt/parallel-algorithms.md)

## <a name="parallel_invoke"></a><a name="parallel_invoke"></a>parallel_invoke

Выполняет объекты функции, предоставленные в виде параметров, в параллельном режиме и блокирует их до завершения выполнения. Каждый объект функции может быть лямбда-выражением, указателем на функцию или любым объектом, который поддерживает оператор вызова функции с подписью `void operator()()`.

```cpp
template <typename _Function1, typename _Function2>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2);

template <typename _Function1, typename _Function2, typename _Function3>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8,
    typename _Function9>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8,
    const _Function9& _Func9);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8,
    typename _Function9,
    typename _Function10>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8,
    const _Function9& _Func9,
    const _Function10& _Func10);
```

### <a name="parameters"></a>Параметры

*_Function1*<br/>
Тип первого функционального объекта, который будет выполняться параллельно.

*_Function2*<br/>
Тип второго объекта функции, который будет выполняться параллельно.

*_Function3*<br/>
Тип третьего объекта функции, который будет выполняться параллельно.

*_Function4*<br/>
Тип четвертого объекта функции, который будет выполняться параллельно.

*_Function5*<br/>
Тип пятого объекта функции, который будет выполняться параллельно.

*_Function6*<br/>
Тип шестого объекта функции, который будет выполняться параллельно.

*_Function7*<br/>
Тип седьмого объекта функции, который будет выполняться параллельно.

*_Function8*<br/>
Тип восьмого объекта функции, который будет выполняться параллельно.

*_Function9*<br/>
Тип девятого объекта функции, который будет выполняться параллельно.

*_Function10*<br/>
Тип десятого объекта функции, который будет выполняться параллельно.

*_Func1*<br/>
Первый объект функции, который будет выполняться параллельно.

*_Func2*<br/>
Второй объект функции, который будет выполняться параллельно.

*_Func3*<br/>
Третий объект функции, который будет выполняться параллельно.

*_Func4*<br/>
Четвертый объект функции, который будет выполняться параллельно.

*_Func5*<br/>
Пятый объект функции, который будет выполняться параллельно.

*_Func6*<br/>
Шестой объект функции, который будет выполняться параллельно.

*_Func7*<br/>
Седьмой объект функции, который будет выполняться параллельно.

*_Func8*<br/>
Восьмой объект функции, который будет выполняться параллельно.

*_Func9*<br/>
Девятый объект функции, который будет выполняться параллельно.

*_Func10*<br/>
Десятый объект функции, который будет выполняться параллельно.

### <a name="remarks"></a>Remarks

Обратите внимание, что один или несколько объектов функции, поставляемые в качестве параметров, могут выполнять сяплайн в контексте вызова.

Если один или несколько объектов функции, передаваемые по параметрам для этой функции, выкидывают `parallel_invoke`исключение, время выполнения выберет одно такое исключение по своему выбору и распространит его из вызова.

Для получения дополнительной [информации см.](../../../parallel/concrt/parallel-algorithms.md)

## <a name="parallel_radixsort"></a><a name="parallel_radixsort"></a>parallel_radixsort

Располагает элементы в указанном диапазоне в неубывающем порядке, используя алгоритм сортировки основания системы счисления. Это стабильная функция сортировки, для которой требуется функция проекции, способная проецировать сортируемые элементы в неподписанные ключи целочисленного типа. Для сортируемых элементов требуется инициализация по умолчанию.

```cpp
template<typename _Random_iterator>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator, typename _Random_iterator>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator, typename _Random_iterator>
inline void parallel_radixsort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator, typename _Function>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);

template<typename _Allocator, typename _Random_iterator,
    typename _Function>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_radixsort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);
```

### <a name="parameters"></a>Параметры

*_Random_iterator*<br/>
Тип итератора входного диапазона.

*_allocator*<br/>
Тип стандартного разлестьа памяти, совместимый со стандартной библиотекой СЗ.

*_Function*<br/>
Тип функции проекции.

*_begin*<br/>
Итератор произвольного доступа, обращающийся к позиции первого элемента в сортируемом диапазоне.

*_end*<br/>
Итератор произвольного доступа, обращающийся к позиции после последнего элемента в сортируемом диапазоне.

*_Alloc*<br/>
Экземпляр стандартного разлестьа памяти со стандартной библиотеки СЗ.

*_Proj_func*<br/>
Объект функции проекции, определяемый пользователем, который преобразует элемент в интегральное значение.

*_Chunk_size*<br/>
Минимальный размер блока, который будет разбит на два для параллельного выполнения.

### <a name="remarks"></a>Remarks

Все перегрузки требуют `n * sizeof(T)` `n` дополнительного пространства, где количество элементов, которые должны быть отсортированы, и `T` тип элемента. Неанормарная проекционная `I _Proj_func(T)` фанктор с подписью требуется `T` для возврата ключа `I` при предъявлении элемента, где находится тип элемента и является неподписанным типом, похожим на ряды.

Если вы не поставляете функцию проекции, функция проекции по умолчанию, которая просто возвращает элемент используется для интегральных типов. Функция не сможет компилироваться, если элемент не является интегральным типом при отсутствии функции проекции.

Если вы не поставляете тип или экземпляр выделения, для выделения `std::allocator<T>` буфера используется распределителька стандартной библиотеки C'S Standard Library.

Алгоритм делит входной диапазон на два блока и последовательно делит каждый блок на два подблока для параллельного выполнения. Дополнительный `_Chunk_size` аргумент может быть использован для указания алгоритму, что `_Chunk_size` он должен обрабатывать куски размера < последовательно.

## <a name="parallel_reduce"></a><a name="parallel_reduce"></a>Parallel_reduce

Параллельно вычисляет сумму всех элементов в указанном диапазоне путем вычисления последовательных частичных сумм или вычисляет результаты последовательных частичных сумм, полученных сходным образом с использованием указанной бинарной операции, отличной от суммирования. `parallel_reduce` семантически аналогичен `std::accumulate`, но требует, чтобы бинарная операция была ассоциативна, а также значение идентификатора вместо начального значения.

```cpp
template<typename _Forward_iterator>
inline typename std::iterator_traits<_Forward_iterator>::value_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const typename std::iterator_traits<_Forward_iterator>::value_type& _Identity);

template<typename _Forward_iterator, typename _Sym_reduce_fun>
inline typename std::iterator_traits<_Forward_iterator>::value_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const typename std::iterator_traits<_Forward_iterator>::value_type& _Identity,
    _Sym_reduce_fun _Sym_fun);

template<typename _Reduce_type,
    typename _Forward_iterator,
    typename _Range_reduce_fun,
    typename _Sym_reduce_fun>
inline _Reduce_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const _Reduce_type& _Identity,
    const _Range_reduce_fun& _Range_fun,
    const _Sym_reduce_fun& _Sym_fun);
```

### <a name="parameters"></a>Параметры

*_Forward_iterator*<br/>
Тип итератора диапазона ввода.

*_Sym_reduce_fun*<br/>
Тип функции симметричной редукции. Это должен быть тип функции с сигнатурой `_Reduce_type _Sym_fun(_Reduce_type, _Reduce_type)`, где _Reduce_type совпадает с типом идентификатора и типом результата редукции. В третьей перегрузке он должен быть совместим с типом вывода `_Range_reduce_fun`.

*_Reduce_type*<br/>
Тип, до которого будет редуцирован ввод, который может отличаться от типа входного элемента. Возвращаемое значение и значение идентификатора будут иметь этот тип.

*_Range_reduce_fun*<br/>
Тип функции редукции диапазона. Это должен быть тип функции с сигнатурой `_Reduce_type _Range_fun(_Forward_iterator, _Forward_iterator, _Reduce_type)`, _Reduce_type совпадает с типом идентификатора и типом результата редукции.

*_begin*<br/>
Итератор ввода, указывающий на первый элемент в диапазоне для редукции.

*_end*<br/>
Итератор ввода, указывающий на позицию после последнего элемента в диапазоне для редукции.

*_Identity*<br/>
Значение идентификатора `_Identity` относится к тому же типу, что и результат редукции, а также совпадает с `value_type` итератора для первой и второй перегрузок. В третьей перегрузке значение идентификатора должно иметь тот же тип, что и результат редукции, но может отличаться от `value_type` итератора. Оно должно иметь такое соответствующее значение, чтобы оператор редукции диапазона `_Range_fun`, примененный к диапазону из единственного элемента типа `value_type` и значению идентификатора, вел себя подобно приведению типа этого значения из типа `value_type` в тип идентификатора.

*_Sym_fun*<br/>
Симметричная функция, которая будет использоваться на второй стадии редукции. Дополнительные сведения см. в примечаниях.

*_Range_fun*<br/>
Симметричная функция, которая будет использоваться на первой стадии редукции. Дополнительные сведения см. в примечаниях.

### <a name="return-value"></a>Возвращаемое значение

Результат редукции.

### <a name="remarks"></a>Remarks

Для выполнения параллельной редукции функция делит диапазон на блоки на основе количества работников, доступных базовому планировщику. Редукция происходит в две стадии, на первой стадии выполняется редукция в каждом блоке, на второй стадии выполняется редукция частичных результатов из каждого блока.

Первая перегрузка требует, чтобы типы итератора `value_type` и `T` были такими же, как и тип значения идентификатора и тип результата редукции. Тип элемента T должен предоставить оператор `T T::operator + (T)`, чтобы выполнить редукцию элементов в каждом блоке. Тот же оператор используется на второй стадии.

Вторая перегрузка также требует, чтобы тип итератора `value_type` был таким же, как и тип значения идентификатора и тип результата редукции. Предоставленный бинарный оператор `_Sym_fun` используется на обеих стадиях редукции со значением идентификатора в качестве начального значения для первой стадии.

В третьей перегрузке тип значения идентификатора должен совпадать с типом результата редукции, но `value_type` итератора может отличаться от них. Функция редукции диапазона `_Range_fun` используется на первой стадии со значением идентификатора в качестве начального значения, а бинарная функция `_Sym_reduce_fun` применяется к промежуточным результатам на второй стадии.

## <a name="parallel_sort"></a><a name="parallel_sort"></a>parallel_sort

Упорядочив элементы в определенном диапазоне в не-нисходящий порядок, или в соответствии с критерием заказа, указанным двоичным предикатом, параллельно. Эта функция семантически схожа с `std::sort`, так как она основана на сравнении, неустойчива, сортирует на месте.

```cpp
template<typename _Random_iterator>
inline void parallel_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator,typename _Function>
inline void parallel_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);
```

### <a name="parameters"></a>Параметры

*_Random_iterator*<br/>
Тип итератора входного диапазона.

*_Function*<br/>
Тип бинарного функтора сравнения.

*_begin*<br/>
Итератор произвольного доступа, обращающийся к позиции первого элемента в сортируемом диапазоне.

*_end*<br/>
Итератор произвольного доступа, обращающийся к позиции после последнего элемента в сортируемом диапазоне.

*_func*<br/>
Определяемый пользователем объект функции предиката, который определяет критерии сравнения, которые должны соблюдаться идущими подряд элементами при упорядочении. Двоичный предикат принимает два аргумента и возвращает **true** , если условие удовлетворено, или **false** , если условие не удовлетворено. Эта функция средства сравнения должна задать строгое слабое упорядочение пар элементов последовательности.

*_Chunk_size*<br/>
Минимальный размер куска, который будет разделен на две части для параллельного выполнения.

### <a name="remarks"></a>Remarks

Первая перегрузка использует двоичный компаратор. `std::less`

Вторая перегрузка использует предоставленное бинарное средство сравнения, которое должно иметь сигнатуру `bool _Func(T, T)`, где `T` — тип элементов во входном диапазоне.

Алгоритм делит входной диапазон на два блока и последовательно делит каждый блок на два подблока для параллельного выполнения. Дополнительный `_Chunk_size` аргумент может быть использован для указания алгоритму, что `_Chunk_size` он должен обрабатывать куски размера < последовательно.

## <a name="parallel_transform"></a><a name="parallel_transform"></a>parallel_transform

Применяет заданный объект функции к каждому элементу в исходном диапазоне или к паре элементов из двух исходных диапазонов и параллельно копирует возвращаемые значения объекта функции в диапазон назначения. Эта функция семантически эквивалентна `std::transform`.

```cpp
template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const auto_partitioner& _Part = auto_partitioner());

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const static_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const simple_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    affinity_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Input_iterator2,
    typename _Output_iterator,
    typename _Binary_operator,
    typename _Partitioner>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Input_iterator2
first2,
    _Output_iterator _Result,
    const _Binary_operator& _Binary_op,
    _Partitioner&& _Part);

template <typename _Input_iterator1,
    typename _Input_iterator2,
    typename _Output_iterator,
    typename _Binary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Input_iterator2
first2,
    _Output_iterator _Result,
    const _Binary_operator& _Binary_op);
```

### <a name="parameters"></a>Параметры

*_Input_iterator1*<br/>
Тип первого или единственного итератора ввода.

*_Output_iterator*<br/>
Тип итератора вывода.

*_Unary_operator*<br/>
Тип унарного функтора, который должен выполняться для каждого элемента во входном диапазоне.

*_Input_iterator2*<br/>
Тип второго итератора ввода.

*_Binary_operator*<br/>
Тип бинарного функтора, выполняемого попарно на элементах из двух исходных диапазонов.

*_Partitioner*<br/>
*first1*<br/>
Итератор ввода указывает на позицию первого элемента в первом или единственном исходном обрабатываемом диапазоне.

*last1*<br/>
Итератор ввода указывает на позицию, следующую за последним элементом в первом или единственном исходном обрабатываемом диапазоне.

*_Result*<br/>
Итератор вывода указывает на позицию первого элемента в диапазоне назначения.

*_Unary_op*<br/>
Определенный пользователем объект унарной функции, который применяется к каждому элементу в исходном диапазоне.

*_Part*<br/>
Ссылка на объект-разделитель. Аргумент может быть `const`одним `const`из `const` [auto_partitioner,](auto-partitioner-class.md)`&` [static_partitioner,](static-partitioner-class.md)`&` [simple_partitioner](simple-partitioner-class.md) `&` или [affinity_partitioner](affinity-partitioner-class.md) `&` Если используется [affinity_partitioner](affinity-partitioner-class.md) объект, ссылка должна быть неконсеной ссылкой l-значения, так что алгоритм может хранить состояние для будущих циклов для повторного использования.

*first2*<br/>
Итератор ввода указывает на позицию первого элемента во втором исходном обрабатываемом диапазоне.

*_Binary_op*<br/>
Определяемый пользователем объект бинарной функции, который последовательно применяется к парам элементов из двух исходных диапазонов.

### <a name="return-value"></a>Возвращаемое значение

Итератор вывода указывает на позицию после последнего элемента в диапазоне назначения, который получает выходные элементы, преобразованные объектом функции.

### <a name="remarks"></a>Remarks

[auto_partitioner](auto-partitioner-class.md) будет использоваться для перегрузок без явного аргумента разделителя.

Для итераторов, которые не поддерживают случайный доступ, поддерживается только [auto_partitioner.](auto-partitioner-class.md)

Перегрузки, принимающие аргумент `_Unary_op`, преобразовывают диапазон ввода в диапазон вывода путем применения унарного функтора к каждому элементу в диапазоне ввода. `_Unary_op` должен поддерживать оператор вызова функции с сигнатурой `operator()(T)`, где `T` является типом значения диапазона, в котором выполняются итерации.

Перегрузки, принимающие аргумент `_Binary_op`, преобразовывают два диапазона ввода в диапазон вывода путем применения бинарного функтора к одному элементу из первого диапазона ввода и к одному элементу из второго диапазона ввода. `_Binary_op` должен поддерживать оператор вызова функции с сигнатурой `operator()(T, U)`, где `T`, `U` являются типами значений двух входных итераторов.

Для получения дополнительной [информации см.](../../../parallel/concrt/parallel-algorithms.md)

## <a name="receive"></a><a name="receive"></a>Получить

Общая реализация получения, позволяющая контексту ожидать данные строго из одного источника и фильтровать значения, которые принимаются.

```cpp
template <class T>
T receive(
    _Inout_ ISource<T>* _Src,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    _Inout_ ISource<T>* _Src,
    typename ITarget<T>::filter_method const& _Filter_proc,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    ISource<T>& _Src,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    ISource<T>& _Src,
    typename ITarget<T>::filter_method const& _Filter_proc,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезной нагрузки.

*_Src*<br/>
Указатель или ссылка на источник, из которого ожидаются данные.

*_Timeout*<br/>
Максимальное время, за которое метод должен быть для данных, в миллисекундах.

*_Filter_proc*<br/>
Функция фильтра, определяющая, следует ли принимать сообщения.

### <a name="return-value"></a>Возвращаемое значение

Значение от источника, типа полезной нагрузки.

### <a name="remarks"></a>Remarks

Если параметр `_Timeout` имеет значение, `COOPERATIVE_TIMEOUT_INFINITE`не предусмотренное постоянным, [то](operation-timed-out-class.md) operation_timed_out исключения брошен, если указанный промежуток времени истекает до получения сообщения. Если вы хотите нулевой тайм-аут длины, вы должны `receive` использовать [функцию try_receive,](concurrency-namespace-functions.md) в отличие от вызова с тайм-аутом `0` (ноль), так как это более эффективно и не бросает исключения на тайм-ауты.

Для получения дополнительной [Message Passing Functions](../../../parallel/concrt/message-passing-functions.md)информации см.

## <a name="run_with_cancellation_token"></a><a name="run_with_cancellation_token"></a>run_with_cancellation_token

Немедленно и синхронно выполняет объект функции в контексте заданного токена отмены.

```cpp
template<typename _Function>
void run_with_cancellation_token(
    const _Function& _Func,
    cancellation_token _Ct);
```

### <a name="parameters"></a>Параметры

*_Function*<br/>
Тип объекта функции, который будет вызываться.

*_func*<br/>
Объект функции, который будет выполняться. Этот объект должен поддерживать оператор вызова функции с сигнатурой (void).

*_Ct*<br/>
Токен отмены, который будет управлять неявной отменой объекта функции. Если требуется выполнение функции без возможности неявной отмены из-за отмены родительской группы задач, следует использовать `cancellation_token::none()`.

### <a name="remarks"></a>Remarks

При отмене `cancellation_token` будут активированы все точки прерывания в объекте функции. Явный токен `_Ct` будет изолировать объект `_Func` от родительской отмены, если родитель имеет другой токен или вообще не имеет токена.

## <a name="send"></a><a name="send"></a>Отправить

Синхронная операции отправки, которая ожидает принятия или отклонения сообщения целевым объектом.

```cpp
template <class T>
bool send(_Inout_ ITarget<T>* _Trg, const T& _Data);

template <class T>
bool send(ITarget<T>& _Trg, const T& _Data);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезной нагрузки.

*_Trg*<br/>
Указатель или ссылка на цель, к которой отправляются данные.

*_Data*<br/>
Ссылка на данные, которые будут отправлены.

### <a name="return-value"></a>Возвращаемое значение

**правда,** если сообщение было принято, **ложное** в противном случае.

### <a name="remarks"></a>Remarks

Для получения дополнительной [Message Passing Functions](../../../parallel/concrt/message-passing-functions.md)информации см.

## <a name="set_ambient_scheduler"></a><a name="set_ambient_scheduler"></a>set_ambient_scheduler

```cpp
inline void set_ambient_scheduler(std::shared_ptr<::Concurrency::scheduler_interface> _Scheduler);
```

### <a name="parameters"></a>Параметры

*_Scheduler*<br/>
Окружающий планировщик для установки.

## <a name="set_task_execution_resources"></a><a name="set_task_execution_resources"></a>set_task_execution_resources

Ограничивает ресурсы выполнения, используемые внутренними рабочими потоками среды выполнения с параллелизмом, определенным набором сходства.

Этот метод можно вызывать только до создания диспетчера ресурсов или между двумя периодами существования диспетчера ресурсов. Его можно вызывать несколько раз при условии, что в момент вызова диспетчер ресурсов не существует. После задания ограничения сходства оно будет оставаться действительным до следующего допустимого вызова метода `set_task_execution_resources`.

Предоставленная маска сходства не обязана быть подмножеством маски сходства процесса. Сходство процесса обновляется при необходимости.

```cpp
void __cdecl set_task_execution_resources(
    DWORD_PTR _ProcessAffinityMask);

void __cdecl set_task_execution_resources(
    unsigned short count,
    PGROUP_AFFINITY _PGroupAffinity);
```

### <a name="parameters"></a>Параметры

*_ProcessAffinityMask*<br/>
Маска сходства, которой должны быть ограничены рабочие потоки среды выполнения с параллелизмом. Используйте этот метод в системе с более чем 64 аппаратными потоками, только если требуется ограничить среду выполнения с параллелизмом подмножеством текущей группы процессоров. Как правило, следует использовать версию метода, которая принимает массив сходств группы в качестве параметра, чтобы ограничить сходство на компьютерах с более чем 64 аппаратными потоками.

*count*<br/>
Количество записей `GROUP_AFFINITY` в массиве, заданном параметром `_PGroupAffinity`.

*_PGroupAffinity*<br/>
Массив записей `GROUP_AFFINITY`.

### <a name="remarks"></a>Remarks

Метод будет invalid_operation [исключение,](invalid-operation-class.md) если менеджер ресурсов присутствует в момент его вызова, и [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если указанное сродство приводит к пустому набору ресурсов.

Версию метода, принимающую массив сходств группы в качестве параметра, следует использовать только в операционных системах Windows версии 7 и выше. В противном случае invalid_operation [исключение.](invalid-operation-class.md)

Программное изменение сродства процесса после вызова этого метода не приведет к тому, что менеджер ресурсов переоценит сродство, к которой он ограничен. Таким образом, все изменения сходства процесса необходимо сделать до вызова этого метода.

## <a name="swap"></a><a name="swap"></a>Своп

Меняет местами элементы двух объектов `concurrent_vector`.

```cpp
template<typename T, class _Ax>
inline void swap(
    concurrent_vector<T, _Ax>& _A,
    concurrent_vector<T, _Ax>& _B);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных элементов, хранящихся в параллельных векторах.

*_Ax*<br/>
Тип разлесть амплокатора одновременных векторов.

*_a*<br/>
Параллельный вектор, элементы которого должны быть обменяны с элементами одновременного вектора. `_B`

*_B*<br/>
Параллельный вектор, обеспечивающий обмен элементов, или вектор, элементы которого `_A`должны быть обменены с элементами одновременного вектора.

### <a name="remarks"></a>Remarks

Функция шаблона — это алгоритм, `concurrent_vector` специализирующийся `_A`на классе контейнеров для выполнения функции элемента. [concurrent_vector::swap](concurrent-vector-class.md#swap) `_B`( ). Это экземпляры частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, `template <class T> void swap(T&, T&)`в классе алгоритма работает по назначению и является медленной операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

Этот метод не является валютным. При вызове этого метода необходимо убедиться, что никакие другие потоки не выполняют операций на одном из одновременных векторов.

## <a name="task_from_exception"></a><a name="task_from_exception"></a>task_from_exception

```cpp
template<typename _TaskType, typename _ExType>
task<_TaskType> task_from_exception(
    _ExType _Exception,
    const task_options& _TaskOptions = task_options());
```

### <a name="parameters"></a>Параметры

*_TaskType*<br/>

*_ExType*<br/>

*_Exception*<br/>

*_TaskOptions*<br/>

### <a name="return-value"></a>Возвращаемое значение

## <a name="task_from_result"></a><a name="task_from_result"></a>task_from_result

```cpp
template<typename T>
task<T> task_from_result(
    T _Param,
    const task_options& _TaskOptions = task_options());

inline task<bool> task_from_result(ool _Param);

inline task<void> task_from_result(
    const task_options& _TaskOptions = task_options());
```

### <a name="parameters"></a>Параметры

*T*<br/>

*_Param*<br/>

*_TaskOptions*<br/>

### <a name="return-value"></a>Возвращаемое значение

## <a name="trace_agents_register_name"></a><a name="trace_agents_register_name"></a>Trace_agents_register_name

Связывает данное имя с блоком сообщений или агентом в трассировки событий Windows.

```cpp
template <class T>
void Trace_agents_register_name(
    _Inout_ T* _PObject,
    _In_z_ const wchar_t* _Name);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта. Обычно это блок сообщений или агент.

*_PObject*<br/>
Указатель на блок сообщений или агент, который именован в трассировке.

*_Name*<br/>
Имя для заданного объекта.

## <a name="try_receive"></a><a name="try_receive"></a>try_receive

Общая реализация проверки-получения, позволяющая контексту выполнять поиск данных строго из одного источника и фильтровать значения, которые принимаются. Если данные не готовы, метод возвращается **ложным.**

```cpp
template <class T>
bool try_receive(_Inout_ ISource<T>* _Src, T& _value);

template <class T>
bool try_receive(
    _Inout_ ISource<T>* _Src,
    T& _value,
    typename ITarget<T>::filter_method const& _Filter_proc);

template <class T>
bool try_receive(ISource<T>& _Src, T& _value);

template <class T>
bool try_receive(
    ISource<T>& _Src,
    T& _value,
    typename ITarget<T>::filter_method const& _Filter_proc);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип полезной нагрузки

*_Src*<br/>
Указатель или ссылка на источник, из которого ожидаются данные.

*_value*<br/>
Ссылка на место, где будет размещен результат.

*_Filter_proc*<br/>
Функция фильтра, определяющая, следует ли принимать сообщения.

### <a name="return-value"></a>Возвращаемое значение

Значение, `bool` указывающее, была ли `_value`размещена полезная нагрузка в.

### <a name="remarks"></a>Remarks

Для получения дополнительной [Message Passing Functions](../../../parallel/concrt/message-passing-functions.md)информации см.

## <a name="wait"></a><a name="wait"></a>Подожди

Приостанавливает текущий контекст на указанный период времени.

```cpp
void __cdecl wait(unsigned int _Milliseconds);
```

### <a name="parameters"></a>Параметры

*_Milliseconds*<br/>
Число миллисекунд, на которое должен быть приостановлен текущий контекст. Если параметру `_Milliseconds` задано значение `0`, текущий контекст должен уступить выполнение другим работоспособным контекстам перед продолжением.

### <a name="remarks"></a>Remarks

Если этот метод вызывается в контексте планировщика затрат на время входиный курс, планировщик найдет другой контекст для запуска на базовом ресурсе. Поскольку планировщик предназначен для совместной работы по своей природе, этот контекст не может возобновиться точно после указанного числа миллисекунд. Если планировщик занят выполнением других задач, которые не уступают планировщику совместно, период ожидания может быть не ограничен.

## <a name="when_all"></a><a name="when_all"></a>When_all

Создает задачу, которая завершается успешно, если все задачи, предоставленные в качестве аргументов, завершаются успешно.

```cpp
template <typename _Iterator>
auto when_all(
    _Iterator _Begin,
    _Iterator _End,
    const task_options& _TaskOptions = task_options()) ->
    decltype (details::_WhenAllImpl<typename std::iterator_traits<_Iterator>::value_type::result_type,
    _Iterator>::_Perform(_TaskOptions, _Begin,  _End));
```

### <a name="parameters"></a>Параметры

*_Iterator*<br/>
Тип итератора ввода.

*_begin*<br/>
Позиция первого элемента в диапазоне элементов, которые будут объединены в результирующую задачу.

*_end*<br/>
Позиция первого элемента за пределами диапазона элементов, которые будут объединены в результирующую задачу.

*_TaskOptions*<br/>
Объект `task_options`.

### <a name="return-value"></a>Возвращаемое значение

Задача, которая успешно выполняется, когда все задачи ввода успешно завершены. Если входные задачи относятся к типу `T`, выводом этой функции будет `task<std::vector<T>>`. Если входные задачи относятся к типу `void`, выходная задача также будет `task<void>`.

### <a name="remarks"></a>Remarks

Функция `when_all` является функцией без блокировки, в качестве результата создающей `task`. В отличие от [задачи::подождите,](task-class.md#wait)это безопасно назвать эту функцию в приложении UWP на потоке ASTA (Application STA).

Если одна из задач отменена или бросает исключение, возвращенная задача завершится досрочно, в отмененном состоянии, и исключение, если `task::wait` оно происходит, будет брошено, если вы вызовете [задачу:::get](task-class.md#get) или на этой задаче.

Для получения дополнительной информации [см.](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)

## <a name="when_any"></a><a name="when_any"></a>When_any

Создает задачу, которая завершается успешно, если любая из задач, предоставленных в качестве аргументов, завершается успешно.

```cpp
template<typename _Iterator>
auto when_any(
    _Iterator _Begin,
    _Iterator _End,
    const task_options& _TaskOptions = task_options())
    -> decltype (
        details::_WhenAnyImpl<
            typename std::iterator_traits<_Iterator>::value_type::result_type,
            _Iterator>::_Perform(_TaskOptions, _Begin, _End));

template<typename _Iterator>
auto when_any(
    _Iterator _Begin,
    _Iterator _End,
    cancellation_token _CancellationToken)
       -> decltype (
           details::_WhenAnyImpl<
               typename std::iterator_traits<_Iterator>::value_type::result_type,
               _Iterator>::_Perform(_CancellationToken._GetImplValue(), _Begin, _End));
```

### <a name="parameters"></a>Параметры

*_Iterator*<br/>
Тип итератора ввода.

*_begin*<br/>
Позиция первого элемента в диапазоне элементов, которые будут объединены в результирующую задачу.

*_end*<br/>
Позиция первого элемента за пределами диапазона элементов, которые будут объединены в результирующую задачу.

*_TaskOptions*<br/>
*_CancellationToken*<br/>
Токен отмены, который контролирует отмену возвращаемой задачи. Если токен отмены отсутствует, результирующая задача получит токен отмены, который используется для выполнения задачи.

### <a name="return-value"></a>Возвращаемое значение

Задача, которая завершается успешно, если все входные задачи завершены успешно. Если входные задачи имеют тип `T`, выходными данными этой функции будут `task<std::pair<T, size_t>>>`, где первый элемент пары является результатом завершаемой задачи, а второй элемент — индексом завершенной задачи. Если входные задачи имеют тип `void`, выходными данными будет `task<size_t>`, где результат — индекс завершаемой задачи.

### <a name="remarks"></a>Remarks

Функция `when_any` является функцией без блокировки, в качестве результата создающей `task`. В отличие от [задачи::подождите,](task-class.md#wait)это безопасно назвать эту функцию в приложении UWP на потоке ASTA (Application STA).

Для получения дополнительной информации [см.](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
