---
title: "Пространство имен concurrency | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concurrent_priority_queue/concurrency"
  - "agents/concurrency"
  - "concurrent_vector/concurrency"
  - "concrt/concurrency"
  - "internal_split_ordered_list/concurrency"
  - "concurrent_queue/concurrency"
  - "pplcancellation_token/concurrency"
  - "pplinterface/concurrency"
  - "ppltasks/concurrency"
  - "ppl/concurrency"
  - "concurrent_unordered_map/concurrency"
  - "concrtrm/concurrency"
  - "concurrent_unordered_set/concurrency"
  - "pplconcrt/concurrency"
  - "internal_concurrent_hash/concurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Concurrency - пространство имен"
ms.assetid: f1d33ca2-679b-4442-b140-22a9d9df61d1
caps.latest.revision: 37
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# Пространство имен concurrency
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Пространство имен `Concurrency` предоставляет классы и функции, предоставляющие доступ к среде выполнения с параллелизмом, которая является платформой параллельного программирования для C++. Дополнительные сведения см. в разделе [среда выполнения с параллелизмом](../../../parallel/concrt/concurrency-runtime.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace concurrency;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="namespaces"></a>Пространства имен  
  
|Имя|Описание|  
|----------|-----------------|  
|[Concurrency::Extensibility пространства имен](http://msdn.microsoft.com/ru-ru/16a86ff2-128e-4edf-89e4-38aac79c81f9)||  
  
### <a name="typedefs"></a>Typedefs  
  
|Имя|Описание|  
|----------|-----------------|  
|`runtime_object_identity`|Каждый экземпляр сообщения имеет идентификатор, который сопутствует ему при клонировании и передаче между компонентами обмена сообщениями. Он не может быть адресом объекта сообщения.|  
|`task_status`|Тип, который представляет конечное состояние задачи. Допустимые значения: `completed` и `canceled`.|  
|`TaskProc`|Простая абстракция для задачи, определенная как `void (__cdecl * TaskProc)(void *)`. `TaskProc` вызывается для вызова тела задачи.|  
|`TaskProc_t`|Простая абстракция для задачи, определенная как `void (__cdecl * TaskProc_t)(void *)`. `TaskProc` вызывается для вызова тела задачи.|  
  
### <a name="classes"></a>Классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс affinity_partitioner](../Topic/affinity_partitioner%20Class.md)|Класс `affinity_partitioner` аналогичен классу `static_partitioner`, но он повышает сходство кэша путем подбора поддиапазонов сопоставления для потоков рабочего процесса. Он может значительно повысить производительность, если цикл повторно выполняется в одном и том же наборе данных и данные помещаются в кэш. Обратите внимание, что один и тот же объект `affinity_partitioner` должен использоваться с последующими итерациями параллельного цикла, выполняемого в указанном наборе данных, чтобы воспользоваться преимуществом локальности данных.|  
|[Класс Agent](../../../parallel/concrt/reference/agent-class.md)|Класс, предназначенный для использования в качестве базового класса для всех независимых агентов. Он используется для скрытия состояния от других агентов и взаимодействия посредством передачи сообщений.|  
|[Класс auto_partitioner](../../../parallel/concrt/reference/auto-partitioner-class.md)|Класс `auto_partitioner` представляет метод, который алгоритмы `parallel_for`, `parallel_for_each` и `parallel_transform` используют по умолчанию для разделения обрабатываемого диапазона. Этот метод разделения использует как перенос диапазона для распределения нагрузки, так и отмену по итерациям.|  
|[Класс bad_target](../../../parallel/concrt/reference/bad-target-class.md)|Этот класс описывает исключение, которое создается, если блок обмена сообщениями получает указатель на целевой объект, который неверен для выполняемой операции.|  
|[Call-класс](../../../parallel/concrt/reference/call-class.md)|Блок обмена сообщениями `call` — это упорядоченный блок `target_block` с несколькими источниками, который вызывает заданную функцию при получении сообщения.|  
|[Класс cancellation_token](../../../parallel/concrt/reference/cancellation-token-class.md)|Класс `cancellation_token` представляет возможность определить, получала ли некоторая операция запрос на отмену. Заданный токен можно связать с `task_group`, `structured_task_group` или `task` для предоставления неявной отмены. Его также можно опрашивать на предмет отмены или зарегистрировать обратный вызов для той ситуации, когда отменяется связанный `cancellation_token_source`.|  
|[Класс cancellation_token_registration](../../../parallel/concrt/reference/cancellation-token-registration-class.md)|Класс `cancellation_token_registration` представляет уведомление обратного вызова из `cancellation_token`. При использовании метода `register` на `cancellation_token` для получения уведомления о времени выполнения отмены объект `cancellation_token_registration` возвращается как дескриптор для обратного вызова, чтобы вызывающий код мог запросить, чтобы определенный обратный вызов больше не выполнялся с помощью метода `deregister`.|  
|[Класс cancellation_token_source](../../../parallel/concrt/reference/cancellation-token-source-class.md)|Класс `cancellation_token_source` представляет возможность отмены некоторой отменяемой операции.|  
|[Класс Choice](../../../parallel/concrt/reference/choice-class.md)|Блок обмена сообщениями `choice` — это блок с несколькими источниками и одной целью, который представляет взаимодействие потока управления с набором источников. Блок choice будет ожидать доступа к любому из нескольких источников для создания сообщения и распространит индекс источника, создавшего сообщение.|  
|[Класс combinable](../../../parallel/concrt/reference/combinable-class.md)|Объект `combinable<T>` предназначен для предоставления частной для потока копии данных для выполнения локальных для потока вложенных вычислений без блокировки потока в параллельных алгоритмах. В конце выполнения параллельной операции частные для потока вложенные вычисления можно объединить для получения общего результата. Этот класс можно использовать вместо общей переменной, что может позволить улучшить производительность в случае возникновения большого числа конфликтов доступа к этой общей переменной.|  
|[Класс concurrent_priority_queue](../../../parallel/concrt/reference/concurrent-priority-queue-class.md)|Класс `concurrent_priority_queue` — это контейнер, который позволяет нескольким потокам параллельно помещать и извлекать элементы. Элементы извлекаются в порядке приоритета, определяемого функтором, предоставленным в качестве аргумента шаблона.|  
|[Класс concurrent_queue](../Topic/concurrent_queue%20Class.md)|Класс `concurrent_queue` представляет собой класс контейнера последовательности, обеспечивающий доступ к элементам в порядке поступления. Он позволяет использовать ограниченный набор параллельно-безопасных операций, таких как `push` и `try_pop`.|  
|[Класс concurrent_unordered_map](../../../parallel/concrt/reference/concurrent-unordered-map-class.md)|Класс `concurrent_unordered_map` представляет собой безопасный в отношении параллелизма контейнер, управляющий последовательностью элементов типа `std::pair<const K, _Element_type>` переменной длины. Последовательность представлена таким образом, что позволяет параллельно-безопасно выполнять операции присоединения, получения доступа к элементу, доступа к итератору и обхода итератора.|  
|[Класс concurrent_unordered_multimap](../../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)|Класс `concurrent_unordered_multimap` представляет собой безопасный в отношении параллелизма контейнер, управляющий последовательностью элементов типа `std::pair<const K, _Element_type>` переменной длины. Последовательность представлена таким образом, что позволяет параллельно-безопасно выполнять операции присоединения, получения доступа к элементу, доступа к итератору и обхода итератора.|  
|[Класс concurrent_unordered_multiset](../../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)| `concurrent_unordered_multiset` Класс является контейнером параллельность, управляющий последовательностью элементов типа K. переменной длины Последовательность представляется в виде, позволяющем параллельность операции присоединения, доступ к элементу, доступа к итератору и итератора обхода.|  
|[Класс concurrent_unordered_set](../../../parallel/concrt/reference/concurrent-unordered-set-class.md)| `concurrent_unordered_set` Класс является контейнером параллельность, управляющий последовательностью элементов типа K. переменной длины Последовательность представляется в виде, позволяющем параллельность операции присоединения, доступ к элементу, доступа к итератору и итератора обхода.|  
|[Класс concurrent_vector](../../../parallel/concrt/reference/concurrent-vector-class.md)|Класс `concurrent_vector` представляет собой класс контейнера последовательности, обеспечивающий доступ к элементам в случайном порядке. Позволяет параллельно-безопасно выполнять операции присоединения, получения доступа к элементу, доступа к итератору и обхода итератора.|  
|[Класс контекста](Context%20Class.md)|Представляет абстракцию для контекста выполнения.|  
|[Класс context_self_unblock](../../../parallel/concrt/reference/context-self-unblock-class.md)|Этот класс описывает исключение, которое создается при вызове метода `Unblock` объекта `Context` из того же контекста. Это означает попытку данного контекста разблокировать самого себя.|  
|[Класс context_unblock_unbalanced](../../../parallel/concrt/reference/context-unblock-unbalanced-class.md)|Данный класс описывает исключение, создаваемое, если вызовы методов `Block` и `Unblock` объекта `Context` объединены неправильно.|  
|[Класс critical_section](../../../parallel/concrt/reference/critical-section-class.md)|Не допускающий повторные входы мьютекс, который явно учитывает среду выполнения с параллелизмом.|  
|[Класс CurrentScheduler](../Topic/CurrentScheduler%20Class.md)|Представляет абстракцию для текущего планировщика, связанного с вызывающим контекстом.|  
|[Класс default_scheduler_exists](../../../parallel/concrt/reference/default-scheduler-exists-class.md)|Этот класс описывает исключение, возникающее при вызове метода `Scheduler::SetDefaultSchedulerPolicy`, когда планировщик по умолчанию уже существует в процессе.|  
|[Класс Event](../Topic/event%20Class.md)|Сбрасываемое вручную событие, которое явно учитывает среду выполнения с параллелизмом.|  
|[Класс improper_lock](../../../parallel/concrt/reference/improper-lock-class.md)|Этот класс описывает исключение, создаваемое, когда блокировка получена неправильно.|  
|[Класс improper_scheduler_attach](../../../parallel/concrt/reference/improper-scheduler-attach-class.md)|Этот класс описывает исключение, которое создается при вызове метода `Attach` на объекте `Scheduler`, который уже присоединен к текущему контексту.|  
|[Класс improper_scheduler_detach](../Topic/improper_scheduler_detach%20Class.md)|Этот класс описывает исключение, создаваемое при вызове метода `CurrentScheduler::Detach` в контексте, который не присоединен ни к одному планировщику с помощью метода `Attach` объекта `Scheduler`.|  
|[Класс improper_scheduler_reference](../Topic/improper_scheduler_reference%20Class.md)|Данный класс описывает исключение, которое создается при вызове метода `Reference` на объекте `Scheduler`, который завершает работу, из контекста, который не является частью этого планировщика.|  
|[Класс invalid_link_target](../../../parallel/concrt/reference/invalid-link-target-class.md)|Данный класс описывает исключение, создаваемое, когда вызывается метод `link_target` блока обмена сообщениями и блок сообщений не может создать связь с целевым объектом. Это может быть результатом превышения числа ссылок, допустимых для блока сообщений, или попытки связать указанную цель с одним и тем же источником дважды.|  
|[Класс invalid_multiple_scheduling](../../../parallel/concrt/reference/invalid-multiple-scheduling-class.md)|Этот класс описывает исключение, создаваемое, если объект `task_handle` запланирован несколько раз с помощью метода `run` объекта `task_group` или `structured_task_group` без промежуточных вызовов любого из методов `wait` или `run_and_wait`.|  
|[Класс invalid_operation](../Topic/invalid_operation%20Class.md)|Данный класс описывает исключение, возникающее при выполнении недопустимой операции, которая не описывается более точно другим типом исключения, создаваемым средой выполнения с параллелизмом.|  
|[Класс invalid_oversubscribe_operation](../../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md)|Этот класс описывает исключение, создаваемое при вызове метода `Context::Oversubscribe` с параметром `_BeginOversubscription`, имеющим значение `false`, без предварительного вызова метода `Context::Oversubscribe` с параметром `_BeginOversubscription`, имеющим значение `true`.|  
|[Класс invalid_scheduler_policy_key](../../../parallel/concrt/reference/invalid-scheduler-policy-key-class.md)|Этот класс описывает исключение, создаваемое, когда конструктору объекта `SchedulerPolicy` передается неверный или неизвестный ключ или методу `SetPolicyValue` объекта `SchedulerPolicy` передается ключ, который должен быть изменен другими средствами, такими как метод `SetConcurrencyLimits`.|  
|[Класс invalid_scheduler_policy_thread_specification](../../../parallel/concrt/reference/invalid-scheduler-policy-thread-specification-class.md)|Данный класс описывает исключение, создаваемое при попытке установить ограничения параллельности объекта `SchedulerPolicy` таким образом, чтобы значение ключа `MinConcurrency` было меньше, чем значение ключа `MaxConcurrency`.|  
|[Класс invalid_scheduler_policy_value](../../../parallel/concrt/reference/invalid-scheduler-policy-value-class.md)|Этот класс описывает исключение, создаваемое, когда ключу политики объекта `SchedulerPolicy` присваивается недопустимое для этого ключа значение.|  
|[Класс ISource](../../../parallel/concrt/reference/isource-class.md)|Класс `ISource` является интерфейсом для всех блоков источников. Блоки источников распространяют сообщения в блоки `ITarget`.|  
|[Класс ITarget](../../../parallel/concrt/reference/itarget-class.md)|Класс `ITarget` является интерфейсом для всех целевых блоков. Целевые блоки потребляют сообщения, предлагаемые ими блоками `ISource`.|  
|[Класс JOIN](../Topic/join%20Class.md)|Блок обмена сообщениями `join` — это упорядоченный блок `propagator_block` с несколькими источниками и одной целью, который объединяет сообщения типа `T` от каждого из своих источников.|  
|[Класс Location](../../../parallel/concrt/reference/location-class.md)|Абстракция физического расположения на оборудовании.|  
|[Класс Message](../../../parallel/concrt/reference/message-class.md)|Основной конверт сообщения, содержащий полезные данные, передаваемые между блоками обмена сообщениями.|  
|[Класс message_not_found](../../../parallel/concrt/reference/message-not-found-class.md)|Этот класс описывает исключение, создаваемое, когда блок обмена сообщениями не может найти запрошенное сообщение.|  
|[Класс message_processor](../../../parallel/concrt/reference/message-processor-class.md)|Класс `message_processor` — это абстрактный базовый класс для обработки объектов `message`. Упорядочивание сообщений не гарантируется.|  
|[Класс missing_wait](../../../parallel/concrt/reference/missing-wait-class.md)|Этот класс описывает исключение, возникающее при наличии задач, для которых по-прежнему запланирован объект `task_group` или `structured_task_group` на момент выполнения деструктора объекта. Это исключение не создается, если деструктор достигается из-за освобождения стека в результате исключения.|  
|[Класс multi_link_registry](../../../parallel/concrt/reference/multi-link-registry-class.md)|Объект `multi_link_registry` представляет собой `network_link_registry`, управляющий несколькими блоками источников или целевыми блоками.|  
|[Класс multitype_join](../../../parallel/concrt/reference/multitype-join-class.md)|Блок обмена сообщениями `multitype_join` — это блок с несколькими источниками и одной целью, который объединяет сообщения разных типов от каждого из своих источников и предлагает кортеж объединенных сообщений своему целевому объекту.|  
|[Класс nested_scheduler_missing_detach](../../../parallel/concrt/reference/nested-scheduler-missing-detach-class.md)|Этот класс описывает исключение, которое возникает, когда исполняющая среда с параллелизмом обнаруживает, что вы не вызвали метод `CurrentScheduler::Detach` для контекста, который присоединился ко второму планировщику с помощью метода `Attach` объекта `Scheduler`.|  
|[Класс network_link_registry](../Topic/network_link_registry%20Class.md)|Абстрактный базовый класс `network_link_registry` управляет связями между блоками источников и целевыми блоками.|  
|[Класс operation_timed_out](../../../parallel/concrt/reference/operation-timed-out-class.md)|Этот класс описывает исключение, создаваемое по истечении времени ожидания операции.|  
|[Класс ordered_message_processor](../Topic/ordered_message_processor%20Class.md)|Класс `ordered_message_processor` представляет собой `message_processor`, который позволяет блокам обмена сообщениями обрабатывать сообщения в том порядке, в котором они их получают.|  
|[Класс overwrite_buffer](../../../parallel/concrt/reference/overwrite-buffer-class.md)|Блок обмена сообщениями `overwrite_buffer` — это упорядоченный блок `propagator_block` с несколькими источниками и несколькими целями, который может хранить одно сообщение в один момент времени. Новые сообщения перезаписывают предыдущие.|  
|[Класс progress_reporter](../../../parallel/concrt/reference/progress-reporter-class.md)|Класс формирования отчетов о ходе выполнения позволяет формировать уведомления о ходе выполнения определенного типа. Каждый объект progress_reporter привязан к конкретному асинхронному действию или операции.|  
|[Класс propagator_block](../../../parallel/concrt/reference/propagator-block-class.md)|Класс `propagator_block` — это абстрактный базовый класс для блоков сообщений, которые являются одновременно блоками источников и целевыми блоками. Он объединяет функциональные возможности обоих классов, `source_block` и `target_block`.|  
|[Класс reader_writer_lock](../Topic/reader_writer_lock%20Class.md)|Блокировка чтения или записи на основе очередей с предпочтением записи только с локальным вращением. Блокировка предоставляет модулям записи доступ в порядке поступления и блокирует доступ модулей чтения при постоянной нагрузке модулей записи.|  
|[Класс ScheduleGroup](../Topic/ScheduleGroup%20Class.md)|Представляет абстракцию для группы расписаний. Группы расписаний организуют набор связанных работ, которые выигрывают от планирования в непосредственной близости друг от друга: во времени (путем выполнения другой задачи в той же группе перед перемещением в другую группу) или в пространстве (путем выполнения нескольких элементов в той же группе в том же узле NUMA или физическом сокете).|  
|[Класс планировщика](../../../parallel/concrt/reference/scheduler-class.md)|Представляет абстракцию для планировщика среды выполнения с параллелизмом.|  
|[Класс scheduler_not_attached](../Topic/scheduler_not_attached%20Class.md)|Этот класс описывает исключение, создаваемое при выполнении операции, при которой планировщик должен был присоединен к текущему контексту, а он не присоединен.|  
|[Класс scheduler_resource_allocation_error](../../../parallel/concrt/reference/scheduler-resource-allocation-error-class.md)|Этот класс описывает исключение, возникающее из-за сбоя получения критического ресурса в исполняющей среде с параллелизмом.|  
|[Класс scheduler_worker_creation_error](../Topic/scheduler_worker_creation_error%20Class.md)|Этот класс описывает исключение, которое создается из-за сбоя создания рабочего контекста выполнения в исполняющей среде с параллелизмом.|  
|[Класс SchedulerPolicy](../../../parallel/concrt/reference/schedulerpolicy-class.md)|Класс `SchedulerPolicy` содержит набор пар «ключ — значение» по одной для каждого элемента политики, управляющего поведением экземпляра планировщика.|  
|[Класс simple_partitioner](../Topic/simple_partitioner%20Class.md)|Класс `simple_partitioner` представляет статическое разделение диапазона, в котором итерации выполняются с помощью `parallel_for`. Разделитель делит диапазон на фрагменты таким образом, что каждый фрагмент имеет число итераций не менее указанного размера фрагмента.|  
|[Класс single_assignment](../../../parallel/concrt/reference/single-assignment-class.md)|Блок обмена сообщениями `single_assignment` — это упорядоченный блок `propagator_block` с несколькими источниками и несколькими целями, который может хранить один объект `message` с однократной записью.|  
|[Класс single_link_registry](../Topic/single_link_registry%20Class.md)|Объект `single_link_registry` представляет собой `network_link_registry`, управляющий только одним блоком источника или целевым блоком.|  
|[Класс source_block](../Topic/source_block%20Class.md)|Класс `source_block` — это абстрактный базовый класс только для блоков источника. Класс предоставляет основные функции управления соединениями, а также проверки распространенных ошибок.|  
|[Класс source_link_manager](../Topic/source_link_manager%20Class.md)|Объект `source_link_manager` управляет сетевыми соединениями блоков обмена сообщениями с блоками `ISource`.|  
|[Класс static_partitioner](../Topic/static_partitioner%20Class.md)|Класс `static_partitioner` представляет статическое разделение диапазона, в котором итерации выполняются с помощью `parallel_for`. Разделитель делит диапазон на количество блоков, соответствующее количеству работников, доступных базовому планировщику.|  
|[Класс structured_task_group](../../../parallel/concrt/reference/structured-task-group-class.md)|Класс `structured_task_group` представляет коллекцию параллельной работы со сложной структурой. Можно поместить в очередь `structured_task_group` отдельные параллельные задачи с помощью объектов `task_handle` и ожидать их выполнения или отменить группу задач до завершения выполнения, что приведет к отмене всех задач, которые не начали выполнение.|  
|[Класс target_block](../../../parallel/concrt/reference/target-block-class.md)|Класс `target_block` — это абстрактный базовый класс, который предоставляет основные функции управления соединениями и проверку ошибок только для целевых блоков.|  
|[Класс Task (среда выполнения параллелизма)](../../../parallel/concrt/reference/task-class-concurrency-runtime.md)|Класс `task` библиотеки параллельных шаблонов (PPL). Объект `task` представляет работу, которая может быть выполнена асинхронно и параллельно с другими задачами и параллельной работой, созданной параллельными алгоритмами в среде выполнения с параллелизмом. При успешном завершении он выводи результат типа `_ResultType`. Задачи типа `task<void>` никакого результата не дают. Задачи можно ожидать и отменять независимо от других задач. Также возможно сочетание с другими задачами с помощью шаблонов продолжений (`then`), присоединений (`when_all`) и выбора (`when_any`).|  
|[Класс task_canceled](../../../parallel/concrt/reference/task-canceled-class.md)|Этот класс описывает исключение, которое создается уровнем задач PPL для принудительной отмены текущей задачи. Оно также создается методом `get()` метод [задачи](http://msdn.microsoft.com/ru-ru/5389e8a5-5038-40b6-844a-55e9b58ad35f), для отмененной задачи.|  
|[Класс task_completion_event](../../../parallel/concrt/reference/task-completion-event-class.md)|Класс `task_completion_event` позволяет отложить выполнение задачи до выполнения условия или запустить задачу в ответ на внешнее событие.|  
|[Класс task_continuation_context](../../../parallel/concrt/reference/task-continuation-context-class.md)|Класс `task_continuation_context` позволяет указать место продолжения выполнения задачи. Этот класс рекомендуется использовать из приложения Магазина Windows. При использовании других приложений контекст выполнения продолжения задачи определяется средой выполнения и не настраивается.|  
|[Класс task_group](../Topic/task_group%20Class.md)|Класс `task_group` представляет коллекцию параллельной работы, для которой возможно ожидание или отмена.|  
|[Класс task_handle](../../../parallel/concrt/reference/task-handle-class.md)|Класс `task_handle` представляет отдельный параллельный рабочий элемент. Он инкапсулирует инструкции и данные, необходимые для выполнения части работы.|  
|[Класс task_options (среда выполнения с параллелизмом)](../Topic/task_options%20Class%20\(Concurrency%20Runtime\).md)|Представляет допустимые параметры для создания задачи|  
|[Класс Timer](../../../parallel/concrt/reference/timer-class.md)|Блок обмена сообщениями `timer` — это блок `source_block` с одной целью, который может отправлять сообщение своей цели по истечении указанного периода времени или через заданные интервалы времени.|  
|[Класс transformer](../../../parallel/concrt/reference/transformer-class.md)|Блок обмена сообщениями `transformer` — это упорядоченный блок `propagator_block` с одной целью и несколькими источниками, который может принимать сообщения одного типа и хранить неограниченное число сообщений другого типа.|  
|[Класс unbounded_buffer](../Topic/unbounded_buffer%20Class.md)|Блок обмена сообщениями `unbounded_buffer` — это упорядоченный блок `propagator_block` с несколькими целями и несколькими источниками, который может хранить неограниченное число сообщений.|  
|[Класс unsupported_os](../../../parallel/concrt/reference/unsupported-os-class.md)|Данный класс описывает исключение, которое создается при использовании неподдерживаемой операционной системы.|  
  
### <a name="structures"></a>Структуры  
  
|Имя|Описание|  
|----------|-----------------|  
|[Структура DispatchState](../../../parallel/concrt/reference/dispatchstate-structure.md)|Структура `DispatchState` используется для передачи состояния в метод `IExecutionContext::Dispatch`. Она описывает обстоятельства, при которых метод `Dispatch` вызывается для интерфейса `IExecutionContext`.|  
|[Структура IExecutionContext](../Topic/IExecutionContext%20Structure.md)|Интерфейс для контекста выполнения, который может выполняться на данном виртуальном процессоре и к которому может применяться совместное переключение контекста.|  
|[Структура IExecutionResource](../../../parallel/concrt/reference/iexecutionresource-structure.md)|Абстракция для аппаратного потока.|  
|[Структура IResourceManager](../../../parallel/concrt/reference/iresourcemanager-structure.md)|Интерфейс для диспетчера ресурсов среды выполнения с параллелизмом. Это интерфейс, по которому планировщики взаимодействуют с диспетчером ресурсов.|  
|[Структура IScheduler](../../../parallel/concrt/reference/ischeduler-structure.md)|Интерфейс для абстракции планировщика работы. Диспетчер ресурсов среды выполнения с параллелизмом использует этот интерфейс для взаимодействия с планировщиками работы.|  
|[Структура ISchedulerProxy](../../../parallel/concrt/reference/ischedulerproxy-structure.md)|Интерфейс, по которому планировщики взаимодействуют с диспетчером ресурсов среды выполнения с параллелизмом для согласования выделения ресурсов.|  
|[Структура IThreadProxy](../../../parallel/concrt/reference/ithreadproxy-structure.md)|Абстракция для потока выполнения. В зависимости от ключа политики `SchedulerType` созданного планировщика, диспетчер ресурсов предоставит прокси-поток, поддерживаемый обычным потоком Win32 или потоком планировщика пользовательского режима (UMS). Потоки UMS поддерживаются в 64-разрядных операционных системах Windows 7 и более поздних версий.|  
|[Структура ITopologyExecutionResource](../../../parallel/concrt/reference/itopologyexecutionresource-structure.md)|Интерфейс для ресурса выполнения, как определено диспетчером ресурсов.|  
|[Структура ITopologyNode](../../../parallel/concrt/reference/itopologynode-structure.md)|Интерфейс для узла топологии, как определено диспетчером ресурсов. Узел содержит один или несколько ресурсов выполнения.|  
|[Структура IUMSCompletionList](../../../parallel/concrt/reference/iumscompletionlist-structure.md)|Представляет список выполнения UMS. Когда поток UMS блокируется, отправляется назначенный планировщиком контекст планирования для принятия решения о том, что нужно запланировать для корня базового виртуального процессора, пока исходный поток заблокирован. Когда снимается блокировка исходного потока, операционная система ставит его в очередь списка выполнения, который доступен через этот интерфейс. Планировщик может запросить список выполнения в назначенном контексте планирования или в другом месте, в котором он выполняет поиск работы.|  
|[Структура IUMSScheduler](../../../parallel/concrt/reference/iumsscheduler-structure.md)|Интерфейс абстракции планировщика, которому требуется, чтобы диспетчер ресурсов среды выполнения с параллелизмом передал ему потоки планировщика в пользовательском режиме (UMS). Диспетчер ресурсов среды выполнения с параллелизмом использует этот интерфейс для взаимодействия с планировщиками потоков UMS. Интерфейс `IUMSScheduler` наследует от интерфейса `IScheduler`.|  
|[Структура IUMSThreadProxy](../../../parallel/concrt/reference/iumsthreadproxy-structure.md)|Абстракция для потока выполнения. Если требуется предоставлять для планировщика потоки планировщика в пользовательском режиме (UMS), задайте для элемента политики планировщика `SchedulerKind` значение `UmsThreadDefault` и реализуйте интерфейс `IUMSScheduler`. Потоки UMS поддерживаются только в 64-разрядных операционных системах Windows 7 и более поздних версий.|  
|[Структура IUMSUnblockNotification](../../../parallel/concrt/reference/iumsunblocknotification-structure.md)|Представляет уведомление диспетчера ресурсов о том, что прокси-поток, который заблокировал и запустил возврат к заданному контексту планирования планировщика, разблокирован и готов для планирования. Этот интерфейс является недопустимым, когда связанный с прокси-потоком контекст выполнения, возвращенный из метода `GetContext`, переносится.|  
|[Структура IVirtualProcessorRoot](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)|Абстракция для аппаратного потока, в котором может выполняться прокси-поток.|  
|[Структура scheduler_interface](../../../parallel/concrt/reference/scheduler-interface-structure.md)|Интерфейс планировщика|  
|[Структура scheduler_ptr (среда выполнения с параллелизмом)](../../../parallel/concrt/reference/scheduler-ptr-structure-concurrency-runtime.md)|Представляет указатель на планировщик. Этот класс существует для того, чтобы обеспечить возможность использования спецификации общего времени жизни путем применения shared_ptr или простой ссылки с помощью необработанного указателя.|  
  
### <a name="enumerations"></a>Перечисления  
  
|Имя|Описание|  
|----------|-----------------|  
|[Перечисление agent_status](../Topic/agent_status%20Enumeration.md)|Допустимые состояния для объекта `agent`.|  
|[Перечисление Agents_EventType](../Topic/Agents_EventType%20Enumeration.md)|Типы событий, которые можно отслеживать с помощью функции трассировки, предоставляемой библиотекой агентов.|  
|[Перечисление ConcRT_EventType](../Topic/ConcRT_EventType%20Enumeration.md)|Типы событий, которые можно отслеживать с помощью функций трассировки, обеспечиваемых средой выполнения с параллелизмом.|  
|[Перечисление Concrt_TraceFlags](../Topic/Concrt_TraceFlags%20Enumeration.md)|Флажки трассировки для типов событий|  
|[Перечисление CriticalRegionType](../Topic/CriticalRegionType%20Enumeration.md)|Тип критической области, внутри которой находится контекст.|  
|[Перечисление DynamicProgressFeedbackType](../Topic/DynamicProgressFeedbackType%20Enumeration.md)|Используется политикой `DynamicProgressFeedback` для описания того, будет ли к ресурсам планировщика применена повторная балансировка в соответствии со статистическими данными, полученными из планировщика, или только на основе перехода виртуальных процессоров в состояние бездействия и из него через вызовы методов `Activate` и `Deactivate` для интерфейса `IVirtualProcessorRoot`. Дополнительные сведения о доступных политиках планировщиков см. в разделе [перечисление PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md).|  
|[Перечисление join_type](../Topic/join_type%20Enumeration.md)|Тип блока обмена сообщениями `join`.|  
|[Перечисление message_status](../Topic/message_status%20Enumeration.md)|Допустимые ответы на предложение объекта `message` блоку.|  
|[Перечисление PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md)|Ключи политики, описывающие аспекты поведения планировщика. Каждый элемент политики описан с помощью пары «ключ — значение». Дополнительные сведения о политиках планировщика и их влияние на планировщики см. в разделе [Планировщик](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).|  
|[Перечисление SchedulerType](../Topic/SchedulerType%20Enumeration.md)|Используется политикой `SchedulerKind` для описания типа потоков, которые должен использовать планировщик для базовых контекстов выполнения. Дополнительные сведения о доступных политиках планировщиков см. в разделе [перечисление PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md).|  
|[Перечисление SchedulingProtocolType](../Topic/SchedulingProtocolType%20Enumeration.md)|Используется политикой `SchedulingProtocol` для описания того, какой алгоритм планирования будет использоваться для планировщика. Дополнительные сведения о доступных политиках планировщиков см. в разделе [перечисление PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md).|  
|[Перечисление SwitchingProxyState](../Topic/SwitchingProxyState%20Enumeration.md)|Используется для обозначения состояния прокси-потока, когда он выполняет совместное переключение контекста на другой прокси-поток.|  
|[Перечисление task_group_status](../Topic/task_group_status%20Enumeration.md)|Описывает состояние выполнения объекта `task_group` или `structured_task_group`. Значение этого типа возвращается многочисленными методами, которые ожидают выполнения задач, запланированных для завершения группой задач.|  
|[Перечисление WinRTInitializationType](../Topic/WinRTInitializationType%20Enumeration.md)|Используется политикой `WinRTInitialization` для описания того, будет ли среда выполнения Windows инициализирована в потоках планировщика для приложения, которое работает в операционных системах Windows с версии 8 или выше, и каким образом это будет выполняться. Дополнительные сведения о доступных политиках планировщиков см. в разделе [перечисление PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md).|  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание|  
|----------|-----------------|  
|[Функция Alloc](../Topic/Alloc%20Function.md)|Выделяет блок памяти указанного размера из подраспределителя кэширования среды параллелизма.|  
|[Функция asend](../Topic/asend%20Function.md)|Перегружен. Асинхронная операция отправки, которая планирует задачу для распространения данных в целевой блок.|  
|[Функция cancel_current_task](../Topic/cancel_current_task%20Function.md)|Отменяет выполняющуюся в данный момент задачу. Эту функцию можно вызывать из тела задачи, чтобы прервать выполнение задачи и перевести ее в состояние `canceled`.<br /><br /> Вызов этой функции является неподдерживаемым сценарием, если вы не находитесь в теле `task`. Такие действия приведут к неопределенному поведению, например сбою или зависанию в приложении.|  
|[Функция create_async](../Topic/create_async%20Function.md)|Создает асинхронную конструкцию среды выполнения Windows на основе предоставленного пользователем лямбда-выражения или объекта функции. Возвращаемый тип `create_async` — один из следующих: `IAsyncAction^`, `IAsyncActionWithProgress<TProgress>^`, `IAsyncOperation<TResult>^` или `IAsyncOperationWithProgress<TResult, TProgress>^`, в зависимости от сигнатуры лямбда-выражения, переданного методу.|  
|[Функция create_task](../Topic/create_task%20Function.md)|Перегружен. Создает PPL [задачи](http://msdn.microsoft.com/ru-ru/5389e8a5-5038-40b6-844a-55e9b58ad35f) объекта. Функция `create_task` может использоваться в любой ситуации, где бы вы использовали конструктор задач. Она предоставлена главным образом для удобства, поскольку позволяет использовать ключевое слово `auto` при создании задач.|  
|[Функция CreateResourceManager](../Topic/CreateResourceManager%20Function.md)|Возвращает интерфейс, который представляет одноэлементный экземпляр диспетчера ресурсов среды выполнения с параллелизмом. Диспетчер ресурсов отвечает за назначение ресурсов планировщикам, которым требуется взаимодействовать друг с другом.|  
|[Функция DisableTracing](../Topic/DisableTracing%20Function.md)|Отключает трассировку в среде выполнения с параллелизмом. Эту функция не рекомендуется использовать, поскольку трассировка событий Windows по умолчанию не регистрируется.|  
|[Функция EnableTracing](../Topic/EnableTracing%20Function.md)|Включает трассировку в среде выполнения с параллелизмом. Эта функция не рекомендована к использованию, поскольку трассировка событий Windows теперь по умолчанию включена.|  
|[Free-функция](../Topic/Free%20Function.md)|Освобождает блок памяти, ранее выделенный методом `Alloc` для подраспределителя кэширования среды выполнения с параллелизмом.|  
|[Функция get_ambient_scheduler (среда выполнения с параллелизмом)](../Topic/get_ambient_scheduler%20Function%20\(Concurrency%20Runtime\).md)||  
|[Функция GetExecutionContextId](../Topic/GetExecutionContextId%20Function.md)|Возвращает уникальный идентификатор, который можно назначить контексту выполнения, реализующему интерфейс `IExecutionContext`.|  
|[Функция GetOSVersion](../Topic/GetOSVersion%20Function.md)|Возвращает версию операционной системы.|  
|[Функция GetProcessorCount](../Topic/GetProcessorCount%20Function.md)|Возвращает число аппаратных потоков базовой системы.|  
|[Функция GetProcessorNodeCount](../Topic/GetProcessorNodeCount%20Function.md)|Возвращает число узлов NUMA или пакетов процессора в базовой системе.|  
|[Функция GetSchedulerId](../Topic/GetSchedulerId%20Function.md)|Возвращает уникальный идентификатор, который можно назначить планировщику, реализующему интерфейс `IScheduler`.|  
|[Функция interruption_point](../Topic/interruption_point%20Function.md)|Создает точку прерывания для отмены. Если отмена выполняется в контексте, где вызывается эта функция, это создает внутреннее исключение, которое прерывает текущую выполняемую параллельную работу. Если отмена не выполняется, функция ничего не делает.|  
|[Функция is_current_task_group_canceling](../Topic/is_current_task_group_canceling%20Function.md)|Возвращает значение, указывающее, находится ли группа задач, которая в данный момент выполняется в текущем контексте во встроенном режиме, в процессе активной отмены (или вскоре перейдет в это состояние). Обратите внимание, что в отсутствие групп задач, выполняющихся в текущем контексте во встроенном режиме, будет возвращено значение `false`.|  
|[Функция make_choice](../Topic/make_choice%20Function.md)|Перегружен. Конструирует блок сообщений `choice` из необязательного объекта `Scheduler` или `ScheduleGroup` и двух или более источников входных данных.|  
|[Функция make_greedy_join](../Topic/make_greedy_join%20Function.md)|Перегружен. Конструирует блок сообщений `greedy multitype_join` из необязательного объекта `Scheduler` или `ScheduleGroup` и двух или более источников входных данных.|  
|[Функция make_join](../Topic/make_join%20Function.md)|Перегружен. Конструирует блок сообщений `non_greedy multitype_join` из необязательного объекта `Scheduler` или `ScheduleGroup` и двух или более источников входных данных.|  
|[Функция make_task](../Topic/make_task%20Function.md)|Метод фабрики для создания объекта `task_handle`.|  
|[Функция parallel_buffered_sort](../Topic/parallel_buffered_sort%20Function.md)|Перегружен. В параллельном режиме упорядочивает элементы в указанном диапазоне в не нисходящем порядке или согласно критерию упорядочивания, заданному бинарным предикатом. Эта функция семантически аналогична `std::sort` в том, что она является нестабильной сортировкой на месте на основе сравнения, за исключением того, что ей требуется `O(n)` дополнительного пространства и инициализация по умолчанию для сортируемых элементов.|  
|[Функция parallel_for](../Topic/parallel_for%20Function.md)|Перегружен. `parallel_for` выполняет итерацию по диапазону индексов и выполняет предоставленную пользователем функцию в каждой итерации параллельно.|  
|[Функция parallel_for_each](../Topic/parallel_for_each%20Function.md)|Перегружен. `parallel_for_each` применяет указанную функцию к каждому элементу в диапазоне параллельно. Эта функция семантически эквивалентна функции `for_each` в пространстве имен `std`, за исключением того, что итерация по элементам выполняется параллельно и порядок итерации не определен. Аргумент `_Func` должен поддерживать оператор вызова функции формы `operator()(T)`, где параметр `T` является типом элемента контейнера, для которого выполняется итерация.|  
|[Функция parallel_invoke](../Topic/parallel_invoke%20Function.md)|Перегружен. Выполняет объекты функции, предоставленные в виде параметров, в параллельном режиме и блокирует их до завершения выполнения. Каждый объект функции может быть лямбда-выражением, указателем на функцию или любым объектом, который поддерживает оператор вызова функции с подписью `void operator()()`.|  
|[Функция parallel_radixsort](../Topic/parallel_radixsort%20Function.md)|Перегружен. Располагает элементы в указанном диапазоне в неубывающем порядке, используя алгоритм сортировки основания системы счисления. Это стабильная функция сортировки, для которой требуется функция проекции, способная проецировать сортируемые элементы в неподписанные ключи целочисленного типа. Для сортируемых элементов требуется инициализация по умолчанию.|  
|[Функция parallel_reduce](../Topic/parallel_reduce%20Function.md)|Перегружен. Параллельно вычисляет сумму всех элементов в указанном диапазоне путем вычисления последовательных частичных сумм или вычисляет результаты последовательных частичных сумм, полученных сходным образом с использованием указанной бинарной операции, отличной от суммирования. `parallel_reduce` семантически аналогичен `std::accumulate`, но требует, чтобы бинарная операция была ассоциативна, а также значение идентификатора вместо начального значения.|  
|[Функция parallel_sort](../Topic/parallel_sort%20Function.md)|Перегружен. В параллельном режиме упорядочивает элементы в указанном диапазоне в не нисходящем порядке или согласно критерию упорядочивания, заданному бинарным предикатом. Эта функция семантически схожа с `std::sort`, так как она основана на сравнении, неустойчива, сортирует на месте.|  
|[Функция parallel_transform](../Topic/parallel_transform%20Function.md)|Перегружен. Применяет заданный объект функции к каждому элементу в исходном диапазоне или к паре элементов из двух исходных диапазонов и параллельно копирует возвращаемые значения объекта функции в диапазон назначения. Эта функция семантически эквивалентна `std::transform`.|  
|[Функция Receive](../Topic/receive%20Function.md)|Перегружен. Общая реализация получения, позволяющая контексту ожидать данные строго из одного источника и фильтровать значения, которые принимаются.|  
|[Функция run_with_cancellation_token](../Topic/run_with_cancellation_token%20Function.md)|Немедленно и синхронно выполняет объект функции в контексте заданного токена отмены.|  
|[Функция Send](../Topic/send%20Function.md)|Перегружен. Синхронная операции отправки, которая ожидает принятия или отклонения сообщения целевым объектом.|  
|[Функция set_ambient_scheduler (среда выполнения с параллелизмом)](../Topic/set_ambient_scheduler%20Function%20\(Concurrency%20Runtime\).md)||  
|[Функция set_task_execution_resources](../Topic/set_task_execution_resources%20Function.md)|Перегружен. Ограничивает ресурсы выполнения, используемые внутренними рабочими потоками среды выполнения с параллелизмом, определенным набором сходства.<br /><br /> Этот метод можно вызывать только до создания диспетчера ресурсов или между двумя периодами существования диспетчера ресурсов. Его можно вызывать несколько раз при условии, что в момент вызова диспетчер ресурсов не существует. После задания ограничения сходства оно будет оставаться действительным до следующего допустимого вызова метода `set_task_execution_resources`.<br /><br /> Предоставленная маска сходства не обязана быть подмножеством маски сходства процесса. Сходство процесса обновляется при необходимости.|  
|[Функция Swap](../Topic/swap%20Function.md)|Меняет местами элементы двух объектов `concurrent_vector`.|  
|[Функция task_from_exception (среда выполнения с параллелизмом)](../Topic/task_from_exception%20Function%20\(Concurrency%20Runtime\).md)||  
|[Функция task_from_result (среда выполнения с параллелизмом)](../Topic/task_from_result%20Function%20\(Concurrency%20Runtime\).md)||  
|[Функция Trace_agents_register_name](../Topic/Trace_agents_register_name%20Function.md)|Связывает данное имя с блоком сообщений или агентом в трассировки событий Windows.|  
|[Функция try_receive](../Topic/try_receive%20Function.md)|Перегружен. Общая реализация проверки-получения, позволяющая контексту выполнять поиск данных строго из одного источника и фильтровать значения, которые принимаются. Если данные не готовы, метод вернет значение False.|  
|[wait-функция](../Topic/wait%20Function.md)|Приостанавливает текущий контекст на указанный период времени.|  
|[Функция when_all](../Topic/when_all%20Function.md)|Создает задачу, которая завершается успешно, если все задачи, предоставленные в качестве аргументов, завершаются успешно.|  
|[Функция when_any](../Topic/when_any%20Function.md)|Перегружен. Создает задачу, которая завершается успешно, если любая из задач, предоставленных в качестве аргументов, завершается успешно.|  
  
### <a name="operators"></a>Операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор! =-оператор](../Topic/operator!=%20Operator.md)|Проверяет неравенство объекта `concurrent_vector` слева от оператора объекту `concurrent_vector` справа от оператора.|  
|[оператор & & оператор](../Topic/operator&&%20Operator.md)|Перегружен. Создает задачу, которая завершается успешно, если обе задачи, предоставленные в качестве аргументов, завершаются успешно.|  
|[оператор &#124; &#124; Оператор](../Topic/operator%7C%7C%20Operator.md)|Перегружен. Создает задачу, которая завершается успешно, если любая из задач, предоставленных в качестве аргументов, завершается успешно.|  
|[оператор < оператор](../Topic/operator%3C%20Operator.md)|Проверяет, меньше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора.|  
|[оператор < =-оператор](../Topic/operator%3C=%20Operator.md)|Проверяет, меньше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора, или равен ему.|  
|[оператор ==-оператор](../Topic/operator==%20Operator.md)|Проверяет равенство объекта `concurrent_vector` слева от оператора объекту `concurrent_vector` справа от оператора.|  
|[оператор > оператор](../Topic/operator%3E%20Operator.md)|Проверяет больше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора.|  
|[оператор > =-оператор](../Topic/operator%3E=%20Operator.md)|Проверяет больше ли объект `concurrent_vector` слева от оператора, чем объект `concurrent_vector` справа от оператора, или равен ему.|  
  
### <a name="constants"></a>Константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Константа AgentEventGuid](../Topic/AgentEventGuid%20Constant.md)|GUID категории ({B9B5B78C-0713-4898-A21A-C67949DCED07}), описывающий события трассировки Windows, запускаемые библиотекой агентов исполняющей среды с параллелизмом.|  
|[Константа ChoreEventGuid](../Topic/ChoreEventGuid%20Constant.md)|GUID категории, описывающий события трассировки событий Windows, инициированные средой выполнения с параллелизмом, которые непосредственно связаны с делами или задачами.|  
|[Константа ConcRT_ProviderGuid](../Topic/ConcRT_ProviderGuid%20Constant.md)|GUID поставщика трассировки событий Windows для среды выполнения с параллелизмом.|  
|[Константа CONCRT_RM_VERSION_1](../Topic/CONCRT_RM_VERSION_1%20Constant.md)|Указывает на поддержку интерфейса диспетчера ресурсов, определенного в Visual Studio 2010.|  
|[Константа ConcRTEventGuid](../Topic/ConcRTEventGuid%20Constant.md)|GUID категории, описывающий события трассировки событий Windows, инициированные средой выполнения с параллелизмом, которые не описаны подробнее другой категорией.|  
|[Константа ContextEventGuid](../Topic/ContextEventGuid%20Constant.md)|GUID категории, описывающий события трассировки событий Windows, инициированные средой выполнения с параллелизмом, которые непосредственно связаны с контекстами.|  
|[Константа COOPERATIVE_TIMEOUT_INFINITE](../Topic/COOPERATIVE_TIMEOUT_INFINITE%20Constant.md)|Значение, указывающее, что время ожидания никогда не должно истечь.|  
|[Константа COOPERATIVE_WAIT_TIMEOUT](../Topic/COOPERATIVE_WAIT_TIMEOUT%20Constant.md)|Значение, указывающее, что время ожидания истекло.|  
|[Константа INHERIT_THREAD_PRIORITY](../Topic/INHERIT_THREAD_PRIORITY%20Constant.md)|Специальное значение для ключа политики `ContextPriority`, указывающее, что приоритет потока всех контекстов в планировщике должен быть таким же, как приоритет потока, создавшего планировщик.|  
|[Константа LockEventGuid](../Topic/LockEventGuid%20Constant.md)|GUID категории, описывающий события трассировки событий Windows, инициированные средой выполнения с параллелизмом, которые непосредственно связаны с блокировками.|  
|[Константа MaxExecutionResources](../Topic/MaxExecutionResources%20Constant.md)|Специальное значение для ключей политики `MinConcurrency` и `MaxConcurrency`. По умолчанию соответствует числу аппаратных потоков на компьютере при отсутствии других ограничений.|  
|[Константа PPLParallelForeachEventGuid](../Topic/PPLParallelForeachEventGuid%20Constant.md)|GUID категории, описывающий события трассировки событий Windows, инициированные средой выполнения с параллелизмом, которые непосредственно связаны с использованием функции `parallel_for_each`.|  
|[Константа PPLParallelForEventGuid](../Topic/PPLParallelForEventGuid%20Constant.md)|GUID категории, описывающий события трассировки событий Windows, инициированные средой выполнения с параллелизмом, которые непосредственно связаны с использованием функции `parallel_for`.|  
|[Константа PPLParallelInvokeEventGuid](../Topic/PPLParallelInvokeEventGuid%20Constant.md)|GUID категории, описывающий события трассировки событий Windows, инициированные средой выполнения с параллелизмом, которые непосредственно связаны с использованием функции `parallel_invoke`.|  
|[Константа ResourceManagerEventGuid](../Topic/ResourceManagerEventGuid%20Constant.md)|GUID категории, описывающий события трассировки событий Windows, инициированные средой выполнения с параллелизмом, которые непосредственно связаны с диспетчером ресурсов.|  
|[Константа ScheduleGroupEventGuid](../Topic/ScheduleGroupEventGuid%20Constant.md)|GUID категории, описывающий события трассировки событий Windows, инициированные средой выполнения с параллелизмом, которые непосредственно связаны с группами расписаний.|  
|[Константа SchedulerEventGuid](../Topic/SchedulerEventGuid%20Constant.md)|GUID категории, описывающий события трассировки событий Windows, инициированные средой выполнения с параллелизмом, которые непосредственно связаны с действиями планировщика.|  
|[Константа VirtualProcessorEventGuid](../Topic/VirtualProcessorEventGuid%20Constant.md)|GUID категории, описывающий события трассировки событий Windows, инициированные средой выполнения с параллелизмом, которые непосредственно связаны с виртуальными процессорами.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h, concrt.h, concrtrm.h, concurrent_priority_queue.h, concurrent_queue.h, concurrent_unordered_map.h, concurrent_unordered_set.h, concurrent_vector.h, internal_concurrent_hash.h, internal_split_ordered_list.h, ppl.h, pplcancellation_token.h, pplconcrt.h, pplinterface.h, ppltasks.h  
  
## <a name="see-also"></a>См. также  
 [Ссылка](../../../parallel/concrt/reference/reference-concurrency-runtime.md)

