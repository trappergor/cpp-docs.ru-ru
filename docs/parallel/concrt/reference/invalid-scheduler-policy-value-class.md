---
title: "Класс invalid_scheduler_policy_value | Microsoft Docs"
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
  - "concrt/concurrency::invalid_scheduler_policy_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_scheduler_policy_value - класс"
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс invalid_scheduler_policy_value
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, которое выдается, когда ключу политики объекта `SchedulerPolicy` присвоено недопустимое значение для этого ключа.  
  
## Синтаксис  
  
```  
class invalid_scheduler_policy_value : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор invalid\_scheduler\_policy\_value::invalid\_scheduler\_policy\_value](../Topic/invalid_scheduler_policy_value::invalid_scheduler_policy_value%20Constructor.md)|Перегружен.  Создает объект `invalid_scheduler_policy_value`.|  
  
## Иерархия наследования  
 `exception`  
  
 `invalid_scheduler_policy_value`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс SchedulerPolicy](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [Перечисление PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md)   
 [Метод SchedulerPolicy::SetPolicyValue](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)   
 [Метод SchedulerPolicy::SetConcurrencyLimits](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)