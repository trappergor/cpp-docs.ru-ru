---
title: "Группы расписаний | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "группы расписаний"
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Группы расписаний
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом документе описана роль групп расписаний в среде выполнения с параллелизмом. A *Группа планирования* связывает или группы задач, связанных друг с другом. Каждый планировщик имеет одну или несколько групп расписаний. Используйте группы расписаний, когда требуется высокая степень локальности связанных задач, например если группу связанных задач лучше выполнять в одном узле процессора. И наоборот используйте экземпляры планировщика, когда у приложения есть определенные требования к качеству, например, для ограничения объема вычислительных ресурсов, выделенных для набора задач. Дополнительные сведения об экземплярах планировщиков см. в разделе [экземпляров планировщика](../../parallel/concrt/scheduler-instances.md).  
  
> [!TIP]
>  Среда выполнения с параллелизмом предоставляет планировщик по умолчанию, и таким образом не требуется создавать планировщик в приложении. Поскольку планировщик заданий помогает оптимизировать производительность приложений, мы рекомендуем начать с [библиотеки параллельных шаблонов (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) или [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) Если вы новичок в среде выполнения с параллелизмом.  
  
 Каждый `Scheduler` объект имеет группу расписаний по умолчанию для каждого узла планирования. A *узел планирования* сопоставляется топологии базовой системы. Среда выполнения создает один узел планирования для каждого пакета процессора или узла архитектуру неоднородной памяти (NUMA), независимо от числа больше. Если задача не связана с группой расписаний явным образом, планировщик выбирает какой группе для добавления задачи.  
  
  `SchedulingProtocol` Политики планировщика влияет на порядок, в котором планировщиком задач в каждой группе расписаний. Когда `SchedulingProtocol` имеет значение `EnhanceScheduleGroupLocality` (используется по умолчанию), планировщик заданий выбирает следующую задачу из группы расписаний, с которой он работает, когда текущая задача завершается, либо совместно передает. Планировщик заданий осуществляет в текущей группе расписаний для работы перед переходом к следующей доступной группе. И наоборот, если `SchedulingProtocol` имеет значение `EnhanceForwardProgress`, планировщик переходит к следующей группе расписаний после завершения каждой задачи или передачи. Пример, в котором сравниваются эти политики см. в разделе [Практическое руководство: использование групп расписаний в порядке выполнения влияют](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  
 Среда выполнения использует [concurrency::ScheduleGroup](../Topic/ScheduleGroup%20Class.md) класс для представления групп расписаний. Для создания `ScheduleGroup` объекта, вызовите [Concurrency::CurrentScheduler:: createschedulegroup](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md) или [Concurrency::Scheduler:: createschedulegroup](../Topic/Scheduler::CreateScheduleGroup%20Method.md) метод. Среда выполнения использует механизм подсчета ссылок для управления временем существования `ScheduleGroup` объекты, как и в случае с `Scheduler` объектов. При создании `ScheduleGroup` объекта, среда выполнения задает ссылку на один счетчик.  [Concurrency::ScheduleGroup:: Reference](../Topic/ScheduleGroup::Reference%20Method.md) метод увеличивает счетчик ссылок на единицу.  [Concurrency::ScheduleGroup:: Release](../Topic/ScheduleGroup::Release%20Method.md) уменьшает значение счетчика ссылок на единицу.  
  
 Многие типы в среде выполнения с параллелизмом позволяют связать объект с группой расписаний. Например [concurrency::agent](../../parallel/concrt/reference/agent-class.md) классов и классы блока сообщений например [concurrency::unbounded_buffer](../Topic/unbounded_buffer%20Class.md), [concurrency::join](../Topic/join%20Class.md), и параллелизм::[таймера](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d5d4c847-5ad6-4c7f-b35b-d0b6f446d8b4/locales/en-US), предоставляют перегруженные версии конструктора, принимающих `ScheduleGroup` объекта. Среда выполнения использует `Scheduler` объект, связанный с этим `ScheduleGroup` объекта для планирования задачи.  
  
 Можно также использовать [Concurrency::ScheduleGroup:: ScheduleTask](../Topic/ScheduleGroup::ScheduleTask%20Method.md) для планирования упрощенной задачи. Дополнительные сведения об упрощенных задачах см. в разделе [упрощенных задач](../../parallel/concrt/lightweight-tasks.md).  
  
## <a name="example"></a>Пример  
 Пример, в котором используется расписаний групп для управления порядком выполнения задач см. в разделе [Практическое руководство: использование групп расписаний в порядке выполнения влияют](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  
## <a name="see-also"></a>См. также  
 [Планировщик заданий](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Экземпляры планировщика](../../parallel/concrt/scheduler-instances.md)   
 [Практическое руководство: использование групп расписаний для определения порядка выполнения](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)

