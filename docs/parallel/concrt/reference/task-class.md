---
title: Класс Task (среда выполнения параллелизма) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- task class
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5887350d9ccdf6fc4a41d72ae8a70fa38d939390
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="task-class-concurrency-runtime"></a>Класс task (среда выполнения с параллелизмом)
Класс `task` библиотеки параллельных шаблонов (PPL). Объект `task` представляет работу, которая может быть выполнена асинхронно и параллельно с другими задачами и параллельной работой, созданной параллельными алгоритмами в среде выполнения с параллелизмом. При успешном завершении он выводи результат типа `_ResultType`. Задачи типа `task<void>` никакого результата не дают. Задачи можно ожидать и отменять независимо от других задач. Также возможно сочетание с другими задачами с помощью продолжений ( `then`) и соединение ( `when_all`) и выбора ( `when_any`) шаблонов.  
  
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
 `T`  
 `T`  
 `_ReturnType`  
 Результирующий тип задачи.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`result_type`|Тип результата, выводимого объектом этого класса.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[task](#ctor)|Перегружен. Создает объект `task`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[get](#get)|Перегружен. Возвращает результат, созданный этой задачей. Если задача не находится в конечном состоянии, вызов `get` будет ожидать завершения задачи. Этот метод не возвращает значение при вызове для задачи с параметром `result_type`, имеющим значение `void`.|  
|[is_apartment_aware](#is_apartment_aware)|Определяет, распаковывает ли задача интерфейс среды выполнения Windows `IAsyncInfo` или происходит от такой задачи.|  
|[is_done](#is_done)|Определяет, завершена ли задача.|  
|[scheduler](#scheduler)|Возвращает планировщик для этой задачи|  
|[затем](#then)|Перегружен. Добавляет задачу продолжения к этой задаче.|  
|[wait](#wait)|Ожидает, когда эта задача достигнет конечного состояния. У `wait` существует возможность выполнения задачи встроенным образом, если все зависимости задач удовлетворены, и она еще не взята для выполнения фоновым рабочим процессом.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор!=](#operator_neq)|Перегружен. Определяет, представляют ли два объекта `task` различные внутренние задачи.|  
|[оператор=](#operator_eq)|Перегружен. Заменяет содержимое одного объекта `task` другим.|  
|[оператор==](#operator_eq_eq)|Перегружен. Определяет, представляют ли два объекта `task` одну и ту же внутреннюю задачу.|  
  
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
>  В приложении универсальной платформы Windows (UWP), не следует вызывать [Concurrency::Task:: wait](#wait) или `get` ( `wait` вызовы `get`) в коде, выполняемом в STA. В противном случае среда выполнения создает [concurrency::invalid_operation](invalid-operation-class.md) , так как эти методы блокирует текущий поток и может вызвать зависание приложения. Тем не менее, можно вызвать `get` метод для получения результата из предшествующей задачи в продолжение на основе задач, поскольку результат имеет сразу становятся доступными.  
  
##  <a name="is_apartment_aware"></a> is_apartment_aware 

 Определяет, распаковывает ли задача интерфейс среды выполнения Windows `IAsyncInfo` или происходит от такой задачи.  
  
```
bool is_apartment_aware() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если задача распаковывает интерфейс `IAsyncInfo` или является потомком такой задачи, в противном случае — значение `false`.  
  
##  <a name="is_done"></a>  Метод Task::is_done (среда выполнения с параллелизмом)  
 Определяет, завершена ли задача.  
  
```
bool is_done() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение true, если задача была завершена, значение false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает значение true, если задача завершается или отменяется (с или без исключения пользователя).  
  
##  <a name="operator_neq"></a> оператор! = 

 Определяет, представляют ли два объекта `task` различные внутренние задачи.  
  
```
bool operator!= (const task<_ReturnType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Rhs`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если объекты ссылаются на разные базовые задачи, в противном случае — значение `false`.  
  
##  <a name="operator_eq"></a> оператор = 

 Заменяет содержимое одного объекта `task` другим.  
  
```
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
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
 `_Rhs`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если объекты ссылаются на одну и ту же базовую задачу, в противном случае — значение `false`.  
  
##  <a name="scheduler"></a>  Метод Task::Scheduler (среда выполнения с параллелизмом)  
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
 `T`  
 Тип параметра, из которого будет создаваться задача.  
  
 `_Param`  
 Параметр, из которого будет создаваться задача. Это может быть лямбда-выражение, объект функции `task_completion_event<result_type>` объекта или Windows::Foundation:: iasyncinfo, если задачи используются в приложении среды выполнения Windows. Лямбда-выражения или объекта функции должно быть к типу, эквивалентному `std::function<X(void)>`, где X может быть переменная типа `result_type`, `task<result_type>`, или Windows::Foundation:: iasyncinfo в приложениях среды выполнения Windows.  
  
 `_TaskOptions`  
 Параметры задачи включают токен отмены, планировщик и др.  
  
 `_Other`  
 Исходный объект `task`.  
  
### <a name="remarks"></a>Примечания  
 Конструктор по умолчанию для `task` присутствует только для того, чтобы задачи могли использоваться внутри контейнеров. Собранную задачу по умолчанию невозможно использовать до тех пор, пока ей не будет присвоена допустимая задача. Такие методы, как `get`, `wait` или `then` вызовет [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение при вызове для собранной задачи по умолчанию.  
  
 Задача, которая создается из `task_completion_event`, завершится (и ее продолжения будут запланированы), если событие завершения задачи установлено.  
  
 Версия конструктора, принимающего токен отмены, создает задачу, которую можно отменить с помощью `cancellation_token_source`, из которого был получен токен. Задачи, созданные без токена отмены, не могут быть отменены.  
  
 Задачи, созданные из интерфейса `Windows::Foundation::IAsyncInfo` или лямбда-выражения, которое возвращает интерфейс `IAsyncInfo`, достигают своего конечного состояния при завершении вложенной асинхронной операции или действия среды выполнения Windows. Аналогично, задачи, созданные из лямбда-выражения, которое возвращает `task<result_type>`, достигают своего конечного состояния, когда внутренняя задача достигает своего конечного состояние, а не когда лямбда-выражение выполняет возврат.  
  
 `task` ведет себя подобно интеллектуальному указателю, и ее можно безопасно передавать по значению. К ней также может быть получен доступ несколькими потоками без необходимости использования блокировки.  
  
 Перегрузки конструктора, которые принимают интерфейс Windows::Foundation:: iasyncinfo или лямбда-выражение возвращает такой интерфейс, доступны только для приложений среды выполнения Windows.  
  
 Дополнительные сведения см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
##  <a name="then"></a> затем 

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
 `_Function`  
 Тип объекта функции, который будет вызываться этой задачей.  
  
 `_Func`  
 Функция продолжения, которая должна быть выполнена по завершении этой задачи. Эта функция продолжения должна принимать в качестве входных данных переменную типа `result_type` или `task<result_type>`, где `result_type` — тип результата, который создает эта задача.  
  
 `_TaskOptions`  
 Параметры задачи включают токен отмены, планировщик и контекст продолжения. По умолчанию предыдущие 3 параметра наследуются от предшествующей задачи  
  
 `_CancellationToken`  
 Токен отмены, который необходимо связать с задачей продолжения. Задача продолжения, созданная без токена отмены, унаследует токен своей предшествующей задачи.  
  
 `_ContinuationContext`  
 Переменная, указывающая, где должно выполняться продолжение. Эта переменная полезен только при использовании в приложении UWP. Дополнительные сведения см. в разделе [task_continuation_context](task-continuation-context-class.md)  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вновь созданная задача продолжения. Тип результата возвращаемой задачи определяется значением, возвращаемым `_Func`.  
  
### <a name="remarks"></a>Примечания  
 Перегруженные версии `then` , которые принимают лямбда-выражение или функтор, которые возвращают интерфейс Windows::Foundation:: iasyncinfo, доступны только для приложений среды выполнения Windows.  
  
 Дополнительные сведения о том, как использовать для создания асинхронной работы продолжений задач см. в разделе [параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
##  <a name="wait"></a> Ожидание 

 Ожидает, когда эта задача достигнет конечного состояния. У `wait` существует возможность выполнения задачи встроенным образом, если все зависимости задач удовлетворены, и она еще не взята для выполнения фоновым рабочим процессом.  
  
```
task_status wait() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `task_status`, которое может быть `completed` или `canceled`. Если задача встретила исключение во время выполнения или исключение было распространено на нее из предшествующей задачи, `wait` вызывает это исключение.  
  
### <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
>  В приложении универсальной платформы Windows (UWP), не следует вызывать `wait` в коде, выполняемом в STA. В противном случае среда выполнения создает [concurrency::invalid_operation](invalid-operation-class.md) , так как этот метод блокирует текущий поток и может вызвать зависание приложения. Тем не менее, можно вызвать [Concurrency::Task:: Get](#get) метод для получения результата из предшествующей задачи в продолжение на основе задач.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
