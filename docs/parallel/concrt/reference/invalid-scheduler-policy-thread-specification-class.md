---
title: "Класс invalid_scheduler_policy_thread_specification | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::invalid_scheduler_policy_thread_specification"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_scheduler_policy_thread_specification - класс"
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс invalid_scheduler_policy_thread_specification
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, которое генерируется, когда сделана попытка установить ограничения параллелизма объекта `SchedulerPolicy` таким образом, что значение ключа `MinConcurrency` меньше, чем значение ключа `MaxConcurrency`.  
  
## Синтаксис  
  
```  
class invalid_scheduler_policy_thread_specification : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор invalid\_scheduler\_policy\_thread\_specification::invalid\_scheduler\_policy\_thread\_specification](../Topic/invalid_scheduler_policy_thread_specification::invalid_scheduler_policy_thread_specification%20Constructor.md)|Перегружен.  Создает объект `invalid_scheduler_policy_value`.|  
  
## Иерархия наследования  
 `exception`  
  
 `invalid_scheduler_policy_thread_specification`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс SchedulerPolicy](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [Перечисление PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md)   
 [Метод SchedulerPolicy::SetConcurrencyLimits](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)