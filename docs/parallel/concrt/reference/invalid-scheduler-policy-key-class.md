---
title: "Класс invalid_scheduler_policy_key | Microsoft Docs"
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
  - "concrt/concurrency::invalid_scheduler_policy_key"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_scheduler_policy_key - класс"
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс invalid_scheduler_policy_key
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, которое выдается каждый раз, когда конструктору объекта `SchedulerPolicy` передан неправильный или неизвестный ключ или метод `SetPolicyValue` объекта `SchedulerPolicy` получил ключ, который должен быть изменен через другие средства, такие как метод `SetConcurrencyLimits`.  
  
## Синтаксис  
  
```  
class invalid_scheduler_policy_key : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор invalid\_scheduler\_policy\_key::invalid\_scheduler\_policy\_key](../Topic/invalid_scheduler_policy_key::invalid_scheduler_policy_key%20Constructor.md)|Перегружен.  Создает объект `invalid_scheduler_policy_key`.|  
  
## Иерархия наследования  
 `exception`  
  
 `invalid_scheduler_policy_key`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс SchedulerPolicy](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [Перечисление PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md)   
 [Метод SchedulerPolicy::SetPolicyValue](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)   
 [Метод SchedulerPolicy::SetConcurrencyLimits](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)