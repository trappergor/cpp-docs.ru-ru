---
title: "Класс task (среда выполнения с параллелизмом) | Microsoft Docs"
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
  - "ppltasks/concurrency::task"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task - класс"
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс task (среда выполнения с параллелизмом)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс библиотеки параллельных шаблонов \(PPL\) `task`.  Объект `task` представляет работу, которую можно выполнять асинхронно, и одновременно с другими задачи и параллельной работой, созданной параллельными алгоритмами среды выполнения с параллелизмом.  Он предоставляет результат типа `_ResultType` при успешном завершении.  Задачи типа `task<void>` не дают никакого результата.  Задачу можно подождать и отменить независимо от любых других задач.  Его также можно составить с другими задачами с помощью продолжений\(`then`\) и соединения\(`when_all`\) и шаблонов выбора \(`when_any`\).  
  
## Синтаксис  
  
```  
template <  
   typename _Type  
>  
class task;  
  
template <>  
class task<void>;  
  
template<  
   typename _ReturnType  
>  
class task;  
```  
  
#### Параметры  
 `_Type`  
 `T`  
 `_ReturnType`  
 Тип результата этой задачи.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Name|Описание|  
|----------|--------------|  
|`result_type`|Тип результата, создаваемого объектом этого класса.|  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор task::task](../Topic/task::task%20Constructor.md)|Перегружен.  Создает объект `task`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод task::get](../Topic/task::get%20Method.md)|Перегружен.  Возвращает результат, созданный этой задачей.  Если задача не находится в конечном состоянии, вызов `get` будет ожидать завершения задачи.  Этот метод не возвращает значение при вызове для задачи с параметром `result_type`, имеющим значение `void`.|  
|[Метод task::is\_apartment\_aware](../Topic/task::is_apartment_aware%20Method.md)|Определяет, распаковывает ли задача интерфейс среды выполнения Windows `IAsyncInfo` или происходит от такой задачи.|  
|[Метод task::is\_done \(среда выполнения с параллелизмом\)](../Topic/task::is_done%20Method%20\(Concurrency%20Runtime\).md)|Определяет, выполнена ли задача.|  
|[Метод task::scheduler \(среда выполнения с параллелизмом\)](../Topic/task::scheduler%20Method%20\(Concurrency%20Runtime\).md)|Возвращает планировщик для этой задачи|  
|[Метод task::then](../Topic/task::then%20Method.md)|Перегружен.  Добавляет задачу продолжения к этой задаче.|  
|[Метод task::wait](../Topic/task::wait%20Method.md)|Ожидает, когда эта задача достигнет конечного состояния.  У `wait` существует возможность выполнения задачи встроенным образом, если все зависимости задач удовлетворены, и она еще не взята для выполнения фоновым рабочим процессом.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор task::operator\!\=](../Topic/task::operator!=%20Operator.md)|Перегружен.  Определяет, представляют ли два объекта `task` различные внутренние задачи.|  
|[Оператор task::operator\=](../Topic/task::operator=%20Operator.md)|Перегружен.  Заменяет содержимое одного объекта `task` другим.|  
|[Оператор task::operator\=\=](../Topic/task::operator==%20Operator.md)|Перегружен.  Определяет, представляют ли два объекта `task` одну и ту же внутреннюю задачу.|  
  
## Заметки  
 Дополнительные сведения см. в разделе [Параллелизм задач](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## Иерархия наследования  
 `task`  
  
## Требования  
 **Заголовок:** ppltasks.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)