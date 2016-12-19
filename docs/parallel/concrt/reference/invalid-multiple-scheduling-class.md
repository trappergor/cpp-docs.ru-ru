---
title: "Класс invalid_multiple_scheduling | Microsoft Docs"
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
  - "concrt/concurrency::invalid_multiple_scheduling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_multiple_scheduling - класс"
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс invalid_multiple_scheduling
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, возникающее когда объект `task_handle` запланирован несколько раз с помощью метода `run` объекта `task_group` или `structured_task_group` без промежуточных вызовов метода `wait` или `run_and_wait`.  
  
## Синтаксис  
  
```  
class invalid_multiple_scheduling : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор invalid\_multiple\_scheduling::invalid\_multiple\_scheduling](../Topic/invalid_multiple_scheduling::invalid_multiple_scheduling%20Constructor.md)|Перегружен.  Создает объект `invalid_multiple_scheduling`.|  
  
## Иерархия наследования  
 `exception`  
  
 `invalid_multiple_scheduling`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс task\_handle](../../../parallel/concrt/reference/task-handle-class.md)   
 [Класс task\_group](../Topic/task_group%20Class.md)   
 [Метод task\_group::run](../Topic/task_group::run%20Method.md)   
 [Метод task\_group::wait](../Topic/task_group::wait%20Method.md)   
 [Метод task\_group::run\_and\_wait](../Topic/task_group::run_and_wait%20Method.md)   
 [Класс structured\_task\_group](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [Метод structured\_task\_group::run](../Topic/structured_task_group::run%20Method.md)   
 [Метод structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md)   
 [Метод structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md)