---
title: Перечисления пространства имен concurrency
ms.date: 11/04/2016
f1_keywords:
- CONCRT/concurrency::Agents_EventType
- CONCRT/concurrency::Concrt_TraceFlags
- CONCRT/concurrency::CriticalRegionType
- CONCRT/concurrency::PolicyElementKey
- CONCRT/concurrency::SchedulerType
- CONCRT/concurrency::SwitchingProxyState
- CONCRT/concurrency::WinRTInitializationType
- CONCRT/concurrency::join_type
- CONCRT/concurrency::message_status Enumeration
ms.assetid: a40e3b2d-ad21-4229-9880-2cfa84f7ab8f
ms.openlocfilehash: e3a943ed52ce9653086203713bb98331f809314d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372724"
---
# <a name="concurrency-namespace-enums"></a>Перечисления пространства имен concurrency

||||
|-|-|-|
|[Agents_EventType](#agents_eventtype)|[ConcRT_EventType](#concrt_eventtype)|[Concrt_TraceFlags](#concrt_traceflags)|
|[КритическийРегионТип](#criticalregiontype)|[DynamicProgressОбратнаяТип](#dynamicprogressfeedbacktype)|[PolicyElementKey](#policyelementkey)|
|[РасписаниеТип](#schedulertype)|[ПланированиеПротоколТип](#schedulingprotocoltype)|[ПереключениеПроксигосударство](#switchingproxystate)|
|[WinRTПервоначальнизацияType](#winrtinitializationtype)|[agent_status](#agent_status)|[join_type](#join_type)|
|[message_status](#message_status)|[task_group_status](#task_group_status)|

## <a name="agent_status-enumeration"></a><a name="agent_status"></a>agent_status Иномерация

Допустимые состояния для объекта `agent`.

```cpp
enum agent_status;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`agent_canceled`|Объект `agent` отменен.|
|`agent_created`|Создано, `agent` но не запущено.|
|`agent_done`|Закончено `agent` без отмены.|
|`agent_runnable`|Запущен, `agent` но не введен `run` в свой метод.|
|`agent_started`|Начато. `agent`|

### <a name="remarks"></a>Remarks

Для получения дополнительной информации, [см.](../../../parallel/concrt/asynchronous-agents.md)

### <a name="requirements"></a>Требования

**Заголовок:** concrt.h

## <a name="agents_eventtype-enumeration"></a><a name="agents_eventtype"></a>Agents_EventType Инумерация

Типы событий, которые можно отслеживать с помощью функции трассировки, предоставляемой библиотекой агентов.

```cpp
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

## <a name="concrt_eventtype-enumeration"></a><a name="concrt_eventtype"></a>ConcRT_EventType Инумерация

Типы событий, которые можно отслеживать с помощью функций трассировки, обеспечиваемых средой выполнения с параллелизмом.

```cpp
enum ConcRT_EventType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`CONCRT_EVENT_ATTACH`|Тип события, представляющий акт присоединения к планировщику.|
|`CONCRT_EVENT_BLOCK`|Тип события, представляющий акт блокировки контекста.|
|`CONCRT_EVENT_DETACH`|Тип события, представляющий акт отсоединения от планировщика.|
|`CONCRT_EVENT_END`|Тип события, знаменующие начало пары событий начала/конца.|
|`CONCRT_EVENT_GENERIC`|Тип события, используемый для различных событий.|
|`CONCRT_EVENT_IDLE`|Тип события, представляющий акт действия контекста, просаиваемый.|
|`CONCRT_EVENT_START`|Тип события, знаменующие начало пары событий начала/конца.|
|`CONCRT_EVENT_UNBLOCK`|Тип события, представляющий акт разблокировки контекста.|
|`CONCRT_EVENT_YIELD`|Тип события, представляющий акт доходности контекста.|

### <a name="requirements"></a>Требования

**Заголовок:** concrt.h **Namespace:** параллелизм

## <a name="concrt_traceflags-enumeration"></a><a name="concrt_traceflags"></a>Concrt_TraceFlags Ичисление

Флажки трассировки для типов событий

```cpp
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

## <a name="criticalregiontype-enumeration"></a><a name="criticalregiontype"></a>Значение criticalRegionType

Тип критической области, внутри которой находится контекст.

```cpp
enum CriticalRegionType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`InsideCriticalRegion`|Означает, что контекст находится внутри критической области. При нахуе внутри критической области асинхронные суспензии скрыты от планировщика. Если такая приостановка произойдет, менеджер ресурсов будет ждать, пока поток станет запущенным, и просто возобновит его вместо того, чтобы снова ссылаться на планировщика. Любые замки, взятые в таком регионе, должны приниматься с особой осторожностью.|
|`InsideHyperCriticalRegion`|Означает, что контекст находится внутри гиперкритической области. Находясь внутри гиперкритической области, как синхронные, так и асинхронные суспензии скрыты от планировщика. Если такая приостановка или блокировка произойдет, менеджер ресурсов будет ждать, пока поток станет запущенным, и просто возобновит его вместо того, чтобы снова ссылаться на планировщика. Блокировки, сделанные внутри такого региона, никогда не должны быть разделены с кодом, запущенным за пределами такого региона. Это приведет к непредсказуемому тупику.|
|`OutsideCriticalRegion`|Означает, что контекст находится за пределами любого критического региона.|

### <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

## <a name="dynamicprogressfeedbacktype-enumeration"></a><a name="dynamicprogressfeedbacktype"></a>ДинамикаОбратнТип Enumeration

Используется политикой `DynamicProgressFeedback` для описания того, будет ли к ресурсам планировщика применена повторная балансировка в соответствии со статистическими данными, полученными из планировщика, или только на основе перехода виртуальных процессоров в состояние бездействия и из него через вызовы методов `Activate` и `Deactivate` для интерфейса `IVirtualProcessorRoot`. Для получения дополнительной информации о [PolicyElementKey](concurrency-namespace-enums.md)доступных политиках планировщика см.

```cpp
enum DynamicProgressFeedbackType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`ProgressFeedbackDisabled`|Планировщик не собирает информацию о ходе работы. Ребалансировка осуществляется исключительно на основе уровня подписки базового аппаратного потока. Для получения дополнительной информации об уровнях подписки см. [IExecutionResource::CurrentSubscriptionLevel](IExecutionResource-structure.md).<br /><br /> Это значение зарезервировано для использования временвыполнения.|
|`ProgressFeedbackEnabled`|Планировщик собирает информацию о ходе и передает ее менеджеру ресурсов. Менеджер ресурсов будет использовать эту статистическую информацию для ребалансировки ресурсов от имени планировщика в дополнение к уровню подписки базового аппаратного потока. Для получения дополнительной информации об уровнях подписки см. [IExecutionResource::CurrentSubscriptionLevel](IExecutionResource-structure.md).|

## <a name="join_type-enumeration"></a><a name="join_type"></a>join_type Ичисление

Тип блока обмена сообщениями `join`.

```cpp
enum join_type;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`greedy`|Блоки `join` обмена сообщениями немедленно принимают сообщение при распространении. Это более эффективно, но имеет возможность для живой блокировки, в зависимости от конфигурации сети.|
|`non_greedy`|Нежадные `join` блоки обмена сообщениями откладывают сообщения и пытаются потреблять их после того, как все они прибыли. Они гарантированно работают, но медленнее.|

### <a name="requirements"></a>Требования

**Заголовок:** agents.h

## <a name="message_status-enumeration"></a><a name="message_status"></a>message_status Ичисление

Допустимые ответы на предложение объекта `message` блоку.

```cpp
enum message_status;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`accepted`|Цель приняла сообщение.|
|`declined`|Цель не приняла сообщение.|
|`missed`|Цель попыталась принять сообщение, но оно было недоступно.|
|`postponed`|Цель отложила сообщение.|

### <a name="requirements"></a>Требования

**Заголовок:** agents.h

## <a name="policyelementkey-enumeration"></a><a name="policyelementkey"></a>Число PolicyElementKey

Ключи политики, описывающие аспекты поведения планировщика. Каждый элемент политики описан с помощью пары «ключ — значение». Для получения дополнительной информации о политиках планировщика [Task Scheduler](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)и их влиянии на планировщики см.

```cpp
enum PolicyElementKey;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`ContextPriority`|Приоритет потока операционной системы каждого контекста в планировщике. Если этот ключ установлен `INHERIT_THREAD_PRIORITY` в значении, то контексты в планировщике унаследуют приоритет потока, создавого планировщика.<br /><br /> Допустимые значения : Любое из `SetThreadPriority` допустимых значений для функции Windows и специальное значение`INHERIT_THREAD_PRIORITY`<br /><br /> Значение по умолчанию:`THREAD_PRIORITY_NORMAL`|
|`ContextStackSize`|Зарезервированный размер стека каждого контекста в планировщике в килобайтах.<br /><br /> Действительные значения : Положительные многомеры<br /><br /> Значение по `0`умолчанию : указывает на то, что значение по умолчанию процесса для размера стека будет использоваться.|
|`DynamicProgressFeedback`|Определяет, будут ли ресурсы для планировщика сбалансированы в соответствии со статистической информацией, собранной от планировщика, или только на основе уровня подписки базовых аппаратных потоков. Для получения дополнительной информации, [см.](#dynamicprogressfeedbacktype)<br /><br /> Допустимые значения : `DynamicProgressFeedbackType` Член перечисления, `ProgressFeedbackEnabled` либо`ProgressFeedbackDisabled`<br /><br /> Значение по умолчанию:`ProgressFeedbackEnabled`|
|`LocalContextCacheSize`|При `SchedulingProtocol` установке ключа политики `EnhanceScheduleGroupLocality`на значение определяется максимальное количество запущенных контекстов, разрешенных к консилификанию в локальных очередях виртуального процессора. Такие контексты, как правило, работают в порядке последнего выхода (LIFO) на виртуальном процессоре, что привело к тому, что они стали управляемыми. Обратите внимание, что этот ключ `SchedulingProtocol` политики не `EnhanceForwardProgress`имеет смысла, когда ключ установлен на значение.<br /><br /> Допустимые значения : Неотрицательные несколько часов<br /><br /> Значение по умолчанию:`8`|
|`MaxConcurrency`|Максимальный уровень параллелизма, желаемый планировщиком. Менеджер ресурсов попытается изначально выделить такое множество виртуальных процессоров. Специальное значение [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) указывает на то, что желаемый уровень параллелизма такой же, как и количество аппаратных потоков на машине. Если `MinConcurrency` указанное значение превышает количество аппаратных потоков на `MaxConcurrency` машине `MaxExecutionResources`и указывается `MaxConcurrency` как, значение поднимается `MinConcurrency`в соответствии с тем, для которого установлено.<br /><br /> Действительные значения : Положительные tetegers и специальное значение`MaxExecutionResources`<br /><br /> Значение по умолчанию:`MaxExecutionResources`|
|`MaxPolicyElementKey`|Максимальный ключ элемента политики. Не является действительным ключом элемента.|
|`MinConcurrency`|Минимальный уровень параллелизма, который должен быть предоставлен планировщику менеджером ресурсов. Количество виртуальных процессоров, назначенных планировщику, никогда не будет ниже минимума. Специальное значение [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) указывает на то, что минимальный уровень параллелизма такой же, как и количество аппаратных потоков на машине. Если `MaxConcurrency` указанное значение меньше количества аппаратных потоков на `MinConcurrency` машине `MaxExecutionResources`и указывается `MinConcurrency` как, значение для понижено, чтобы соответствовать тому, для которого `MaxConcurrency`установлено.<br /><br /> Действительные значения : Неотрицательные несколько чихов и специальное значение. `MaxExecutionResources` Обратите внимание, что для политик планировщика, используемых для создания планировщиков исполняющей среды с параллелизмом, значение `0` недопустимо.<br /><br /> Значение по умолчанию:`1`|
|`SchedulerKind`|Тип потоков, которые планировщик будет использовать для базовых контекстов выполнения. Для получения дополнительной информации [см.](#schedulertype)<br /><br /> Допустимые значения: элемент перечисления `SchedulerType`, например `ThreadScheduler`<br /><br /> Значение по `ThreadScheduler`умолчанию : . Это переводится как потоки Win32 на всех операционных системах.|
|`SchedulingProtocol`|Описывает, какой алгоритм планирования будет использоваться планировщиком. Для получения дополнительной информации [см.](#schedulingprotocoltype)<br /><br /> Допустимые значения : `SchedulingProtocolType` Член перечисления, `EnhanceScheduleGroupLocality` либо`EnhanceForwardProgress`<br /><br /> Значение по умолчанию:`EnhanceScheduleGroupLocality`|
|`TargetOversubscriptionFactor`|Предварительное количество виртуальных процессоров на аппаратный поток. Коэффициент переподписки целевого объекта при необходимости может быть увеличен диспетчером ресурсов для обеспечения `MaxConcurrency` аппаратными потоками на компьютере.<br /><br /> Действительные значения : Положительные многомеры<br /><br /> Значение по умолчанию:`1`|
|`WinRTInitialization`||

### <a name="requirements"></a>Требования

**Заголовок:** concrt.h

## <a name="schedulertype-enumeration"></a><a name="schedulertype"></a>РасписаниеТип Ичисление

Используется политикой `SchedulerKind` для описания типа потоков, которые должен использовать планировщик для базовых контекстов выполнения. Для получения дополнительной информации о [PolicyElementKey](concurrency-namespace-enums.md)доступных политиках планировщика см.

```cpp
enum SchedulerType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`ThreadScheduler`|Указывает явный запрос регулярных потоков Win32.|
|`UmsThreadDefault`|Потоки для schedulable (UMS) режима пользователя не поддерживаются в Concurrency Runtime в Visual Studio 2013. Использование `UmsThreadDefault` в качестве значения для политики `SchedulerType` не приведет к ошибке. Однако, планировщик, созданный с помощью этой политики, по умолчанию будет настроен на использование потоков Win32.|

### <a name="requirements"></a>Требования

**Заголовок:** concrt.h

## <a name="schedulingprotocoltype-enumeration"></a><a name="schedulingprotocoltype"></a>ПланированиеПротоколТип Enumeration

Используется политикой `SchedulingProtocol` для описания того, какой алгоритм планирования будет использоваться для планировщика. Для получения дополнительной информации о [PolicyElementKey](concurrency-namespace-enums.md)доступных политиках планировщика см.

```cpp
enum SchedulingProtocolType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`EnhanceForwardProgress`|Планировщик предпочитает круговой круг опоры через группы графиков после выполнения каждой задачи. Разблокированные контексты, как правило, планируются в порядке первого выхода (FIFO). Виртуальные процессоры не кэшируют разблокированные контексты.|
|`EnhanceScheduleGroupLocality`|Планировщик предпочитает продолжать работу над задачами в текущей группе расписания, прежде чем перейти к другой группе расписания. Разблокированные контексты кэшируются в виртуальном процессоре и, как правило, планируются в последнем в первом из (LIFO) моды виртуальный процессор, который разблокировал их.|

### <a name="requirements"></a>Требования

**Заголовок:** concrt.h

## <a name="switchingproxystate-enumeration"></a><a name="switchingproxystate"></a>ПересчетПрокси-государственное число

Используется для обозначения состояния прокси-потока, когда он выполняет совместное переключение контекста на другой прокси-поток.

```cpp
enum SwitchingProxyState;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`Blocking`|Указывает, что поток вызова совместно блокируется и должен находиться исключительно в собственности вызывающего абонента до тех пор, пока впоследствии не будет запущен снова и не будет выполняться другие действия.|
|`Idle`|Указывается, что поток вызовов больше не нужен планировщику и возвращается диспетчеру ресурсов. Контекст, который был отправлен, больше не может быть использован менеджером ресурсов.|
|`Nesting`|Означает, что поток вызова гнездится планировщиком ребенка и необходим вызывающему абоненту, чтобы прикрепить его к другому планировщику.|

### <a name="remarks"></a>Remarks

Параметр типа `SwitchingProxyState` передается методу, `IThreadProxy::SwitchTo` чтобы проинструктировать менеджера ресурсов, как обращаться с прокси-сервером потока, который делает вызов.

Для получения дополнительной информации о том, как этот тип используется, [см. IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto).

## <a name="task_group_status-enumeration"></a><a name="task_group_status"></a>task_group_status Ичисление

Описывает состояние выполнения объекта `task_group` или `structured_task_group`. Значение этого типа возвращается многочисленными методами, которые ожидают выполнения задач, запланированных для завершения группой задач.

```cpp
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

## <a name="winrtinitializationtype-enumeration"></a><a name="winrtinitializationtype"></a>WinRTПервоначальнизацияТип Enumeration

Используется политикой `WinRTInitialization` для описания того, будет ли среда выполнения Windows инициализирована в потоках планировщика для приложения, которое работает в операционных системах Windows с версии 8 или выше, и каким образом это будет выполняться. Для получения дополнительной информации о [PolicyElementKey](concurrency-namespace-enums.md)доступных политиках планировщика см.

```cpp
enum WinRTInitializationType;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`DoNotInitializeWinRT`|Когда приложение выполняется в операционной системе Windows версии 8 и выше, потоки в планировщике не инициализируют среду выполнения Windows.|
|`InitializeWinRTAsMTA`|Когда приложение выполняется в операционной системе Windows версии 8 или выше, каждый поток в планировщике инициализирует среду выполнения Windows и объявляет, что это часть многопотокового подразделения.|

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
