---
title: "Класс task_completion_event | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppltasks/concurrency::task_completion_event"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_completion_event - класс"
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Класс task_completion_event
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `task_completion_event` позволяет, чтобы отложить выполнение задачи до тех пор, пока не будет выполняться условие, или запустить задачу в ответ на внешнее событие.  
  
## Синтаксис  
  
```  
template<  
   typename _ResultType  
>  
class task_completion_event;  
  
template<>  
class task_completion_event<void>;  
```  
  
#### Параметры  
 `_ResultType`  
 Тип результата этого класса `task_completion_event`.  
  
 `T`  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор task\_completion\_event::task\_completion\_event](../Topic/task_completion_event::task_completion_event%20Constructor.md)|Создает объект `task_completion_event`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод task\_completion\_event::set](../Topic/task_completion_event::set%20Method.md)|Перегружен.  Задает событие завершения задачи.|  
|[Метод task\_completion\_event::set\_exception](../Topic/task_completion_event::set_exception%20Method.md)|Перегружен.  Распространяет исключение на всем задачи, связанные с этим событием.|  
  
## Заметки  
 Используйте задачу, созданную из события завершения задачи, когда сценарий требует создания задачи, которая будет завершаться и, следовательно, иметь запланированные продолжения для выполнения в некоторый момент времени в будущем.  Аргумент `task_completion_event` должен иметь тот же тип, что и создаваемая задача, и вызов метода задания для объекта завершения задачи со значением этого типа приведет к завершению связанной задачи, причем это значение будет предоставлено продолжениям в качестве результата.  
  
 Если событие завершения задачи никогда не возникает, будут отменены все задачи, созданные из нее, при ее разрушении.  
  
 `task_completion_event` ведет себя подобно интеллектуальному указателю, и его следует передавать по значению.  
  
## Иерархия наследования  
 `task_completion_event`  
  
## Требования  
 **Заголовок:** ppltasks.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task Class](http://msdn.microsoft.com/ru-ru/5389e8a5-5038-40b6-844a-55e9b58ad35f)