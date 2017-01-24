---
title: "Класс missing_wait | Microsoft Docs"
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
  - "concrt/concurrency::missing_wait"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "missing_wait - класс"
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс missing_wait
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, которое выдается, когда имеются задачи, по\-прежнему запланированные объекту `task_group` или `structured_task_group` во время выполнения деструктора этого объекта.  Никогда не будет создано это исключение, если деструктор достигается из\-за очистки стека в результате исключения.  
  
## Синтаксис  
  
```  
class missing_wait : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор missing\_wait::missing\_wait](../Topic/missing_wait::missing_wait%20Constructor.md)|Перегружен.  Создает объект `missing_wait`.|  
  
## Заметки  
 Если отсутствует поток исключения, вы должны вызвать метод `wait` или метод `run_and_wait` объекта `task_group` или `structured_task_group` до разрешения выполнения уничтожения этим объектом.  Среда выполнения выдает исключение как показатель того, что вы забыли вызывать метод `wait` или `run_and_wait`.  
  
## Иерархия наследования  
 `exception`  
  
 `missing_wait`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс task\_group](../Topic/task_group%20Class.md)   
 [Метод task\_group::wait](../Topic/task_group::wait%20Method.md)   
 [Метод task\_group::run\_and\_wait](../Topic/task_group::run_and_wait%20Method.md)   
 [Класс structured\_task\_group](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [Метод structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md)   
 [Метод structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md)