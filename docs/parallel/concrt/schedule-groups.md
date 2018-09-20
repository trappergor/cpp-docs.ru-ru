---
title: Группы расписаний | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- schedule groups
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4fa61772af96ba0d2602ff42a6a43b2b3a13a4e6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385903"
---
# <a name="schedule-groups"></a>Группы расписаний

В этом документе описывается роль групп расписаний в среде выполнения с параллелизмом. Объект *группы расписаний* связывает или групп, задач, связанных друг с другом. Каждый планировщик имеет один или несколько групп расписаний. Используйте группы расписаний, когда требуется высокая степень локальности связанных задач, например если группу связанных задач лучше выполнять в одном узле процессора. И наоборот используйте экземпляры планировщика, когда приложение имеет определенные требования к качеству, например, если вы хотите ограничить объем вычислительных ресурсов, выделенных для набора задач. Дополнительные сведения о экземпляры планировщика, см. в разделе [экземпляры планировщика](../../parallel/concrt/scheduler-instances.md).

> [!TIP]
>  Среда выполнения с параллелизмом предоставляет планировщик по умолчанию, и таким образом не требуется создавать планировщик в приложении. Поскольку планировщик задач помогает оптимизировать производительность приложений, мы рекомендуем начать с [библиотеки параллельных шаблонов (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) или [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) при наличии создать среду выполнения с параллелизмом.

Каждый `Scheduler` объект имеет группу расписаний по умолчанию для каждого узла планирования. Объект *узел планирования* сопоставляется топологии базовой системы. Среда выполнения создает один узел планирования для каждого пакета процессора или узел архитектура неоднородной памяти (NUMA), какое из этих значение больше. Если задача не связана с группой расписаний явным образом, планировщик выбирает какую группу добавляется задача.

`SchedulingProtocol` Политики планировщика влияет на порядок, в котором планировщиком задач в каждой группе расписаний. Когда `SchedulingProtocol` присваивается `EnhanceScheduleGroupLocality` (это значение по умолчанию), планировщик выбирает следующую задачу из группы расписаний, он работает, когда текущая задача завершается или выполняет совместную передачу. Планировщик задач выполняет поиск текущей группы расписаний для рабочего, прежде чем перейти к следующей группе доступны. И наоборот, если `SchedulingProtocol` присваивается `EnhanceForwardProgress`, планировщик переходит к следующей группе расписаний после завершения каждой задачи, или передачи. Пример, в котором сравниваются эти политики, см. в разделе [как: используйте группы расписаний для влияют на порядок выполнения](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

Среда выполнения использует [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) класс для представления групп расписаний. Чтобы создать `ScheduleGroup` , вызовите [Concurrency::CurrentScheduler:: createschedulegroup](reference/currentscheduler-class.md#createschedulegroup) или [Concurrency::Scheduler:: createschedulegroup](reference/scheduler-class.md#createschedulegroup) метод. Среда выполнения использует механизм подсчета ссылок для управления временем существования `ScheduleGroup` объектов, так же, как с помощью `Scheduler` объектов. При создании `ScheduleGroup` объекта, среда выполнения задает ссылку на один счетчик. [Concurrency::ScheduleGroup:: Reference](reference/schedulegroup-class.md#reference) метод увеличивает счетчик ссылок на единицу. [Concurrency::ScheduleGroup:: Release](reference/schedulegroup-class.md#release) метод уменьшает значение счетчика ссылок на единицу.

Многие типы в среде выполнения с параллелизмом позволяют связать объект с группой расписаний. Например [concurrency::agent](../../parallel/concrt/reference/agent-class.md) классы блок класса и сообщения, такие как [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency::join](../../parallel/concrt/reference/join-class.md), параллелизма и::[ таймер](reference/timer-class.md), предоставляют перегруженные версии конструктора, принимающих `ScheduleGroup` объекта. Среда выполнения использует `Scheduler` объект, связанный с данным `ScheduleGroup` объекта для планирования задачи.

Можно также использовать [Concurrency::ScheduleGroup:: ScheduleTask](reference/schedulegroup-class.md#scheduletask) метод для планирования упрощенной задачи. Дополнительные сведения об упрощенных задач см. в разделе [упрощенных задач](../../parallel/concrt/lightweight-tasks.md).

## <a name="example"></a>Пример

Пример, что используются группы для управления порядком выполнения задач расписаний, см. в разделе [как: используйте группы расписаний для влияют на порядок выполнения](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

## <a name="see-also"></a>См. также

[Планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Экземпляры планировщика](../../parallel/concrt/scheduler-instances.md)<br/>
[Практическое руководство. Использование групп планирования для определения порядка выполнения](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)

