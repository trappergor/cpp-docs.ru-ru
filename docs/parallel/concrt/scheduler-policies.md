---
title: Политики планировщика | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scheduler policies
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cabb35901dab38247e8af7909199f8c7efdb4020
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442959"
---
# <a name="scheduler-policies"></a>Политики планировщика

В этом документе описывается роль политик планировщика в среде выполнения с параллелизмом. Объект *политики планировщика* определяет стратегию, которую планировщик применяет при управлении задачами. Например, рассмотрим приложение, которое требует выполнение некоторых задач с `THREAD_PRIORITY_NORMAL` и других задач с `THREAD_PRIORITY_HIGHEST`.  Можно создать два экземпляра планировщика: один задает политику `ContextPriority` как `THREAD_PRIORITY_NORMAL`, а второй определяет ту же политику как `THREAD_PRIORITY_HIGHEST`.

Использование политики планировщика позволяет разделять доступные ресурсы для обработки и назначать каждому планировщику фиксированный набор ресурсов. Например рассмотрим параллельный алгоритм, который невозможно использовать более четырех процессоров. Можно создать политики планировщика, который позволяет задачам параллельно использовать не более четырех процессоров.

> [!TIP]
>  Исполняющая среда с параллелизмом предоставляет планировщик по умолчанию. Поэтому не требуется создавать его в приложении. Поскольку планировщик задач помогает оптимизировать производительность приложений, мы рекомендуем начать с [библиотеки параллельных шаблонов (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) или [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) при наличии создать среду выполнения с параллелизмом.

При использовании [Concurrency::CurrentScheduler:: CREATE](reference/currentscheduler-class.md#create), [Concurrency::Scheduler:: CREATE](reference/scheduler-class.md#create), или [Concurrency::Scheduler:: SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) метод для создания экземпляра планировщика, указываемые [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) объект, содержащий коллекцию пар "ключ значение", определяющих поведение планировщика. `SchedulerPolicy` Конструктор принимает переменное число аргументов. Первый аргумент — количество элементов политики, которые вы собираетесь задать. Остальные элементы пары ключ значение для каждого элемента политики. В следующем примере создается `SchedulerPolicy` , указывающий три элемента политики. Среда выполнения использует для незаданных ключей политики значения по умолчанию.

[!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/cpp/scheduler-policies_1.cpp)]

[Concurrency::PolicyElementKey](reference/concurrency-namespace-enums.md#policyelementkey) перечисление определяет ключи политики, связанные с планировщиком задач. Ниже перечислены ключи политики и значение по умолчанию, используемые средой выполнения для каждого из них.

|Ключ политики|Описание|Значение по умолчанию|
|----------------|-----------------|-------------------|
|`SchedulerKind`|Объект [concurrency::SchedulerType](reference/concurrency-namespace-enums.md#schedulertype) значение, указывающее тип потоков, используемых для планирования задач.|`ThreadScheduler` (используйте стандартные потоки). Это единственное допустимое значение для этого ключа.|
|`MaxConcurrency`|`unsigned int` Значение, указывающее максимальное количество ресурсов параллелизма, которые использует планировщик.|[Concurrency::MaxExecutionResources](reference/concurrency-namespace-constants1.md#maxexecutionresources)|
|`MinConcurrency`|`unsigned int` Значение, указывающее минимальное количество ресурсов параллелизма, которые использует планировщик.|`1`|
|`TargetOversubscriptionFactor`|`unsigned int` Значение, указывающее, сколько потоков необходимо выделить для каждого ресурса обработки.|`1`|
|`LocalContextCacheSize`|`unsigned int` Значение, указывающее максимальное число контекстов, которые могут быть кэшированы в локальной очереди каждого виртуального процессора.|`8`|
|`ContextStackSize`|`unsigned int` Значение, указывающее размер стека, в килобайтах, которое следует зарезервировать для каждого контекста.|`0` (использовать размер стека по умолчанию)|
|`ContextPriority`|`int` Значение, указывающее приоритет потока для каждого контекста. Это может быть любое значение, которое можно передать [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) или `INHERIT_THREAD_PRIORITY`.|`THREAD_PRIORITY_NORMAL`|

|`SchedulingProtocol`| Объект [concurrency::SchedulingProtocolType](reference/concurrency-namespace-enums.md#schedulingprotocoltype) значение, указывающее используемый алгоритм планирования. | `EnhanceScheduleGroupLocality`| | `DynamicProgressFeedback`| Объект [concurrency::DynamicProgressFeedbackType](reference/concurrency-namespace-enums.md#dynamicprogressfeedbacktype) значение, указывающее, следует ли перераспределять ресурсы в соответствии с статистические данные о ходе выполнения.<br /><br /> **Примечание** не задать эту политику `ProgressFeedbackDisabled` так как оно зарезервировано для использования средой выполнения. |`ProgressFeedbackEnabled`|

Каждый планировщик использует собственную политику для планирования задач. Политики, связанные с одним планировщиком, не влияют на поведение других планировщиков. Кроме того, невозможно изменить политику планировщика после создания `Scheduler` объекта.

> [!IMPORTANT]
>  Только политики планировщика используются для управления атрибутами потоков, создаваемых средой выполнения. Не изменяйте сходство или приоритет потоков, создаваемых средой выполнения, поскольку это может привести к неопределенному поведению.

Среда выполнения создает планировщик по умолчанию, если вы не создан явно. Если вы хотите использовать планировщик по умолчанию в приложении, но вы хотите указать политику для этого планировщика, вызовите [Concurrency::Scheduler:: SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) перед планированием параллельной работы. Если вы не вызываете `Scheduler::SetDefaultSchedulerPolicy` метода, среда выполнения использует политику по умолчанию значения из таблицы.

Используйте [сoncurrency::CurrentScheduler:: GetPolicy](reference/currentscheduler-class.md#getpolicy) и [сoncurrency::Scheduler:: GetPolicy](reference/scheduler-class.md#getpolicy) методы для извлечения копии политики планировщика. Значения политики, которые получены из этих методов может отличаться от значения политики, указанные вами при создании планировщика.

## <a name="example"></a>Пример

Чтобы изучить примеры, в которых конкретные политики планировщика используются для контроля поведения планировщика, см. в разделе [как: укажите конкретные политики планировщика](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md) и [как: создание агентов, использовать определенные политики планировщика](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).

## <a name="see-also"></a>См. также

[Планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Практическое руководство. Задание определенных политик планировщика](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)<br/>
[Практическое руководство. Создание агентов, использующих определенные политики планировщика](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)

