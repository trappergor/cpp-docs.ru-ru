---
title: "Класс default_scheduler_exists | Microsoft Docs"
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
  - "concrt/concurrency::default_scheduler_exists"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "default_scheduler_exists - класс"
ms.assetid: f6e575e2-4e0f-455a-9e06-54f462ce0c1c
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс default_scheduler_exists
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, которое выдается, когда метод `Scheduler::SetDefaultSchedulerPolicy` вызывается, когда планировщик по умолчанию уже существует внутри процесса.  
  
## Синтаксис  
  
```  
class default_scheduler_exists : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор default\_scheduler\_exists::default\_scheduler\_exists](../Topic/default_scheduler_exists::default_scheduler_exists%20Constructor.md)|Перегружен.  Создает объект `default_scheduler_exists`.|  
  
## Иерархия наследования  
 `exception`  
  
 `default_scheduler_exists`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Метод Scheduler::SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)