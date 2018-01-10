---
title: "Группы расписаний | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: schedule groups
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a61566878adc539af21e1645844eff27c5a8aec0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="schedule-groups"></a>Группы расписаний
В этом документе описывается роль групп расписаний в среде выполнения с параллелизмом. Объект *группы расписаний* связывает или группы задач, связанных друг с другом. Каждый планировщик имеет один или несколько групп расписаний. Используйте группы расписаний, когда требуется высокая степень локальности связанных задач, например если группу связанных задач лучше выполнять в одном узле процессора. И наоборот используйте экземпляры планировщика, когда приложение получает определенные требования к качеству, например, если требуется ограничить объем вычислительных ресурсов, выделенных для набора задач. Дополнительные сведения об экземплярах планировщиков см. в разделе [экземпляры планировщика](../../parallel/concrt/scheduler-instances.md).  
  
> [!TIP]
>  Среда выполнения с параллелизмом предоставляет планировщик по умолчанию, и таким образом не требуется создавать планировщик в приложении. Поскольку планировщик задач помогает оптимизировать производительность приложений, рекомендуется начать с [библиотеки параллельных шаблонов (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) или [библиотеки асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md) при наличии новые и среда выполнения с параллелизмом.  
  
 Каждый `Scheduler` объект имеет группу расписаний по умолчанию для каждого узла планирования. Объект *узел планирования* сопоставляется топологии базовой системы. Среда выполнения создает один узел планирования для каждого пакета процессора или узла архитектуру неоднородной памяти (NUMA), выбирая значение больше. Если задача не связана с группой расписаний явным образом, то планировщик выбирает какую группу для добавления задачи.  
  
 `SchedulingProtocol` Политики планировщика влияет на порядок, в котором планировщиком задач в каждой группе расписаний. Когда `SchedulingProtocol` задано значение `EnhanceScheduleGroupLocality` (используется по умолчанию), планировщик заданий выбирает следующую задачу из группы расписаний, с которой он работает, когда завершается текущая задача, либо совместно передает. Планировщик задач выполняет поиск в текущей группе расписаний для рабочего перед переходом к следующей доступной группы. И наоборот, если `SchedulingProtocol` равно `EnhanceForwardProgress`, планировщик переходит к следующей группе расписаний после завершения каждой задачи, или передачи. Пример, в котором сравниваются эти политики см. в разделе [как: используйте группы расписаний для влияние порядка выполнения](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  

 Среда выполнения использует [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) класс для представления групп расписаний. Для создания `ScheduleGroup` , вызовите [Concurrency::CurrentScheduler:: createschedulegroup](reference/currentscheduler-class.md#createschedulegroup) или [Concurrency::Scheduler:: createschedulegroup](reference/scheduler-class.md#createschedulegroup) метод. Среда выполнения использует механизм подсчета ссылок для управления временем существования `ScheduleGroup` объектов, как и в случае с `Scheduler` объектов. При создании `ScheduleGroup` объекта, среда выполнения задает ссылку на один счетчик. [Concurrency::ScheduleGroup:: Reference](reference/schedulegroup-class.md#reference) метод увеличивает счетчик ссылок на единицу. [Concurrency::ScheduleGroup:: Release](reference/schedulegroup-class.md#release) метод уменьшает значение счетчика ссылок на единицу.  
  
 Многие типы в среде выполнения с параллелизмом позволяют связать объект с группой расписаний. Например [concurrency::agent](../../parallel/concrt/reference/agent-class.md) класса и сообщения блока классов, таких как [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency::join](../../parallel/concrt/reference/join-class.md)и параллелизм::[ таймер](reference/timer-class.md), предоставляют перегруженные версии конструктора, принимающих `ScheduleGroup` объекта. Среда выполнения использует `Scheduler` объекта, связанного с данным `ScheduleGroup` объекта для планирования задачи.  
  
 Можно также использовать [Concurrency::ScheduleGroup:: ScheduleTask](reference/schedulegroup-class.md#scheduletask) для планирования упрощенной задачи. Дополнительные сведения об упрощенных задачах см. в разделе [упрощенных задач](../../parallel/concrt/lightweight-tasks.md).  

  
## <a name="example"></a>Пример  
 Пример, в котором используется расписаний групп для управления порядком выполнения задач см. в разделе [как: используйте группы расписаний для влияние порядка выполнения](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  
## <a name="see-also"></a>См. также  
 [Планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Экземпляры планировщика](../../parallel/concrt/scheduler-instances.md)   
 [Практическое руководство. Использование групп планирования для определения порядка выполнения](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)

