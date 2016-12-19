---
title: "Класс structured_task_group | Microsoft Docs"
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
  - "ppl/concurrency::structured_task_group"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "structured_task_group - класс"
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс structured_task_group
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `structured_task_group` представляет высокоструктурированную коллекцию параллельной работы.  Отдельные параллельные задачи можно ставить в очередь `structured_task_group` с помощью объектов `task_handle` и дождаться их завершения или отменить группу задач до завершения их выполнения, что прервет все задачи, которые не начали выполнение.  
  
## Синтаксис  
  
```  
class structured_task_group;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор structured\_task\_group::structured\_task\_group](../Topic/structured_task_group::structured_task_group%20Constructor.md)|Перегружен.  Создает новый объект `structured_task_group`.|  
|[Деструктор structured\_task\_group::~structured\_task\_group](../Topic/structured_task_group::~structured_task_group%20Destructor.md)|Удаляет объект `structured_task_group`.  Ожидается вызов метода `wait` или `run_and_wait` на объект до выполнения деструктора, если деструктор не выполняется в результате очистки стека из\-за исключения.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод structured\_task\_group::cancel](../Topic/structured_task_group::cancel%20Method.md)|Пытается отменить поддерево работ, имеющее корень в данной группе задач.  Все задачи, запланированные в группе задач, по возможности отменяются транзитивно.|  
|[Метод structured\_task\_group::is\_canceling](../Topic/structured_task_group::is_canceling%20Method.md)|Сообщает вызывающей стороне, находится ли группа задач в данный момент в состоянии отмены.  Это не обязательно означает, что метод `cancel` был вызван на объект `structured_task_group` \(хотя это определенно позволяет этому метод вернуть `true`\).  Может быть,что объект `structured_task_group` выполняется встроено и группа задач выше в дереве работы была отменена.  В подобных случаях там, где среда выполнения может заранее определить, что отмена будет передаваться через этот объект `structured_task_group`, будет возвращено значение `true`.|  
|[Метод structured\_task\_group::run](../Topic/structured_task_group::run%20Method.md)|Перегружен.  Назначает задание на объекте `structured_task_group`.  Вызывающий объект управляет временем жизни переданного в параметр `_Task_handle` объекта `task_handle`.  Версия, которая принимает параметр `_Placement`, заставляет задачу стремиться выполняться в расположении, указанном параметром.|  
|[Метод structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md)|Перегружен.  Планирует задачу для выполнения встроено в вызывающий контекст с помощью объекта `structured_task_group` для поддержки полной отмены.  Если объект `task_handle` передается как параметр в `run_and_wait`, вызывающий объект отвечает за управление временем жизни объекта `task_handle`.  Функция затем ожидает до тех пор, пока вся работа объекта `structured_task_group` будет завершена или отменена.|  
|[Метод structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md)|Ожидает до тех пор, пока вся работа над `structured_task_group` не завершена или отменена.|  
  
## Заметки  
 Существует ряд серьезных ограничений, которые накладываются на использование объекта `structured_task_group` с целью повышения производительности:  
  
-   Один объект `structured_task_group` не может использоваться несколькими потоками.  Все операции для объекта `structured_task_group` должны быть выполнены потоком, создавшим объект.  Два исключения из этого правила являются функциями члена `cancel` и `is_canceling`.  Объект может не быть в списке захвата лямбда\-выражения и может использоваться внутри задачи, если задача не является одной из операций отмены.  
  
-   Все задания, назначенные объекту `structured_task_group`, планируются с помощью объектов `task_handle`, для которых необходимо явно управлять временем жизни.  
  
-   Несколько групп могут использоваться только в абсолютно вложенных порядке.  Если объявлено два объекта `structured_task_group`, второй объявленный \(внутренний\) должен разрушиться перед вызовов любого метода, кроме `cancel` и `is_canceling`, на первый \(внешний\).  Это условие истинно как в случае простого объявления нескольких объектов `structured_task_group` объектов внутри одного и того же или функционально вложенных областей, а также в случае, если задача, которое было поставлена в очередь в `structured_task_group` через методы `run` или `run_and_wait`.  
  
-   В отличие от общего класса `task_group`, все состояния в классе `structured_task_group` являются окончательными.  После помещения задач в очередь группы и ожидания их завершения нельзя использовать ту же группу снова.  
  
 Для получения дополнительной информации см. [Параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## Иерархия наследования  
 `structured_task_group`  
  
## Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс task\_group](../Topic/task_group%20Class.md)   
 [Класс task\_handle](../../../parallel/concrt/reference/task-handle-class.md)