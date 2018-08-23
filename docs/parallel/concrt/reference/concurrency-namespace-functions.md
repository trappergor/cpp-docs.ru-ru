---
title: функции пространства имен Concurrency | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 520a6dff-9324-4df2-990d-302e3050af6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98e385f965ab3036d6ccf2383fd4ae6f420eb548
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2018
ms.locfileid: "42541080"
---
# <a name="concurrency-namespace-functions"></a>функции пространства имен Concurrency
||||  
|-|-|-|  
|[Alloc](#alloc)|[CreateResourceManager](#createresourcemanager)|[DisableTracing](#disabletracing)|  
|[EnableTracing](#enabletracing)|[бесплатно](#free)|[GetExecutionContextId](#getexecutioncontextid)|  
|[GetOSVersion](#getosversion)|[GetProcessorCount](#getprocessorcount)|[GetProcessorNodeCount](#getprocessornodecount)|  
|[GetSchedulerId](#getschedulerid)|[Trace_agents_register_name](#trace_agents_register_name)|[asend](#asend)|  
|[cancel_current_task](#cancel_current_task)|[clear](#clear)|[create_async](#create_async)|  
|[create_task](#create_task)|[get_ambient_scheduler](#get_ambient_scheduler)|[internal_assign_iterators](#internal_assign_iterators)|  
|[interruption_point](#interruption_point)|[is_current_task_group_canceling](#is_current_task_group_canceling)|[make_choice](#make_choice)|  
|[make_greedy_join](#make_greedy_join)|[make_join](#make_join)|[make_task](#make_task)|  
|[parallel_buffered_sort](#parallel_buffered_sort)|[parallel_for](#parallel_for)|[parallel_for_each](#parallel_for_each)|  
|[parallel_invoke](#parallel_invoke)|[parallel_radixsort](#parallel_radixsort)|[parallel_reduce](#parallel_reduce)|  
|[parallel_sort](#parallel_sort)|[parallel_transform](#parallel_transform)|[receive](#receive)|  
|[run_with_cancellation_token](#run_with_cancellation_token)|[send](#send)|[set_ambient_scheduler](#set_ambient_scheduler)|  
|[set_task_execution_resources](#set_task_execution_resources)|[swap](#swap)|[task_from_exception](#task_from_exception)|  
|[task_from_result](#task_from_result)|[try_receive](#try_receive)|[wait](#wait)|  
|[when_all](#when_all)|[when_any](#when_any)|  
  
##  <a name="alloc"></a>  Alloc  
 Выделяет блок памяти указанного размера из подраспределителя кэширования среды параллелизма.  
  
```
void* __cdecl Alloc(size_t _NumBytes);
```  
  
### <a name="parameters"></a>Параметры  
 `_NumBytes`  
 Число байтов памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что выделенную память.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о том, какие сценарии в приложении преимущество от использования подраспределитель кэширования, см. в разделе [планировщик](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
##  <a name="asend"></a>  asend  
 Асинхронная операция отправки, которая планирует задачу для распространения данных в целевой блок.  
  
```
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
 `T`  
 Тип данных для отправки.  
  
 `_Trg`  
 Указатель или ссылку на целевой объект, на который отправляются данные.  
  
 `_Data`  
 Ссылка на передаваемые данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если сообщение было принято, прежде чем он был возвращен, `false` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [функции передачи сообщений](../../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="cancel_current_task"></a>  cancel_current_task  
 Отменяет выполняющуюся в данный момент задачу. Эту функцию можно вызывать из тела задачи, чтобы прервать выполнение задачи и перевести ее в состояние `canceled`.  
  
 Вызов этой функции является неподдерживаемым сценарием, если вы не находитесь в теле `task`. Такие действия приведут к неопределенному поведению, например сбою или зависанию в приложении.  
  
```
inline __declspec(noreturn) void __cdecl cancel_current_task();
```  
  
##  <a name="clear"></a>  Очистить  
 Очищает параллельную очередь, уничтожая все в данный момент элементов в очереди. Этот метод не является безопасным в режиме параллелизма.  
  
```
template<typename T, class _Ax>
void concurrent_queue<T, _Ax>::clear();
```   
  
### <a name="parameters"></a>Параметры  
 `T`  
 `_Ax`  
  
##  <a name="create_async"></a>  create_async  
 Создает асинхронную конструкцию среды выполнения Windows на основе предоставленного пользователем лямбда-выражения или объекта функции. Возвращаемый тип `create_async` — один из следующих: `IAsyncAction^`, `IAsyncActionWithProgress<TProgress>^`, `IAsyncOperation<TResult>^` или `IAsyncOperationWithProgress<TResult, TProgress>^`, в зависимости от сигнатуры лямбда-выражения, переданного методу.  
  
```
template<typename _Function>
__declspec(noinline) auto create_async(const _Function& _Func)
    -> decltype(ref new details::_AsyncTaskGeneratorThunk<_Function>(_Func));
```  
  
### <a name="parameters"></a>Параметры  
 `_Function`  
 `_Func`  
 Лямбда-выражение или объект функции, из которого требуется создать асинхронную конструкцию среды выполнения Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Асинхронная конструкция, представленная Asyncaction ^, IAsyncActionWithProgress\<TProgress > ^, IAsyncOperation\<TResult > ^, или IAsyncOperationWithProgress\<TResult, TProgress > ^. Возвращаемый интерфейс зависит от сигнатуры лямбда-выражения, переданного функции.  
  
### <a name="remarks"></a>Примечания  
 Тип возвращаемого значения лямбда-выражения определяет, чем является конструкция — действием или операцией.  
  
 Лямбда-выражения, возвращающие значение void, приводят к созданию действий. Лямбда-выражения, возвращающие результат типа `TResult`, приводят к созданию операций TResult.  
  
 Лямбда-выражение может также возвращать объект `task<TResult>`, который инкапсулирует асинхронную работу внутри себя или является продолжением цепочки задач, представляющих асинхронную работу. В этом случае лямбда-выражение само выполняется встроенным образом, поскольку задачами являются те, которые выполняются асинхронно, и возвращаемый тип лямбда-выражения распаковывается для создания асинхронной конструкции, возвращаемой `create_async`. Это означает, что лямбда-выражение, которое возвращает task\<void >, вызовет создание действий и лямбда-выражение, которое возвращает task\<TResult >, вызовет создание операций TResult.  
  
 Лямбда-выражение может принимать ноль, один или два аргумента. Допустимые аргументы — `progress_reporter<TProgress>` и `cancellation_token`, в этом порядке, если используются оба. Лямбда-выражение без аргументов вызывает создание асинхронной конструкции без возможности выдачи отчета о ходе выполнения. Лямбда-выражение, которое принимает progress_reporter\<TProgress > приведет к `create_async` для возврата асинхронной конструкции, которая сообщает о ходе выполнения типа TProgress каждый раз `report` вызывается метод объекта progress_reporter. Лямбда-выражение, которое принимает cancellation_token, может использовать этот токен для проверки отмены или передать создаваемым им задачам, чтобы отмена асинхронной конструкции приводила к отмене этих задач.  
  
 Если тело лямбда-выражения или объекта функции возвращает результат (а не task\<TResult >), многопотоковом подразделении выполняется асинхронно в рамках процесса, в контексте задачи, который среда неявно создает для него. Метод `IAsyncInfo::Cancel` вызовет отмену неявной задачи.  
  
 Если тело лямбда-выражения возвращает задачу, лямбда-выражение выполняется встроенным образом, и путем объявления, чтобы лямбда-выражение принимало аргумент типа `cancellation_token`, можно привести в действие отмену всех задач, создаваемых внутри лямбда-выражения путем передачи этого токена при их создании. Можно также использовать метод `register_callback` для этого токена, чтобы вызвать выполнение исполняющей средой обратного вызова при вызове `IAsyncInfo::Cancel` для созданной асинхронной операции или действия.  
  
 Эта функция доступна только для приложений среды выполнения Windows.  
  
##  <a name="createresourcemanager"></a>  CreateResourceManager  
 Возвращает интерфейс, который представляет одноэлементный экземпляр диспетчера ресурсов среды выполнения с параллелизмом. Диспетчер ресурсов отвечает за назначение ресурсов планировщикам, которым требуется взаимодействовать друг с другом.  
  
```
IResourceManager* __cdecl CreateResourceManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Интерфейс `IResourceManager`.  
  
### <a name="remarks"></a>Примечания  
 Несколько последующие вызовы этого метода будет возвращать один и тот же экземпляр диспетчера ресурсов. Каждый вызов метода увеличивает ссылку подсчета с помощью Resource Manager и должен совпадать с вызовом [IResourceManager::Release](http://msdn.microsoft.com/en-us/5d1356ec-fbd3-4284-a361-1e9e20bbb522) метод, когда планировщик завершает взаимодействует с диспетчером ресурсов.  
  
 [unsupported_os](unsupported-os-class.md) возникает исключение, если операционная система не поддерживается средой выполнения с параллелизмом.  
  
##  <a name="create_task"></a>  create_task  
 Создает объект PPL [задачи](http://msdn.microsoft.com/en-us/5389e8a5-5038-40b6-844a-55e9b58ad35f) объекта. Функция `create_task` может использоваться в любой ситуации, где бы вы использовали конструктор задач. Она предоставлена главным образом для удобства, поскольку позволяет использовать ключевое слово `auto` при создании задач.  
  
```
template<typename T>
__declspec(noinline) auto create_task(T _Param, const task_options& _TaskOptions = task_options())
    -> task<typename details::_TaskTypeFromParam<T>::T>;

template<typename _ReturnType>
__declspec( noinline) task<_ReturnType> create_task(const task<_ReturnType>& _Task);
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Тип параметра, из которого будет создаваться задача.  
  
 `_ReturnType`  
 `_Param`  
 Параметр, из которого будет создаваться задача. Это может быть объектом лямбда-выражения или функции, `task_completion_event` другой `task` объекта или интерфейс Windows::Foundation:: iasyncinfo, если задачи используются в приложении универсальной платформы Windows.  
  
 `_TaskOptions`  
 `_Task`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая задача типа `T`, в котором выведены из `_Param`.  
  
### <a name="remarks"></a>Примечания  
 Первый перегруженный метод ведет себя как конструктор задач, который принимает один параметр.  
  
 Вторая перегруженная связывающего токена отмены, поставляемый с вновь созданной задачей. При использовании этой перегрузки недопустимы для передачи в другом `task` объект в качестве первого параметра.  
  
 Тип возвращаемой задачи выводится из первого параметра функции. Если `_Param` — `task_completion_event<T>`, `task<T>`, или функтор, возвращающий тип `T` или `task<T>`, тип созданной задачи — `task<T>`.  
  
 В приложении UWP Если `_Param` имеет тип Windows::Foundation:: iasyncoperation\<T > ^ или Windows::Foundation:: iasyncoperationwithprogress\<T, P > ^, или функтор, возвращающий один из этих типов, созданная задача будет Тип `task<T>`. Если `_Param` имеет тип Windows::Foundation:: iasyncaction ^ или Windows::Foundation:: iasyncactionwithprogress\<P > ^, или функтор, возвращающий один из этих типов, созданная задача будет иметь тип `task<void>`.  
  
##  <a name="disabletracing"></a>  DisableTracing  
 Отключает трассировку в среде выполнения с параллелизмом. Эту функция не рекомендуется использовать, поскольку трассировка событий Windows по умолчанию не регистрируется.  
  
```
__declspec(deprecated("Concurrency::DisableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl DisableTracing();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если трассировка была правильно отключена, `S_OK` возвращается. Если трассировка не была запущена ранее, возвращается `E_NOT_STARTED`  
  
##  <a name="enabletracing"></a>  EnableTracing  
 Включает трассировку в среде выполнения с параллелизмом. Эта функция не рекомендована к использованию, поскольку трассировка событий Windows теперь по умолчанию включена.  
  
```
__declspec(deprecated("Concurrency::EnableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl EnableTracing();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если трассировка была правильно запущена, `S_OK` возвращается; в противном случае — значение `E_NOT_STARTED` возвращается.  
  
##  <a name="free"></a>  бесплатно  
 Освобождает блок памяти, ранее выделенный методом `Alloc` для подраспределителя кэширования среды выполнения с параллелизмом.  
  
```
void __cdecl Free(_Pre_maybenull_ _Post_invalid_ void* _PAllocation);
```  
  
### <a name="parameters"></a>Параметры  
 `_PAllocation`  
 Указатель на память, выделенную ранее `Alloc` метод, который необходимо освободить. Если параметр `_PAllocation` присвоено значение `NULL`, этот метод игнорирует его и немедленный возврат.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о том, какие сценарии в приложении преимущество от использования подраспределитель кэширования, см. в разделе [планировщик](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
##  <a name="get_ambient_scheduler"></a>  get_ambient_scheduler  
  
```
inline std::shared_ptr<::Concurrency::scheduler_interface> get_ambient_scheduler();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="getexecutioncontextid"></a>  GetExecutionContextId  
 Возвращает уникальный идентификатор, который можно назначить контексту выполнения, реализующему интерфейс `IExecutionContext`.  
  
```
unsigned int __cdecl GetExecutionContextId();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уникальный идентификатор для контекста выполнения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод позволяет получить идентификатор контекста выполнения, прежде чем передать `IExecutionContext` интерфейсом в виде параметра любого из методов, предлагаемые диспетчером ресурсов.  
  
##  <a name="getosversion"></a>  GetOSVersion  
 Возвращает версию операционной системы.  
  
```
IResourceManager::OSVersion __cdecl GetOSVersion();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Перечислимое значение, представляющее операционной системы.  
  
### <a name="remarks"></a>Примечания  
 [unsupported_os](unsupported-os-class.md) возникает исключение, если операционная система не поддерживается средой выполнения с параллелизмом.  
  
##  <a name="getprocessorcount"></a>  GetProcessorCount  
 Возвращает число аппаратных потоков базовой системы.  
  
```
unsigned int __cdecl GetProcessorCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество аппаратных потоков.  
  
### <a name="remarks"></a>Примечания  
 [unsupported_os](unsupported-os-class.md) возникает исключение, если операционная система не поддерживается средой выполнения с параллелизмом.  
  
##  <a name="getprocessornodecount"></a>  GetProcessorNodeCount  
 Возвращает число узлов NUMA или пакетов процессора в базовой системе.  
  
```
unsigned int __cdecl GetProcessorNodeCount();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число пакетов процессора или узлов NUMA.  
  
### <a name="remarks"></a>Примечания  
 Если система содержит больше узлов NUMA, чем пакеты процессора, возвращается число узлов NUMA, в противном случае возвращается число пакетов процессора.  
  
 [unsupported_os](unsupported-os-class.md) возникает исключение, если операционная система не поддерживается средой выполнения с параллелизмом.  
  
##  <a name="getschedulerid"></a>  GetSchedulerId  
 Возвращает уникальный идентификатор, который можно назначить планировщику, реализующему интерфейс `IScheduler`.  
  
```
unsigned int __cdecl GetSchedulerId();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уникальный идентификатор для планировщика.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для получения идентификатора для планировщика, прежде чем передать `IScheduler` интерфейсом в виде параметра любого из методов, предлагаемые диспетчером ресурсов.  
  
##  <a name="internal_assign_iterators"></a>  internal_assign_iterators  
  
```
template<typename T, class _Ax>
template<class _I> 
void concurrent_vector<T, _Ax>::internal_assign_iterators(
   _I first,
   _I last);
```   
  
### <a name="parameters"></a>Параметры  
 `T`  
 `_Ax`  
 `_I`  
 `first`  
 `last`  
  
##  <a name="interruption_point"></a>  interruption_point  
 Создает точку прерывания для отмены. Если отмена выполняется в контексте, где вызывается эта функция, это создает внутреннее исключение, которое прерывает текущую выполняемую параллельную работу. Если отмена не выполняется, функция ничего не делает.  
  
```
inline void interruption_point();
```  
  
### <a name="remarks"></a>Примечания  
 Не следует перехватывать внутреннее исключение отмены, создаваемое функцией `interruption_point()`. Исключение будет перехвачено и обработано средой выполнения, и его перехват может вызвать непредсказуемое поведение программы.  
  
##  <a name="is_current_task_group_canceling"></a>  is_current_task_group_canceling  
 Возвращает значение, указывающее, находится ли группа задач, которая в данный момент выполняется в текущем контексте во встроенном режиме, в процессе активной отмены (или вскоре перейдет в это состояние). Обратите внимание, что в отсутствие групп задач, выполняющихся в текущем контексте во встроенном режиме, будет возвращено значение `false`.  
  
```
bool __cdecl is_current_task_group_canceling();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если группы задач, которые в данный момент Отмена, `false` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [отмены](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).  
  
##  <a name="make_choice"></a>  make_choice  
 Конструирует блок сообщений `choice` из необязательного объекта `Scheduler` или `ScheduleGroup` и двух или более источников входных данных.  
  
```
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
 `T1`  
 Тип блока сообщений первого источника.  
  
 `T2`  
 Тип блока сообщений второго источника.  
  
 `_PScheduler`  
 Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `choice` .  
  
 `_Item1`  
 Первый источник.  
  
 `_Item2`  
 Второй источник.  
  
 `_Items`  
 Дополнительные источники.  
  
 `_PScheduleGroup`  
 Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `choice` . Используемый объект `Scheduler` подразумевается группой расписаний.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Блок сообщений `choice` с двумя или более источниками входных данных.  
  
##  <a name="make_greedy_join"></a>  make_greedy_join  
 Конструирует блок сообщений `greedy multitype_join` из необязательного объекта `Scheduler` или `ScheduleGroup` и двух или более источников входных данных.  
  
```
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
 `T1`  
 Тип блока сообщений первого источника.  
  
 `T2`  
 Тип блока сообщений второго источника.  
  
 `_PScheduler`  
 Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` .  
  
 `_Item1`  
 Первый источник.  
  
 `_Item2`  
 Второй источник.  
  
 `_Items`  
 Дополнительные источники.  
  
 `_PScheduleGroup`  
 Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` . Используемый объект `Scheduler` подразумевается группой расписаний.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Блок сообщений `greedy multitype_join` с двумя или более источниками входных данных.  
  
##  <a name="make_join"></a>  make_join  
 Конструирует блок сообщений `non_greedy multitype_join` из необязательного объекта `Scheduler` или `ScheduleGroup` и двух или более источников входных данных.  
  
```
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
 `T1`  
 Тип блока сообщений первого источника.  
  
 `T2`  
 Тип блока сообщений второго источника.  
  
 `_PScheduler`  
 Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` .  
  
 `_Item1`  
 Первый источник.  
  
 `_Item2`  
 Второй источник.  
  
 `_Items`  
 Дополнительные источники.  
  
 `_PScheduleGroup`  
 Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` . Используемый объект `Scheduler` подразумевается группой расписаний.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Блок сообщений `non_greedy multitype_join` с двумя или более источниками входных данных.  
  
##  <a name="make_task"></a>  make_task  
 Метод фабрики для создания объекта `task_handle`.  
  
```
template <class _Function>
task_handle<_Function> make_task(const _Function& _Func);
```  
  
### <a name="parameters"></a>Параметры  
 `_Function`  
 Тип объекта функции, который будет вызываться для выполнения работы, представленной `task_handle` объекта.  
  
 `_Func`  
 Функция, которая будет вызываться для выполнения работы, представленной `task_handle` объекта. Это может быть лямбда-функтор, указатель на функцию, или любым объектом, который поддерживает версию оператора вызова функции с сигнатурой `void operator()()`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `task_handle`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна, когда вам нужно создать `task_handle` объекта с помощью лямбда-выражения, так как он позволяет создать объект, не зная истинный тип лямбда-функтора.  
  
##  <a name="parallel_buffered_sort"></a>  parallel_buffered_sort  
 В параллельном режиме упорядочивает элементы в указанном диапазоне в не нисходящем порядке или согласно критерию упорядочивания, заданному бинарным предикатом. Эта функция семантически аналогична `std::sort` в том, что она является нестабильной сортировкой на месте на основе сравнения, за исключением того, что ей требуется `O(n)` дополнительного пространства и инициализация по умолчанию для сортируемых элементов.  
  
```
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
 `_Random_iterator`  
 Тип итератора входного диапазона.  
  
 `_Allocator`  
 Тип распределитель памяти совместимой стандартной библиотеки C++.  
  
 `_Function`  
 Тип бинарное средство сравнения.  
  
 `_Begin`  
 Итератор произвольного доступа, обращающийся к позиции первого элемента в сортируемом диапазоне.  
  
 `_End`  
 Итератор произвольного доступа, обращающийся к позиции после последнего элемента в сортируемом диапазоне.  
  
 `_Alloc`  
 Экземпляр распределитель памяти совместимой стандартной библиотеки C++.  
  
 `_Func`  
 Определяемый пользователем объект функции предиката, который определяет критерии сравнения, которые должны соблюдаться идущими подряд элементами при упорядочении. Бинарный предикат принимает два аргумента и возвращает `true` в случае соответствия и `false` в случае несоответствия. Эта функция средства сравнения должна задать строгое слабое упорядочение пар элементов последовательности.  
  
 `_Chunk_size`  
 Минимальный размер блока, который будет разбит на два для параллельного выполнения.  
  
### <a name="remarks"></a>Примечания  
 Все перегрузки требуют `n * sizeof(T)` дополнительное место, где `n` — количество элементов для сортировки и `T` является типом элемента. В большинстве случаев parallel_buffered_sort покажет повышение производительности по [parallel_sort](concurrency-namespace-functions.md), и его следует использовать через parallel_sort при наличии доступной памяти.  
  
 Если вы не предоставляете бинарное средство сравнения `std::less` используется в качестве значения по умолчанию, которое требуется предоставить оператор элемента типа `operator<()`.  
  
 Если вы не предоставляете распределителя типа или экземпляра, распределитель памяти стандартной библиотеки C++ `std::allocator<T>` используется для выделения буфера.  
  
 Алгоритм делит входной диапазон на два блока и последовательно делит каждый блок на два подблока для параллельного выполнения. Необязательный аргумент `_Chunk_size` можно использовать, чтобы показать алгоритму, что необходимо обрабатывать блоки размера < `_Chunk_size` последовательно.  
  
##  <a name="parallel_for"></a>  parallel_for  
 `parallel_for` выполняет итерацию по диапазону индексов и выполняет предоставленную пользователем функцию в каждой итерации параллельно.  
  
```
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
 `_Index_type`  
 Тип индекса, используемого для итерации.  
  
 `_Function`  
 Тип функции, будет выполнен на каждой итерации.  
  
 `_Partitioner`  
 Тип разделителя, в котором используется для секционирования указанный диапазон.  
  
 `first`  
 Первый индекс для включения в итерации.  
  
 `last`  
 Индекс на один после последнего индекса должны быть включены в итерации.  
  
 `_Step`  
 Значение шага при переборе от `first` для `last`. Шаг должен быть положительным. [invalid_argument](../../../standard-library/invalid-argument-class.md) возникает исключение, если на этапе не меньше 1.  
  
 `_Func`  
 Функция, выполняемая в каждой итерации. Это может быть лямбда-выражение, указатель на функцию, или любой объект, который поддерживает версию оператора вызова функции с сигнатурой `void operator()(_Index_type)`.  
  
 `_Part`  
 Ссылка на объект-разделитель. Аргумент может принимать одно из `const` [auto_partitioner](auto-partitioner-class.md)`&`, `const` [static_partitioner](static-partitioner-class.md)`&`, `const` [simple_ разделитель](simple-partitioner-class.md) `&` или [affinity_partitioner](affinity-partitioner-class.md) `&` Если [affinity_partitioner](affinity-partitioner-class.md) используется объект, ссылка должен быть неконстантной l значение ссылки, чтобы алгоритм мог сохранять состояние для повторного использования в последующих циклах.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [параллельные алгоритмы](../../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="parallel_for_each"></a>  parallel_for_each  
 `parallel_for_each` применяет указанную функцию к каждому элементу в диапазоне параллельно. Эта функция семантически эквивалентна функции `for_each` в пространстве имен `std`, за исключением того, что итерация по элементам выполняется параллельно и порядок итерации не определен. Аргумент `_Func` должен поддерживать оператор вызова функции формы `operator()(T)`, где параметр `T` является типом элемента контейнера, для которого выполняется итерация.  
  
```
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
 `_Iterator`  
 Тип итератора, используемый для перебора контейнера.  
  
 `_Function`  
 Тип функции, которая будет применяться к каждому элементу в диапазоне.  
  
 `_Partitioner`  
 `first`  
 Итератор, обращающийся к позиции первого элемента для включения в параллельных итерации.  
  
 `last`  
 Итератор, указывающий на позицию, следующую за последним элементом для включения в параллельных итерации.  
  
 `_Func`  
 Объект определяемой пользователем функции, которая применяется к каждому элементу в диапазоне.  
  
 `_Part`  
 Ссылка на объект-разделитель. Аргумент может принимать одно из `const` [auto_partitioner](auto-partitioner-class.md)`&`, `const` [static_partitioner](static-partitioner-class.md)`&`, `const` [simple_ разделитель](simple-partitioner-class.md) `&` или [affinity_partitioner](affinity-partitioner-class.md) `&` Если [affinity_partitioner](affinity-partitioner-class.md) используется объект, ссылка должен быть неконстантной l значение ссылки, чтобы алгоритм мог сохранять состояние для повторного использования в последующих циклах.  
  
### <a name="remarks"></a>Примечания  
 [auto_partitioner](auto-partitioner-class.md) будет использоваться для перегрузки без явного разделения.  
  
 Для итераторов, не поддерживающих произвольный доступ, только [auto_partitioner](auto-partitioner-class.md) поддерживается.  
  
 Дополнительные сведения см. в разделе [параллельные алгоритмы](../../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="parallel_invoke"></a>  parallel_invoke  
 Выполняет объекты функции, предоставленные в виде параметров, в параллельном режиме и блокирует их до завершения выполнения. Каждый объект функции может быть лямбда-выражением, указателем на функцию или любым объектом, который поддерживает оператор вызова функции с подписью `void operator()()`.  
  
```
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
 `_Function1`  
 Тип первого объект функции для выполнения параллельно.  
  
 `_Function2`  
 Тип второго объекта функции для выполнения в параллельном режиме.  
  
 `_Function3`  
 Тип третьего объект функции для выполнения параллельно.  
  
 `_Function4`  
 Тип четвертого объект функции для выполнения параллельно.  
  
 `_Function5`  
 Тип пятого объект функции для выполнения параллельно.  
  
 `_Function6`  
 Тип шестого объект функции для выполнения параллельно.  
  
 `_Function7`  
 Тип седьмого объект функции для выполнения параллельно.  
  
 `_Function8`  
 Тип восьмого объект функции для выполнения параллельно.  
  
 `_Function9`  
 Тип девятого объект функции для выполнения параллельно.  
  
 `_Function10`  
 Тип десятого объект функции для выполнения параллельно.  
  
 `_Func1`  
 Первый объект функции для выполнения параллельно.  
  
 `_Func2`  
 Второй объект функции для выполнения параллельно.  
  
 `_Func3`  
 Третий объект функции для выполнения параллельно.  
  
 `_Func4`  
 Четвертый объект функции для выполнения параллельно.  
  
 `_Func5`  
 Пятый объект функции для выполнения параллельно.  
  
 `_Func6`  
 Шестой объект функции для выполнения параллельно.  
  
 `_Func7`  
 Седьмой объект функции для выполнения параллельно.  
  
 `_Func8`  
 Восьмой объект функции для выполнения параллельно.  
  
 `_Func9`  
 Девятый объект функции для выполнения параллельно.  
  
 `_Func10`  
 Десятый объект функции для выполнения параллельно.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание на то, что один или несколько объектов-функций, предоставленных в качестве параметров, может выполняться встроено в контексте вызова.  
  
 Если один или несколько объектов-функций, передаваемые в качестве параметров, эта функция создает исключение, среда выполнения будет выбрать одно такое исключение и распространить из вызова `parallel_invoke`.  
  
 Дополнительные сведения см. в разделе [параллельные алгоритмы](../../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="parallel_radixsort"></a>  parallel_radixsort  
 Располагает элементы в указанном диапазоне в неубывающем порядке, используя алгоритм сортировки основания системы счисления. Это стабильная функция сортировки, для которой требуется функция проекции, способная проецировать сортируемые элементы в неподписанные ключи целочисленного типа. Для сортируемых элементов требуется инициализация по умолчанию.  
  
```
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
 `_Random_iterator`  
 Тип итератора входного диапазона.  
  
 `_Allocator`  
 Тип распределитель памяти совместимой стандартной библиотеки C++.  
  
 `_Function`  
 Тип функции проекции.  
  
 `_Begin`  
 Итератор произвольного доступа, обращающийся к позиции первого элемента в сортируемом диапазоне.  
  
 `_End`  
 Итератор произвольного доступа, обращающийся к позиции после последнего элемента в сортируемом диапазоне.  
  
 `_Alloc`  
 Экземпляр распределитель памяти совместимой стандартной библиотеки C++.  
  
 `_Proj_func`  
 Объект функции проекции, определяемые пользователем, который преобразует элемент в виде целочисленного значения.  
  
 `_Chunk_size`  
 Минимальный размер блока, который будет разбит на два для параллельного выполнения.  
  
### <a name="remarks"></a>Примечания  
 Все перегрузки требуют `n * sizeof(T)` дополнительное место, где `n` — количество элементов для сортировки и `T` является типом элемента. Проекция унарного функтора, с подписью `I _Proj_func(T)` необходим для возвращения ключа для заданного элемента, где `T` является типом элемента и `I` является тип целочисленного типа без знака.  
  
 Если вы не предоставляете функция проекции, по умолчанию функция проекции, которая просто возвращает элемент используется для целочисленных типов. Функция завершится с ошибкой для компиляции, если элемент не является целым типом при отсутствии функции проекции.  
  
 Если вы не предоставляете распределителя типа или экземпляра, распределитель памяти стандартной библиотеки C++ `std::allocator<T>` используется для выделения буфера.  
  
 Алгоритм делит входной диапазон на два блока и последовательно делит каждый блок на два подблока для параллельного выполнения. Необязательный аргумент `_Chunk_size` можно использовать, чтобы показать алгоритму, что необходимо обрабатывать блоки размера < `_Chunk_size` последовательно.  
  
##  <a name="parallel_reduce"></a>  parallel_reduce  
 Параллельно вычисляет сумму всех элементов в указанном диапазоне путем вычисления последовательных частичных сумм или вычисляет результаты последовательных частичных сумм, полученных сходным образом с использованием указанной бинарной операции, отличной от суммирования. `parallel_reduce` семантически аналогичен `std::accumulate`, но требует, чтобы бинарная операция была ассоциативна, а также значение идентификатора вместо начального значения.  
  
```
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
 `_Forward_iterator`  
 Тип итератора диапазона ввода.  
  
 `_Sym_reduce_fun`  
 Тип функции симметричной редукции. Это должен быть тип функции с сигнатурой `_Reduce_type _Sym_fun(_Reduce_type, _Reduce_type)`, где _Reduce_type совпадает с типом идентификатора и типом результата редукции. В третьей перегрузке он должен быть совместим с типом вывода `_Range_reduce_fun`.  
  
 `_Reduce_type`  
 Тип, до которого будет редуцирован ввод, который может отличаться от типа входного элемента. Возвращаемое значение и значение идентификатора будут иметь этот тип.  
  
 `_Range_reduce_fun`  
 Тип функции редукции диапазона. Это должен быть тип функции с сигнатурой `_Reduce_type _Range_fun(_Forward_iterator, _Forward_iterator, _Reduce_type)`, _Reduce_type совпадает с типом идентификатора и типом результата редукции.  
  
 `_Begin`  
 Итератор ввода, указывающий на первый элемент в диапазоне для редукции.  
  
 `_End`  
 Итератор ввода, указывающий на позицию после последнего элемента в диапазоне для редукции.  
  
 `_Identity`  
 Значение идентификатора `_Identity` относится к тому же типу, что и результат редукции, а также совпадает с `value_type` итератора для первой и второй перегрузок. В третьей перегрузке значение идентификатора должно иметь тот же тип, что и результат редукции, но может отличаться от `value_type` итератора. Оно должно иметь такое соответствующее значение, чтобы оператор редукции диапазона `_Range_fun`, примененный к диапазону из единственного элемента типа `value_type` и значению идентификатора, вел себя подобно приведению типа этого значения из типа `value_type` в тип идентификатора.  
  
 `_Sym_fun`  
 Симметричная функция, которая будет использоваться на второй стадии редукции. Дополнительные сведения см. в примечаниях.  
  
 `_Range_fun`  
 Симметричная функция, которая будет использоваться на первой стадии редукции. Дополнительные сведения см. в примечаниях.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат редукции.  
  
### <a name="remarks"></a>Примечания  
 Для выполнения параллельной редукции функция делит диапазон на блоки на основе количества работников, доступных базовому планировщику. Редукция происходит в две стадии, на первой стадии выполняется редукция в каждом блоке, на второй стадии выполняется редукция частичных результатов из каждого блока.  
  
 Первая перегрузка требует, чтобы типы итератора `value_type` и `T` были такими же, как и тип значения идентификатора и тип результата редукции. Тип элемента T должен предоставить оператор `T T::operator + (T)`, чтобы выполнить редукцию элементов в каждом блоке. Тот же оператор используется на второй стадии.  
  
 Вторая перегрузка также требует, чтобы тип итератора `value_type` был таким же, как и тип значения идентификатора и тип результата редукции. Предоставленный бинарный оператор `_Sym_fun` используется на обеих стадиях редукции со значением идентификатора в качестве начального значения для первой стадии.  
  
 В третьей перегрузке тип значения идентификатора должен совпадать с типом результата редукции, но `value_type` итератора может отличаться от них. Функция редукции диапазона `_Range_fun` используется на первой стадии со значением идентификатора в качестве начального значения, а бинарная функция `_Sym_reduce_fun` применяется к промежуточным результатам на второй стадии.  
  
##  <a name="parallel_sort"></a>  parallel_sort  
 В параллельном режиме упорядочивает элементы в указанном диапазоне в не нисходящем порядке или согласно критерию упорядочивания, заданному бинарным предикатом. Эта функция семантически схожа с `std::sort`, так как она основана на сравнении, неустойчива, сортирует на месте.  
  
```
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
 `_Random_iterator`  
 Тип итератора входного диапазона.  
  
 `_Function`  
 Тип бинарного функтора сравнения.  
  
 `_Begin`  
 Итератор произвольного доступа, обращающийся к позиции первого элемента в сортируемом диапазоне.  
  
 `_End`  
 Итератор произвольного доступа, обращающийся к позиции после последнего элемента в сортируемом диапазоне.  
  
 `_Func`  
 Определяемый пользователем объект функции предиката, который определяет критерии сравнения, которые должны соблюдаться идущими подряд элементами при упорядочении. Бинарный предикат принимает два аргумента и возвращает `true` в случае соответствия и `false` в случае несоответствия. Эта функция средства сравнения должна задать строгое слабое упорядочение пар элементов последовательности.  
  
 `_Chunk_size`  
 Минимальный размер блока, который будет разбит на два для параллельного выполнения.  
  
### <a name="remarks"></a>Примечания  
 Первая перегрузка использует бинарное средство сравнения `std::less`.  
  
 Вторая перегрузка использует предоставленное бинарное средство сравнения, которое должно иметь сигнатуру `bool _Func(T, T)`, где `T` — тип элементов во входном диапазоне.  
  
 Алгоритм делит входной диапазон на два блока и последовательно делит каждый блок на два подблока для параллельного выполнения. Необязательный аргумент `_Chunk_size` можно использовать, чтобы показать алгоритму, что необходимо обрабатывать блоки размера < `_Chunk_size` последовательно.  
  
##  <a name="parallel_transform"></a>  parallel_transform  
 Применяет заданный объект функции к каждому элементу в исходном диапазоне или к паре элементов из двух исходных диапазонов и параллельно копирует возвращаемые значения объекта функции в диапазон назначения. Эта функция семантически эквивалентна `std::transform`.  
  
```
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
 `_Input_iterator1`  
 Тип первого или единственного итератора ввода.  
  
 `_Output_iterator`  
 Тип итератора вывода.  
  
 `_Unary_operator`  
 Тип унарного функтора, который должен выполняться для каждого элемента во входном диапазоне.  
  
 `_Input_iterator2`  
 Тип второго итератора ввода.  
  
 `_Binary_operator`  
 Тип бинарного функтора, выполняемого попарно на элементах из двух исходных диапазонов.  
  
 `_Partitioner`  
 `first1`  
 Итератор ввода указывает на позицию первого элемента в первом или единственном исходном обрабатываемом диапазоне.  
  
 `last1`  
 Итератор ввода указывает на позицию, следующую за последним элементом в первом или единственном исходном обрабатываемом диапазоне.  
  
 `_Result`  
 Итератор вывода указывает на позицию первого элемента в диапазоне назначения.  
  
 `_Unary_op`  
 Определенный пользователем объект унарной функции, который применяется к каждому элементу в исходном диапазоне.  
  
 `_Part`  
 Ссылка на объект-разделитель. Аргумент может принимать одно из `const` [auto_partitioner](auto-partitioner-class.md)`&`, `const` [static_partitioner](static-partitioner-class.md)`&`, `const` [simple_ разделитель](simple-partitioner-class.md) `&` или [affinity_partitioner](affinity-partitioner-class.md) `&` Если [affinity_partitioner](affinity-partitioner-class.md) используется объект, ссылка должен быть неконстантной l значение ссылки, чтобы алгоритм мог сохранять состояние для повторного использования в последующих циклах.  
  
 `first2`  
 Итератор ввода указывает на позицию первого элемента во втором исходном обрабатываемом диапазоне.  
  
 `_Binary_op`  
 Определяемый пользователем объект бинарной функции, который последовательно применяется к парам элементов из двух исходных диапазонов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор вывода указывает на позицию после последнего элемента в диапазоне назначения, который получает выходные элементы, преобразованные объектом функции.  
  
### <a name="remarks"></a>Примечания  
 [auto_partitioner](auto-partitioner-class.md) будет использоваться для перегрузок без явного аргумента разделителя.  
  
 Для итераторов, не поддерживающих произвольный доступ, только [auto_partitioner](auto-partitioner-class.md) поддерживается.  
  
 Перегрузки, принимающие аргумент `_Unary_op`, преобразовывают диапазон ввода в диапазон вывода путем применения унарного функтора к каждому элементу в диапазоне ввода. `_Unary_op` должен поддерживать оператор вызова функции с сигнатурой `operator()(T)`, где `T` является типом значения диапазона, в котором выполняются итерации.  
  
 Перегрузки, принимающие аргумент `_Binary_op`, преобразовывают два диапазона ввода в диапазон вывода путем применения бинарного функтора к одному элементу из первого диапазона ввода и к одному элементу из второго диапазона ввода. `_Binary_op` должен поддерживать оператор вызова функции с сигнатурой `operator()(T, U)`, где `T`, `U` являются типами значений двух входных итераторов.  
  
 Дополнительные сведения см. в разделе [параллельные алгоритмы](../../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="receive"></a>  Получение  
 Общая реализация получения, позволяющая контексту ожидать данные строго из одного источника и фильтровать значения, которые принимаются.  
  
```
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
 `T`  
 Тип полезных данных.  
  
 `_Src`  
 Указатель или ссылку на источник, из которого ожидается данных.  
  
 `_Timeout`  
 Максимальное время, для которого следует метод для отображения данных в миллисекундах.  
  
 `_Filter_proc`  
 Функция фильтра, который определяет, следует ли принять сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение из источника, типа полезных данных.  
  
### <a name="remarks"></a>Примечания  
 Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE`, исключение [operation_timed_out](operation-timed-out-class.md) вызывается по истечении заданного количества времени до получения сообщения. Если требуется, чтобы время ожидания нулевой длины, следует использовать [try_receive](concurrency-namespace-functions.md) функции, в отличие от вызова `receive` с временем ожидания `0` (нуль), так как он более эффективен и не создает исключение времени ожидания.  
  
 Дополнительные сведения см. в разделе [функции передачи сообщений](../../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="run_with_cancellation_token"></a>  run_with_cancellation_token  
 Немедленно и синхронно выполняет объект функции в контексте заданного токена отмены.  
  
```
template<typename _Function>
void run_with_cancellation_token(
    const _Function& _Func,
    cancellation_token _Ct);
```  
  
### <a name="parameters"></a>Параметры  
 `_Function`  
 Тип объекта функции, который будет вызываться.  
  
 `_Func`  
 Объект функции, который будет выполняться. Этот объект должен поддерживать оператор вызова функции с сигнатурой (void).  
  
 `_Ct`  
 Токен отмены, который будет управлять неявной отменой объекта функции. Если требуется выполнение функции без возможности неявной отмены из-за отмены родительской группы задач, следует использовать `cancellation_token::none()`.  
  
### <a name="remarks"></a>Примечания  
 При отмене `cancellation_token` будут активированы все точки прерывания в объекте функции. Явный токен `_Ct` будет изолировать объект `_Func` от родительской отмены, если родитель имеет другой токен или вообще не имеет токена.  
  
##  <a name="send"></a>  Отправить  
 Синхронная операции отправки, которая ожидает принятия или отклонения сообщения целевым объектом.  
  
```
template <class T>
bool send(_Inout_ ITarget<T>* _Trg, const T& _Data);

template <class T>
bool send(ITarget<T>& _Trg, const T& _Data);
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Тип полезных данных.  
  
 `_Trg`  
 Указатель или ссылку на целевой объект, на который отправляются данные.  
  
 `_Data`  
 Ссылка на передаваемые данные.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если сообщение было принято, `false` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [функции передачи сообщений](../../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="set_ambient_scheduler"></a>  set_ambient_scheduler  
  
```
inline void set_ambient_scheduler(std::shared_ptr<::Concurrency::scheduler_interface> _Scheduler);
```  
  
### <a name="parameters"></a>Параметры  
 `_Scheduler`  
  
##  <a name="set_task_execution_resources"></a>  set_task_execution_resources  
 Ограничивает ресурсы выполнения, используемые внутренними рабочими потоками среды выполнения с параллелизмом, определенным набором сходства.  
  
 Этот метод можно вызывать только до создания диспетчера ресурсов или между двумя периодами существования диспетчера ресурсов. Его можно вызывать несколько раз при условии, что в момент вызова диспетчер ресурсов не существует. После задания ограничения сходства оно будет оставаться действительным до следующего допустимого вызова метода `set_task_execution_resources`.  
  
 Предоставленная маска сходства не обязана быть подмножеством маски сходства процесса. Сходство процесса обновляется при необходимости.  
  
```
void __cdecl set_task_execution_resources(
    DWORD_PTR _ProcessAffinityMask);

void __cdecl set_task_execution_resources(
    unsigned short count,
    PGROUP_AFFINITY _PGroupAffinity);
```  
  
### <a name="parameters"></a>Параметры  
 `_ProcessAffinityMask`  
 Маска сходства, которой должны быть ограничены рабочие потоки среды выполнения с параллелизмом. Используйте этот метод в системе с более чем 64 аппаратными потоками, только если требуется ограничить среду выполнения с параллелизмом подмножеством текущей группы процессоров. Как правило, следует использовать версию метода, которая принимает массив сходств группы в качестве параметра, чтобы ограничить сходство на компьютерах с более чем 64 аппаратными потоками.  
  
 `count`  
 Количество записей `GROUP_AFFINITY` в массиве, заданном параметром `_PGroupAffinity`.  
  
 `_PGroupAffinity`  
 Массив записей `GROUP_AFFINITY`.  
  
### <a name="remarks"></a>Примечания  
 Метод вызовет [invalid_operation](invalid-operation-class.md) исключение, если во время вызова, присутствует Resource Manager и [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если указанное сходство приводит в пустой набор ресурсы.  
  
 Версию метода, принимающую массив сходств группы в качестве параметра, следует использовать только в операционных системах Windows версии 7 и выше. В противном случае [invalid_operation](invalid-operation-class.md) возникает исключение.  
  
 Программное изменение сходства процесса после вызова этого метода не будет приводить к повторной оценке диспетчером ресурсов сходства, которым ограничен процесс. Таким образом, все изменения сходства процесса необходимо сделать до вызова этого метода.  
  
##  <a name="swap"></a>  swap  
 Меняет местами элементы двух объектов `concurrent_vector`.  
  
```
template<typename T, class _Ax>
inline void swap(
    concurrent_vector<T, _Ax>& _A,
    concurrent_vector<T, _Ax>& _B);
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных для элементов, хранящихся в параллельных векторах.  
  
 `_Ax`  
 Тип распределителя параллельных векторов.  
  
 `_A`  
 Параллельный вектор, элементы которого должны быть заменены параллельный вектор `_B`.  
  
 `_B`  
 Параллельный вектор, предоставляющий элементы для обмена местами, или вектор, элементы которого должны быть заменены параллельный вектор `_A`.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон является алгоритмом, специализированным на классе контейнера `concurrent_vector` для выполнения функции-члена `_A`. [concurrent_vector::Swap](concurrent-vector-class.md#swap)( `_B`). Это экземпляры частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, `template <class T> void swap(T&, T&)`, в алгоритме класс работает посредством присвоения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
 Этот метод не является безопасным в режиме параллелизма. Необходимо убедиться, что нет других потоков, выполняющих операции на любой из параллельные векторы, при вызове этого метода.  
  
##  <a name="task_from_exception"></a>  task_from_exception  
  
```
template<typename _TaskType, typename _ExType>
task<_TaskType> task_from_exception(
    _ExType _Exception,
    const task_options& _TaskOptions = task_options());
```  
  
### <a name="parameters"></a>Параметры  
 `_TaskType`  
 `_ExType`  
 `_Exception`  
 `_TaskOptions`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="task_from_result"></a>  task_from_result  
  
```
template<typename T>
task<T> task_from_result(
    T _Param,
    const task_options& _TaskOptions = task_options());

inline task<bool> task_from_result(ool _Param);

inline task<void> task_from_result(
    const task_options& _TaskOptions = task_options());
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 `_Param`  
 `_TaskOptions`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="trace_agents_register_name"></a>  Trace_agents_register_name  
 Связывает данное имя с блоком сообщений или агентом в трассировки событий Windows.  
  
```
template <class T>
void Trace_agents_register_name(
    _Inout_ T* _PObject,
    _In_z_ const wchar_t* _Name);
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Тип объекта. Обычно это блок сообщений или агент.  
  
 `_PObject`  
 Указатель на блок сообщений или агент, который именован в трассировке.  
  
 `_Name`  
 Имя для заданного объекта.  
  
##  <a name="try_receive"></a>  try_receive  
 Общая реализация проверки-получения, позволяющая контексту выполнять поиск данных строго из одного источника и фильтровать значения, которые принимаются. Если данные не готовы, метод вернет значение False.  
  
``` 
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
 `T`  
 Тип полезных данных  
  
 `_Src`  
 Указатель или ссылку на источник, из которого ожидается данных.  
  
 `_value`  
 Ссылка на расположение, где будет храниться результат.  
  
 `_Filter_proc`  
 Функция фильтра, который определяет, следует ли принять сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `bool` значение, указывающее, является ли полезная нагрузка в `_value`.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [функции передачи сообщений](../../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="wait"></a>  Подождите  
 Приостанавливает текущий контекст на указанный период времени.  
  
```
void __cdecl wait(unsigned int _Milliseconds);
```  
  
### <a name="parameters"></a>Параметры  
 `_Milliseconds`  
 Число миллисекунд, на которое должен быть приостановлен текущий контекст. Если параметру `_Milliseconds` задано значение `0`, текущий контекст должен уступить выполнение другим работоспособным контекстам перед продолжением.  
  
### <a name="remarks"></a>Примечания  
 Если этот метод вызывается в контексте планировщик среды выполнения с параллелизмом, планировщик найдет другой контекст для выполнения на основной ресурс. Поскольку планировщик предназначен для совместной работы по своей природе, этот контекст не может возобновиться точно после указанного числа миллисекунд. Если планировщик занят выполнением других задач, которые не уступают планировщику совместно, период ожидания может быть не ограничен.  
  
##  <a name="when_all"></a>  when_all  
 Создает задачу, которая завершается успешно, если все задачи, предоставленные в качестве аргументов, завершаются успешно.  
  
```
template <typename _Iterator>
auto when_all(
    _Iterator _Begin,
    _Iterator _End,
    const task_options& _TaskOptions = task_options()) -> 
    decltype (details::_WhenAllImpl<typename std::iterator_traits<_Iterator>::value_type::result_type,
    _Iterator>::_Perform(_TaskOptions, _Begin,  _End));
```   
  
### <a name="parameters"></a>Параметры  
 `_Iterator`  
 Тип итератора ввода.  
  
 `_Begin`  
 Позиция первого элемента в диапазоне элементов, которые будут объединены в результирующую задачу.  
  
 `_End`  
 Позиция первого элемента за пределами диапазона элементов, которые будут объединены в результирующую задачу.  
  
 `_TaskOptions`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Задача, которая завершается успешно, если все входные задачи завершены успешно. Если входные задачи относятся к типу `T`, выводом этой функции будет `task<std::vector<T>>`. Если входные задачи относятся к типу `void`, выходная задача также будет `task<void>`.  
  
### <a name="remarks"></a>Примечания  
 Функция `when_all` является функцией без блокировки, в качестве результата создающей `task`. В отличие от [task::wait](task-class.md#wait), безопасно для вызова этой функции в приложении UWP в потоке ASTA (STA приложения).  
  
 Если одна из задач отменяется или создает исключение, возвращенная задача завершится рано, в отмененном состоянии, и, если таковое встречено, возникнет исключение при вызове метода [task::get](task-class.md#get) или `task::wait` для этой задачи.  
  
 Дополнительные сведения см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
##  <a name="when_any"></a>  when_any  
 Создает задачу, которая завершается успешно, если любая из задач, предоставленных в качестве аргументов, завершается успешно.  
  
```
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
 `_Iterator`  
 Тип итератора ввода.  
  
 `_Begin`  
 Позиция первого элемента в диапазоне элементов, которые будут объединены в результирующую задачу.  
  
 `_End`  
 Позиция первого элемента за пределами диапазона элементов, которые будут объединены в результирующую задачу.  
  
 `_TaskOptions`  
 `_CancellationToken`  
 Токен отмены, который контролирует отмену возвращаемой задачи. Если токен отмены отсутствует, результирующая задача получит токен отмены, который используется для выполнения задачи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Задача, которая завершается успешно, если все входные задачи завершены успешно. Если входные задачи имеют тип `T`, выходными данными этой функции будут `task<std::pair<T, size_t>>>`, где первый элемент пары является результатом завершаемой задачи, а второй элемент — индексом завершенной задачи. Если входные задачи имеют тип `void`, выходными данными будет `task<size_t>`, где результат — индекс завершаемой задачи.  
  
### <a name="remarks"></a>Примечания  
 Функция `when_any` является функцией без блокировки, в качестве результата создающей `task`. В отличие от [task::wait](task-class.md#wait), безопасно для вызова этой функции в приложении UWP в потоке ASTA (STA приложения).  
  
 Дополнительные сведения см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
