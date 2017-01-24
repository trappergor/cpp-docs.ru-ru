---
title: "Класс task_handle | Microsoft Docs"
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
  - "ppl/concurrency::task_handle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_handle - класс"
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
caps.latest.revision: 23
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс task_handle
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `task_handle` представляет отдельный параллельный рабочий элемент.  Он инкапсулирует инструкции и данные, необходимые для выполнения части работы.  
  
## Синтаксис  
  
```  
template<  
   typename _Function  
>  
class task_handle : public ::Concurrency::details::_UnrealizedChore;  
```  
  
#### Параметры  
 `_Function`  
 Тип объекта функции, который будет вызываться для выполнения работы, представленной объектом `task_handle`.  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор task\_handle::task\_handle](../Topic/task_handle::task_handle%20Constructor.md)|Создает новый объект `task_handle`.  Работа задачи выполняется путем вызова функции, указанной в качестве параметра конструктора.|  
|[Деструктор task\_handle::~task\_handle](../Topic/task_handle::~task_handle%20Destructor.md)|Уничтожает объект `task_handle`.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор task\_handle::operator\(\)](../Topic/task_handle::operator\(\)%20Operator.md)|Оператор вызова функции, который среда выполнения вызывает для выполнения работ дескриптора задачи.|  
  
## Заметки  
 Объекты `task_handle` могут использоваться в сочетании с `structured_task_group` или более общим объектом `task_group` для разделения работы в параллельные задачи.  Для получения дополнительной информации см. [Параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Обратите внимание, что создатель объекта `task_handle` ответственен за поддержание времени существования, созданного объекта `task_handle` до тех пор, пока он больше не требуется средой параллелизма.  Как правило это означает, что объект `task_handle` не должен разрушаться до вызова метода `wait` или `run_and_wait` `task_group` или `structured_task_group`, в которой он находится в очереди.  
  
 Объекты `task_handle` обычно используются в сочетании с лямбда\-выражения C\+\+.  Поскольку вы не знаете истинный тип лямбда\-выражение, функция [make\_task](../Topic/make_task%20Function.md) обычно используется для создания объекта `task_handle`.  
  
 Среда выполнения создает копию рабочей функции, передаваемой объекту `task_handle`.  Следовательно, любые изменения, происходящие в объекте функции, передаваемом объекту `task_handle`, не отобразятся в пользовательской копии объекта функции.  
  
## Иерархия наследования  
 `task_handle`  
  
## Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс task\_group](../Topic/task_group%20Class.md)   
 [Класс structured\_task\_group](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [Функция make\_task](../Topic/make_task%20Function.md)   
 [Метод task\_group::run](../Topic/task_group::run%20Method.md)   
 [Метод task\_group::wait](../Topic/task_group::wait%20Method.md)   
 [Метод task\_group::run\_and\_wait](../Topic/task_group::run_and_wait%20Method.md)   
 [Метод structured\_task\_group::run](../Topic/structured_task_group::run%20Method.md)   
 [Метод structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md)   
 [Метод structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md)