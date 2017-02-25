---
title: "Класс Scheduler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::Scheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Scheduler - класс"
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс Scheduler
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Представляет абстракцию для планировщика среды параллелизма.  
  
## Синтаксис  
  
```  
class Scheduler;  
```  
  
## Члены  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор Scheduler::Scheduler](../Topic/Scheduler::Scheduler%20Constructor.md)|Объект класса `Scheduler` можно создавать только с помощью методов фабрики или неявно.|  
|[Деструктор Scheduler::~Scheduler](../Topic/Scheduler::~Scheduler%20Destructor.md)|Объект класса `Scheduler` неявно уничтожается, когда все внешние ссылки на него прекращают существование.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод Scheduler::Attach](../Topic/Scheduler::Attach%20Method.md)|Присоединяет планировщик к контекста вызова.  После выполнения возврата данным методом вызывающий контекст управляется планировщиком и планировщик становится текущим планировщиком.|  
|[Метод Scheduler::Create](../Topic/Scheduler::Create%20Method.md)|Создает новый планировщик, поведение которого описанного параметром `_Policy`, помещает исходную ссылку на планировщик и возвращает указатель на него.|  
|[Метод Scheduler::CreateScheduleGroup](../Topic/Scheduler::CreateScheduleGroup%20Method.md)|Перегружен.  Создает новую группу расписания в планировщике.  Версия, которая принимает параметр `_Placement`, заставляет задачи из вновь созданной группы расписаний стремиться выполняться в расположении, указанном параметром.|  
|[Метод Scheduler::GetNumberOfVirtualProcessors](../Topic/Scheduler::GetNumberOfVirtualProcessors%20Method.md)|Возвращает текущее число виртуальных процессоров для планировщика.|  
|[Метод Scheduler::GetPolicy](../Topic/Scheduler::GetPolicy%20Method.md)|Возвращает копию политики, с которой создан планировщик.|  
|[Метод Scheduler::Id](../Topic/Scheduler::Id%20Method.md)|Возвращает уникальный идентификатор для планировщика.|  
|[Метод Scheduler::IsAvailableLocation](../Topic/Scheduler::IsAvailableLocation%20Method.md)|Определяет, доступно ли данное расположение в планировщике.|  
|[Метод Scheduler::Reference](../Topic/Scheduler::Reference%20Method.md)|Увеличивает значение счетчика ссылок планировщика.|  
|[Метод Scheduler::RegisterShutdownEvent](../Topic/Scheduler::RegisterShutdownEvent%20Method.md)|Приводит к тому, что дескриптору объекта события Windows, переданному в параметре `_Event`, направляется сигнал, когда планировщик завершает работу и удаляет себя.  В момент получения событием сигнала вся работа, запланированная планировщику, завершена.  Через этот метод может быть зарегистрировано несколько событий завершения работы.|  
|[Метод Scheduler::Release](../Topic/Scheduler::Release%20Method.md)|Уменьшает значение счетчика ссылок планировщика.|  
|[Метод Scheduler::ResetDefaultSchedulerPolicy](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md)|Восстанавливает политику по умолчанию планировщика на политику среды выполнения по умолчанию.  В следующий раз, когда будет создан планировщик по умолчанию, он будет использовать параметры политики по умолчанию среды выполнения.|  
|[Метод Scheduler::ScheduleTask](../Topic/Scheduler::ScheduleTask%20Method.md)|Перегружен.  Назначает легкое задание в планировщике.  Облегченная задача будет размещена в группу расписаний, определенной средой выполнения.  Версия, которая принимает параметр `_Placement`, склоняет задачу к выполнению в указанном месте.|  
|[Метод Scheduler::SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)|Позволяет использовать политику определенную пользователем для создания планировщика по умолчанию.  Этот метод может вызываться только когда не существует планировщика по умолчанию внутри процесса.  После установки политики по умолчанию он остается в силе до следующего допустимого вызова к методу `SetDefaultSchedulerPolicy` или [ResetDefaultSchedulerPolicy](../Topic/Scheduler::ResetDefaultSchedulerPolicy%20Method.md).|  
  
## Заметки  
 Планировщик среды параллелизма использует контексты выполнения, которые сопоставляются с контекстами выполнения операционной системы, например поток, для выполнения работы, поставленной в очередь приложением.  В любое время уровень параллелизма выполнения планировщика равен номеру виртуальный процессор, предоставленные ему диспетчером ресурсов.  Виртуальный процессор является абстракцией для обработки ресурсов и сопоставляется с аппаратным потоком в базовой системе.  В данный момент времени только один контекст планировщика может выполняться на виртуальном процессоре.  
  
 Среда параллелизма создаст планировщик по умолчанию на каждый процесс для выполнения параллельной работы.  В дополнение к этому можно создавать собственные экземпляры планировщика и управлять им с помощью этого класса.  
  
## Иерархия наследования  
 `Scheduler`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler Class](../../../parallel/concrt/reference/scheduler-class.md)   
 [Перечисление PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md)   
 [Планировщик задач](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)