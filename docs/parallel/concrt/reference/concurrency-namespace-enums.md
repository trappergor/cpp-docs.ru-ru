---
title: "перечисления имен параллелизма | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a40e3b2d-ad21-4229-9880-2cfa84f7ab8f
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 8f7488ff07c9789e2d5f35056de390a5bc464f56
ms.openlocfilehash: ff187e827b2dd979466b746eee297235e6a6c0ca
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-enums"></a>перечисления имен параллелизма
||||  
|-|-|-|  
|[Перечисление Agents_EventType](#agents_eventtype)|[Перечисление ConcRT_EventType](#concrt_eventtype)|[Перечисление Concrt_TraceFlags](#concrt_traceflags)|  
|[Перечисление CriticalRegionType](#criticalregiontype)|[Перечисление DynamicProgressFeedbackType](#dynamicprogressfeedbacktype)|[Перечисление PolicyElementKey](#policyelementkey)|  
|[Перечисление SchedulerType](#schedulertype)|[Перечисление SchedulingProtocolType](#schedulingprotocoltype)|[Перечисление SwitchingProxyState](#switchingproxystate)|  
|[Перечисление WinRTInitializationType](#winrtinitializationtype)|[Перечисление agent_status](#agent_status)|[Перечисление join_type](#join_type)|  
|[Перечисление message_status](#message_status)|[Перечисление task_group_status](#task_group_status)|  
  
##  <a name="a-nameagentstatusa--agentstatus-enumeration"></a><a name="agent_status"></a>Перечисление agent_status  
 Допустимые состояния для объекта `agent`.  
  
```
enum agent_status;
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`agent_canceled`|Объект `agent` отменен.|  
|`agent_created`|`agent` Был создан, но не запущена.|  
|`agent_done`|`agent` Завершился без отмены.|  
|`agent_runnable`|`agent` Работы, но не введен его `run` метод.|  
|`agent_started`|`agent` Запущена.|  

### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [асинхронных агентов](../../../parallel/concrt/asynchronous-agents.md).  

### <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h

##  <a name="a-nameagentseventtypea--agentseventtype-enumeration"></a><a name="agents_eventtype"></a>Перечисление Agents_EventType  
 Типы событий, которые можно отслеживать с помощью функции трассировки, предоставляемой библиотекой агентов.  
  
```
enum Agents_EventType;
```  

### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`AGENTS_EVENT_CREATE`|Тип события, который представляет создание объекта|  
|`AGENTS_EVENT_DESTROY`|Тип события, который представляет удаление объекта|  
|`AGENTS_EVENT_END`|Тип события, который представляет завершение некоторой обработки|  
|`AGENTS_EVENT_LINK`|Тип события, который представляет связывание блоков сообщений|  
|`AGENTS_EVENT_NAME`|Тип события, который представляет имя для объекта|  
|`AGENTS_EVENT_SCHEDULE`|Тип события, который представляет расписание процесса|  
|`AGENTS_EVENT_START`|Тип события, который представляет запуск некоторой обработки|  
|`AGENTS_EVENT_UNLINK`|Тип события, который представляет отвязку блоков сообщений|  

### <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h

##  <a name="a-nameconcrteventtypea--concrteventtype-enumeration"></a><a name="concrt_eventtype"></a>Перечисление ConcRT_EventType  
 Типы событий, которые можно отслеживать с помощью функций трассировки, обеспечиваемых средой выполнения с параллелизмом.  
  
```
enum ConcRT_EventType;
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`CONCRT_EVENT_ATTACH`|Тип событий, который представляет акт присоединение к планировщику.|  
|`CONCRT_EVENT_BLOCK`|Тип события, который представляет акт блокировки контекста.|  
|`CONCRT_EVENT_DETACH`|Тип событий, который представляет акт отсоединения от планировщика.|  
|`CONCRT_EVENT_END`|Тип события, отмечающий начало пары событий начала и окончания.|  
|`CONCRT_EVENT_GENERIC`|Тип события, используемые для различных событий.|  
|`CONCRT_EVENT_IDLE`|Тип события, который представляет акт неактивное контекста.|  
|`CONCRT_EVENT_START`|Тип события, отмечающий начало пары событий начала и окончания.|  
|`CONCRT_EVENT_UNBLOCK`|Тип события, который представляет акт разблокирования контекста.|  
|`CONCRT_EVENT_YIELD`|Тип события, который представляет акт выдачи контекста.|  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h

##  <a name="a-nameconcrttraceflagsa--concrttraceflags-enumeration"></a><a name="concrt_traceflags"></a>Перечисление Concrt_TraceFlags  
 Флажки трассировки для типов событий  
  
```
enum Concrt_TraceFlags;
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`AgentEventFlag`||  
|`AllEventsFlag`||  
|`ContextEventFlag`||  
|`PPLEventFlag`||  
|`ResourceManagerEventFlag`||  
|`SchedulerEventFlag`||  
|`VirtualProcessorEventFlag`||

### <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h

##  <a name="a-namecriticalregiontypea--criticalregiontype-enumeration"></a><a name="criticalregiontype"></a>Перечисление CriticalRegionType  
 Тип критической области, внутри которой находится контекст.  
  
```
enum CriticalRegionType;
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`InsideCriticalRegion`|Указывает, что контекст внутри критической области. Внутри критической области, асинхронные приостановки скрыты от планировщика. Если такая приостановка произошло, диспетчер ресурсов будет ожидать к запуску и просто возобновит его, вместо повторного вызова планировщика потока. Все блокировки, сделанные внутри такой области следует с особой осторожностью.|  
|`InsideHyperCriticalRegion`|Указывает, что контекст внутри hyper критической области. При нахождении hyper критической области, синхронные и асинхронные приостановки скрыты от планировщика. Такая приостановка или блокировка происходит, диспетчер ресурсов будет ожидать к запуску и просто возобновит его, вместо повторного вызова планировщика потока. Блокировки, сделанные внутри такой области никогда не должен использоваться совместно с код, выполняемый вне такие области. Это приведет к непредсказуемым взаимоблокировки.|  
|`OutsideCriticalRegion`|Указывает, что контекст вне любой критической области.|  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h 

##  <a name="a-namedynamicprogressfeedbacktypea--dynamicprogressfeedbacktype-enumeration"></a><a name="dynamicprogressfeedbacktype"></a>Перечисление DynamicProgressFeedbackType  
 Используется политикой `DynamicProgressFeedback` для описания того, будет ли к ресурсам планировщика применена повторная балансировка в соответствии со статистическими данными, полученными из планировщика, или только на основе перехода виртуальных процессоров в состояние бездействия и из него через вызовы методов `Activate` и `Deactivate` для интерфейса `IVirtualProcessorRoot`. Дополнительные сведения о доступных политиках планировщиков см. в разделе [перечисление PolicyElementKey](concurrency-namespace-enums.md).  
  
```
enum DynamicProgressFeedbackType;
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`ProgressFeedbackDisabled`|Планировщик не выполняет сбор сведений о ходе выполнения. Перераспределения выполняется на основе исключительно на уровень подписки базовой аппаратный поток. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](IExecutionResource-structure.md).<br /><br /> Это значение зарезервировано для использования средой выполнения.|  
|`ProgressFeedbackEnabled`|Планировщик собирает сведения о ходе выполнения и передает ее в диспетчер ресурсов. Диспетчер ресурсов будет использовать эти статистические данные для балансирования ресурсов от имени планировщика в дополнение к уровень подписки базовой аппаратный поток. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](IExecutionResource-structure.md).|  
##  <a name="a-namejointypea--jointype-enumeration"></a><a name="join_type"></a>Перечисление join_type  
 Тип блока обмена сообщениями `join`.  
  
```
enum join_type;
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`greedy`|Жадное `join` блоков обмена сообщениями немедленно принимают сообщение после распространения. Это более эффективно, но имеет возможность live блокировки, в зависимости от конфигурации сети.|  
|`non_greedy`|Нежадный `join` блоков обмена сообщениями отложенных сообщений и попытайтесь и использовать их, когда все поступили. Они гарантированно работать, но медленнее.|  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  

##  <a name="a-namemessagestatusa--messagestatus-enumeration"></a><a name="message_status"></a>Перечисление message_status  
 Допустимые ответы на предложение объекта `message` блоку.  
  
```
enum message_status;
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`accepted`|Целевой объект принял сообщение.|  
|`declined`|Целевой объект не принял сообщение.|  
|`missed`|Целевой объект попытался принять сообщение, но больше не были доступны.|  
|`postponed`|Целевой объект отложил сообщение.|  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  

##  <a name="a-namepolicyelementkeya--policyelementkey-enumeration"></a><a name="policyelementkey"></a>Перечисление PolicyElementKey  
 Ключи политики, описывающие аспекты поведения планировщика. Каждый элемент политики описан с помощью пары «ключ — значение». Дополнительные сведения о политиках планировщика и их влияние на планировщики см. в разделе [планировщик](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
```
enum PolicyElementKey;
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`ContextPriority`|Приоритет потоков операционной системы каждого контекста в планировщике. Если этот ключ присвоено значение `INHERIT_THREAD_PRIORITY` контексты в планировщике наследуют приоритет потока, который создал планировщик.<br /><br /> Допустимые значения: любые допустимые значения для Windows `SetThreadPriority` функции и специальные значения`INHERIT_THREAD_PRIORITY`<br /><br /> Значение по умолчанию:`THREAD_PRIORITY_NORMAL`|  
|`ContextStackSize`|Размер зарезервированного стека для каждого контекста в планировщике в килобайтах.<br /><br /> Допустимые значения: положительные целые числа<br /><br /> Значение по умолчанию: `0`, указывающее, что использовать процесса по умолчанию размер стека.|  
|`DynamicProgressFeedback`|Определяет, будет ли быть сбалансировано ресурсы для планировщика согласно статистическим сведениям, собранным из планировщика или только на основании уровня подписки базовых аппаратных потоков. Дополнительные сведения см. в разделе [перечисление DynamicProgressFeedbackType](#dynamicprogressfeedbacktype).<br /><br /> Допустимые значения: член `DynamicProgressFeedbackType` перечисления, либо `ProgressFeedbackEnabled` или`ProgressFeedbackDisabled`<br /><br /> Значение по умолчанию:`ProgressFeedbackEnabled`|  
|`LocalContextCacheSize`|При `SchedulingProtocol` ключ политики установлено значение `EnhanceScheduleGroupLocality`, указывает максимальное количество работоспособным контекстам, которые разрешено кэшировать в каждого виртуального процессора локальные очереди. Таких контекстов обычно выполняется в порядке виртуального процессора, которая привела к запуску последним в первым обслужен (LIFO). Обратите внимание, что данный параметр политики не то, когда `SchedulingProtocol` ключа задано значение `EnhanceForwardProgress`.<br /><br /> Допустимые значения: неотрицательные целые числа<br /><br /> Значение по умолчанию:`8`|  
|`MaxConcurrency`|Максимальный уровень параллелизма, необходимый планировщику. Диспетчер ресурсов будет пытаться изначально выделить это количество виртуальных процессоров. Особое значение [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) указывает, что нужный уровень параллельности совпадает с числом аппаратных потоков на компьютере. Если значение, указанное для `MinConcurrency` больше, чем количество аппаратных потоков на компьютере и `MaxConcurrency` указан как `MaxExecutionResources`, значение `MaxConcurrency` вызывается для сопоставления, что задано для `MinConcurrency`.<br /><br /> Допустимые значения: положительные целые числа и специальные значения`MaxExecutionResources`<br /><br /> Значение по умолчанию:`MaxExecutionResources`|  
|`MaxPolicyElementKey`|Максимальный ключ элемента политики. Не допустимый ключ элемента.|  
|`MinConcurrency`|Минимальный уровень параллелизма, которые предоставляются диспетчером ресурсов планировщику. Число виртуальных процессоров, назначенных планировщику никогда не перейдет ниже минимума. Особое значение [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) указывает, что минимальный уровень параллелизма совпадает с числом аппаратных потоков на компьютере. Если значение, указанное для `MaxConcurrency` меньше, чем количество аппаратных потоков на компьютере и `MinConcurrency` указан как `MaxExecutionResources`, значение `MinConcurrency` уменьшается для сопоставления, что задано для `MaxConcurrency`.<br /><br /> Допустимые значения: неотрицательные целые числа и специальные значения `MaxExecutionResources`. Обратите внимание, что для политик планировщика, используемых для создания планировщиков исполняющей среды с параллелизмом, значение `0` недопустимо.<br /><br /> Значение по умолчанию:`1`|  
|`SchedulerKind`|Тип потоков, которые будет использовать планировщик для базовых контекстов выполнения. Дополнительные сведения см. в разделе [перечисление SchedulerType](#schedulertype).<br /><br /> Допустимые значения: элемент перечисления `SchedulerType`, например `ThreadScheduler`<br /><br /> Значение по умолчанию: `ThreadScheduler`. Это преобразует в Win32 потоки во всех операционных системах.|  
|`SchedulingProtocol`|Описывает, какой алгоритм планирования будет использоваться планировщиком. Дополнительные сведения см. в разделе [перечисление SchedulingProtocolType](#schedulingprotocoltype).<br /><br /> Допустимые значения: член `SchedulingProtocolType` перечисления, либо `EnhanceScheduleGroupLocality` или`EnhanceForwardProgress`<br /><br /> Значение по умолчанию:`EnhanceScheduleGroupLocality`|  
|`TargetOversubscriptionFactor`|Пробный число виртуальных процессоров на аппаратный поток. Коэффициент переподписки целевого объекта при необходимости может быть увеличен диспетчером ресурсов для обеспечения `MaxConcurrency` аппаратными потоками на компьютере.<br /><br /> Допустимые значения: положительные целые числа<br /><br /> Значение по умолчанию:`1`|  
|`WinRTInitialization`||  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  

##  <a name="a-nameschedulertypea--schedulertype-enumeration"></a><a name="schedulertype"></a>Перечисление SchedulerType  
 Используется политикой `SchedulerKind` для описания типа потоков, которые должен использовать планировщик для базовых контекстов выполнения. Дополнительные сведения о доступных политиках планировщиков см. в разделе [перечисление PolicyElementKey](concurrency-namespace-enums.md).  
  
```
enum SchedulerType;
``` 

### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`ThreadScheduler`|Указывает явного запроса регулярных потоков Win32.|  
|`UmsThreadDefault`|Планируемые потоки в режиме пользователя (UMS) не поддерживаются в среде выполнения с параллелизмом в Visual Studio 2013. Использование `UmsThreadDefault` в качестве значения для политики `SchedulerType` не приведет к ошибке. Однако, планировщик, созданный с помощью этой политики, по умолчанию будет настроен на использование потоков Win32.|  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
##  <a name="a-nameschedulingprotocoltypea--schedulingprotocoltype-enumeration"></a><a name="schedulingprotocoltype"></a>Перечисление SchedulingProtocolType  
 Используется политикой `SchedulingProtocol` для описания того, какой алгоритм планирования будет использоваться для планировщика. Дополнительные сведения о доступных политиках планировщиков см. в разделе [перечисление PolicyElementKey](concurrency-namespace-enums.md).  
  
```
enum SchedulingProtocolType;
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`EnhanceForwardProgress`|Планировщик предпочитает циклический перебор по группам расписаний после выполнения каждой задачи. Разблокированные контексты обычно планируются образом первым в первым обслужен (FIFO). Виртуальные процессоры не кэшируют разблокированные контексты.|  
|`EnhanceScheduleGroupLocality`|Планировщик предпочитает продолжать работать над задачами в пределах текущей группы расписаний перед перемещением в другую группу расписания. Разблокированные контексты кэшируются на виртуальный процессор и обычно планируются образом последним в первым обслужен (LIFO) виртуальным процессором, который их разблокировал.|  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
 
##  <a name="a-nameswitchingproxystatea--switchingproxystate-enumeration"></a><a name="switchingproxystate"></a>Перечисление SwitchingProxyState  
 Используется для обозначения состояния прокси-потока, когда он выполняет совместное переключение контекста на другой прокси-поток.  
  
```
enum SwitchingProxyState;
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`Blocking`|Указывает, что вызывающий поток блокируется совместно и должны исключительно принадлежать вызывающим до повторного запуска впоследствии и выполнения других действий.|  
|`Idle`|Указывает, что вызывающий поток больше не нужен планировщику и возвращается к диспетчеру ресурсов. Контекст, который был отправлен больше не может использоваться диспетчером ресурсов.|  
|`Nesting`|Указывает, что вызывающий поток вложен дочерний планировщик и необходимости вызывающим объектом, чтобы присоединить к другому планировщику.|  

### <a name="remarks"></a>Примечания  
 Тип параметра `SwitchingProxyState` передается в метод `IThreadProxy::SwitchTo` для указания того, как обрабатывать прокси-поток, который выполняет вызов диспетчера ресурсов.  
  
 Дополнительные сведения об использовании этого типа см. в разделе [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto).  
  
##  <a name="a-nametaskgroupstatusa--taskgroupstatus-enumeration"></a><a name="task_group_status"></a>Перечисление task_group_status  
 Описывает состояние выполнения объекта `task_group` или `structured_task_group`. Значение этого типа возвращается многочисленными методами, которые ожидают выполнения задач, запланированных для завершения группой задач.  
  
```
enum task_group_status;
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`canceled`|Объект `task_group` или `structured_task_group` отменен. Одна или несколько задач, возможно, не были выполнены.|  
|`completed`|Задачи, поставленные в очередь объекта `task_group` или `structured_task_group`, завершены успешно.|  
|`not_complete`|Задачи, поставленные в очередь объекта `task_group`, не завершены. Обратите внимание, что это значение в настоящее время не возвращается исполняющей средой с параллелизмом.|  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** pplinterface.h  

##  <a name="a-namewinrtinitializationtypea--winrtinitializationtype-enumeration"></a><a name="winrtinitializationtype"></a>Перечисление WinRTInitializationType  
 Используется политикой `WinRTInitialization` для описания того, будет ли среда выполнения Windows инициализирована в потоках планировщика для приложения, которое работает в операционных системах Windows с версии 8 или выше, и каким образом это будет выполняться. Дополнительные сведения о доступных политиках планировщиков см. в разделе [перечисление PolicyElementKey](concurrency-namespace-enums.md).  
  
```
enum WinRTInitializationType;
```  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`DoNotInitializeWinRT`|Когда приложение выполняется в операционной системе Windows версии 8 и выше, потоки в планировщике не инициализируют среду выполнения Windows.|  
|`InitializeWinRTAsMTA`|Когда приложение выполняется в операционной системе Windows версии 8 или выше, каждый поток в планировщике инициализирует среду выполнения Windows и объявляет, что это часть многопотокового подразделения.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  

## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

