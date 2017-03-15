---
title: "Политики планировщика | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "политики планировщика"
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Политики планировщика
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом документе описана роль политик планировщика в среде выполнения с параллелизмом.  *Политика планировщика* определяет стратегию, которую планировщик использует при управлении задачами.  Например, рассмотрим приложение, которое требует выполнение некоторых задач с `THREAD_PRIORITY_NORMAL` и других задач с `THREAD_PRIORITY_HIGHEST`.  Можно создать два экземпляра планировщика: один задает политику `ContextPriority` `THREAD_PRIORITY_NORMAL`, а второй определяет ту же политику как `THREAD_PRIORITY_HIGHEST`.  
  
 Использование политики планировщика позволяет разделять доступные ресурсы для обработки и назначать каждому планировщику фиксированный набор ресурсов.  Например, рассмотрим параллельный алгоритм, который невозможно использовать более чем с четырьмя процессорами.  Можно создать политику планировщика, которая не позволяет задачам использовать более четырех процессоров одновременно.  
  
> [!TIP]
>  Среда выполнения с параллелизмом предоставляет планировщик по умолчанию.  Поэтому не следует создать его в приложении.  Так как планировщик заданий помогает оптимизировать производительность приложений, рекомендуется начать с раздела [Библиотека параллельных шаблонов](../../parallel/concrt/parallel-patterns-library-ppl.md) или [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md), если вы не знакомы со средой выполнения с параллелизмом.  
  
 При использовании метода [concurrency::CurrentScheduler::Create](../Topic/CurrentScheduler::Create%20Method.md), [concurrency::Scheduler::Create](../Topic/Scheduler::Create%20Method.md) или [concurrency::Scheduler::SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md) для создания экземпляра планировщика следует предоставить объект [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md), содержащий набор пар ключ\-значение, определяющих поведение планировщика.  Конструктор `SchedulerPolicy` принимает переменное число аргументов.  Первый аргумент — количество элементов политики, которые собирается задать пользователь.  Остальные аргументы представляют собой пары "ключ\-значение" для каждого элемента политики.  В следующем примере создается объект `SchedulerPolicy`, задающий три элемента политики.  Среда выполнения использует для незаданных ключей политики значения по умолчанию.  
  
 [!CODE [concrt-scheduler-policy#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-scheduler-policy#2)]  
  
 Перечисление [concurrency::PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md) определяет ключи политики, связанные с планировщиком заданий.  В следующей таблице описаны ключи политики и значения по умолчанию, используемые средой выполнения для каждого из них.  
  
|Ключ политики|Описание|Значение по умолчанию|  
|-------------------|--------------|---------------------------|  
|`SchedulerKind`|Значение [concurrency::SchedulerType](../Topic/SchedulerType%20Enumeration.md), задающее тип потоков для планирования задач.|`ThreadScheduler` \(использование стандартных потоков\)  Это единственное допустимое значение для этого ключа.|  
|`MaxConcurrency`|Значение `unsigned int`, задающее максимальное количество ресурсов параллелизма, которые используются планировщиком.|[concurrency::MaxExecutionResources](../Topic/MaxExecutionResources%20Constant.md)|  
|`MinConcurrency`|Значение `unsigned int`, задающее минимальное количество ресурсов параллелизма, которые используются планировщиком.|`1`|  
|`TargetOversubscriptionFactor`|Значение `unsigned int`, задающее, сколько потоков необходимо выделить каждому ресурсу для обработки.|`1`|  
|`LocalContextCacheSize`|Значение `unsigned int`, задающее максимальное число контекстов, которые можно кэшировать в локальной очереди каждого виртуального процессора.|`8`|  
|`ContextStackSize`|Значение `unsigned int`, задающее размер стека \(в килобайтах\), который необходимо зарезервировать для каждого контекста.|`0` \(использовать размер стека по умолчанию\)|  
|`ContextPriority`|Значение `int`, задающее потоковый приоритет каждого контекста.  Это может быть любое значение, которое можно передать [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) или `INHERIT_THREAD_PRIORITY`.|`THREAD_PRIORITY_NORMAL`|  
|`SchedulingProtocol`|Значение [concurrency::SchedulingProtocolType](../Topic/SchedulingProtocolType%20Enumeration.md), задающее используемый алгоритм планирования.|`EnhanceScheduleGroupLocality`|  
|`DynamicProgressFeedback`|Значение [concurrency::DynamicProgressFeedbackType](../Topic/DynamicProgressFeedbackType%20Enumeration.md), задающее, нужно ли перераспределять ресурсы в соответствии со статистическими данными о ходе выполнения.<br /><br /> **Примечание** Не устанавливайте этой политике значение `ProgressFeedbackDisabled`, поскольку оно зарезервировано для использования средой выполнения.|`ProgressFeedbackEnabled`|  
  
 Каждый планировщик использует собственную политику для планирования задач.  Политики, связанные с одним планировщиком, не влияют на поведение других планировщиков.  Кроме того, невозможно изменить политику планировщика после создания объекта `Scheduler`.  
  
> [!IMPORTANT]
>  Для управления атрибутами потоков, создаваемых средой выполнения, следует использовать только политики планировщиков.  Не изменяйте сходство или приоритет потоков, созданных средой выполнения, поскольку это приводит к неопределенному поведению.  
  
 Среда выполнения с параллелизмом создает планировщик по умолчанию, если он не создан явно.  Если вы хотите использовать в приложении планировщик по умолчанию, но при этом ему нужно задать политику, вызовите метод [concurrency::Scheduler::SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md) перед планированием параллельной работы.  Если не вызывается метод `Scheduler::SetDefaultSchedulerPolicy`, среда выполнения использует значения политики по умолчанию из таблицы.  
  
 Для извлечения копии политики планировщика необходимо использовать методы [concurrency::CurrentScheduler::GetPolicy](../Topic/CurrentScheduler::GetPolicy%20Method.md) и [concurrency::Scheduler::GetPolicy](../Topic/Scheduler::GetPolicy%20Method.md).  Значения политики, полученные от этих методов, могут отличаться от значений политики, задаваемых при создании планировщика.  
  
## Пример  
 Примеры, в которых конкретные политики планировщика используются для контроля поведения планировщика, см. в разделах [Практическое руководство. Задание определенных политик планировщика](../Topic/How%20to:%20Specify%20Specific%20Scheduler%20Policies.md) и [Практическое руководство. Создание агентов, использующих определенные политики планировщика](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).  
  
## См. также  
 [Планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Практическое руководство. Задание определенных политик планировщика](../Topic/How%20to:%20Specify%20Specific%20Scheduler%20Policies.md)   
 [Практическое руководство. Создание агентов, использующих определенные политики планировщика](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)