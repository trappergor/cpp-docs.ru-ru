---
title: "Класс nested_scheduler_missing_detach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::nested_scheduler_missing_detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nested_scheduler_missing_detach - класс"
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс nested_scheduler_missing_detach
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, которое возникает, когда среда выполнения параллелизма обнаруживает, что вы не вызвали метод `CurrentScheduler::Detach` на контекст, который присоединен к второй планировщик через метод `Attach` объекта `Scheduler`.  
  
## Синтаксис  
  
```  
class nested_scheduler_missing_detach : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор nested\_scheduler\_missing\_detach::nested\_scheduler\_missing\_detach](../Topic/nested_scheduler_missing_detach::nested_scheduler_missing_detach%20Constructor.md)|Перегружен.  Создает объект `nested_scheduler_missing_detach`.|  
  
## Заметки  
 Это исключение вызывается, только когда один планировщик вложен внутрь другого путем вызова метода `Attach` объекта `Scheduler` объекта в контексте, которым уже владеет или который прикреплен к другому планировщику.  Среда параллелизма по возможности выдает это исключение, если может обнаружить сценарий как средство, облегчающее поиск неполадки.  Не каждый экземпляр игнорирования для вызова метода `CurrentScheduler::Detach` гарантированно создает это исключение.  
  
## Иерархия наследования  
 `exception`  
  
 `nested_scheduler_missing_detach`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс Scheduler](../../../parallel/concrt/reference/scheduler-class.md)   
 [Метод CurrentScheduler::Detach](../Topic/CurrentScheduler::Detach%20Method.md)   
 [Метод Scheduler::Attach](../Topic/Scheduler::Attach%20Method.md)