---
title: "Класс SchedulerPolicy | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::SchedulerPolicy"
  - "concrtrm/concurrency::SchedulerPolicy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SchedulerPolicy - класс"
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
caps.latest.revision: 22
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс SchedulerPolicy
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `SchedulerPolicy` содержит набор пар "ключ—значение", одна для каждого элемента политики, контролирующего поведение экземпляра планировщика.  
  
## Синтаксис  
  
```  
class SchedulerPolicy;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор SchedulerPolicy::SchedulerPolicy](../Topic/SchedulerPolicy::SchedulerPolicy%20Constructor.md)|Перегружен.  Создает новую политику планировщик и заполняет ее значениями для [ключей политики](../Topic/PolicyElementKey%20Enumeration.md), поддерживаемых планировщиками среды параллелизма и диспетчером ресурсов.|  
|[Деструктор SchedulerPolicy::~SchedulerPolicy](../Topic/SchedulerPolicy::~SchedulerPolicy%20Destructor.md)|Уничтожает политику планировщика.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод SchedulerPolicy::GetPolicyValue](../Topic/SchedulerPolicy::GetPolicyValue%20Method.md)|Извлекает значение ключа политики, предоставленного в виде параметра `_Key`.|  
|[Метод SchedulerPolicy::SetConcurrencyLimits](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)|Одновременно устанавливает для объекта `SchedulerPolicy` политики `MaxConcurrency` и `MinConcurrency`.|  
|[Метод SchedulerPolicy::SetPolicyValue](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)|Задает значение ключа политики предоставленного в виде параметра `_Key` и возвращает старое значение.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Оператор SchedulerPolicy::operator\=](../Topic/SchedulerPolicy::operator=%20Operator.md)|Назначает политику планировщика из другой политики планировщика.|  
  
## Заметки  
 Для получения дополнительных сведений о политиках, которые могут управляться с помощью класса `SchedulerPolicy`, см. раздел [Перечисление PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md).  
  
## Иерархия наследования  
 `SchedulerPolicy`  
  
## Требования  
 **Заголовок:** concrt.h, concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Перечисление PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md)   
 [Класс CurrentScheduler](../Topic/CurrentScheduler%20Class.md)   
 [Класс Scheduler](../../../parallel/concrt/reference/scheduler-class.md)   
 [Планировщик задач](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)