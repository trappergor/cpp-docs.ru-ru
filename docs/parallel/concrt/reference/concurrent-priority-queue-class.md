---
title: "Класс concurrent_priority_queue | Microsoft Docs"
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
  - "concurrent_priority_queue/concurrency::concurrent_priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_priority_queue - класс"
ms.assetid: 3e740381-0f4e-41fc-8b66-ad0bb55f17a3
caps.latest.revision: 9
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс concurrent_priority_queue
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `concurrent_priority_queue` — это контейнер, который позволяет нескольким потокам параллельно класть и извлекать элементы.  Элементы извлекаются в порядке приоритета, определяемого функтором, предоставленным в качестве аргумента шаблона.  
  
## Синтаксис  
  
```  
template <  
   typename _Ty,  
   typename _Compare=std::less<_Ty>,  
   typename _Ax = std::allocator<_Ty>  
>  
, typename _Ax = std::allocator<_Ty> > class concurrent_priority_queue;  
```  
  
#### Параметры  
 `_Ty`  
 Тип данных элементов, хранимых в очереди с приоритетом.  
  
 `_Compare`  
 Тип объекта функции, который может сравнивать значения двух элементов в качестве ключей сортировки для определения относительного порядка в очереди с приоритетом.  Этот аргумент является необязательным, и бинарный предикат `less<``_Ty``>` является значением по умолчанию.  
  
 `_Ax`  
 Тип, представляющий хранимый объект распределителя, инкапсулирующий сведения о распределении и освобождении памяти для очереди с приоритетом.  Этот аргумент является необязательным и значение по умолчанию — `allocator<``_Ty``>`.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`allocator_type`|Тип, представляющий класс распределителя для параллельной очереди с приоритетом.|  
|`const_reference`|Тип, представляющий константную ссылку на элемент типа хранящихся в параллельной очереди с приоритетом.|  
|`reference`|Тип, представляющий ссылку на элемент типа хранящихся в параллельной очереди с приоритетом.|  
|`size_type`|Тип, который подсчитывает число элементов в параллельной очереди с приоритетом.|  
|`value_type`|Тип, который представляет тип данных, хранящихся в параллельной очереди с приоритетом.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор concurrent\_priority\_queue::concurrent\_priority\_queue](../Topic/concurrent_priority_queue::concurrent_priority_queue%20Constructor.md)|Перегружен.  Создает параллельную очередь с приоритетом.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод concurrent\_priority\_queue::clear](../Topic/concurrent_priority_queue::clear%20Method.md)|Удаляет все элементы в параллельной очереди с приоритетом.  Данный метод не безопасен в режиме параллелизма.|  
|[Метод concurrent\_priority\_queue::empty](../Topic/concurrent_priority_queue::empty%20Method.md)|Проверяет, пуста ли параллельная очередь с приоритетом в момент, когда этот метод вызывается.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_priority\_queue::get\_allocator](../Topic/concurrent_priority_queue::get_allocator%20Method.md)|Возвращает копию распределителя, используемого для создания параллельной очереди с приоритетом.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_priority\_queue::push](../Topic/concurrent_priority_queue::push%20Method.md)|Перегружен.  Добавляет элемент в параллельную очередь с приоритетом.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_priority\_queue::size](../Topic/concurrent_priority_queue::size%20Method.md)|Возвращает число элементов, которые находятся в параллельной очереди с приоритетом.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_priority\_queue::swap](../Topic/concurrent_priority_queue::swap%20Method.md)|Обмен содержимого двух параллельных очередей с приоритетом.  Данный метод не безопасен в режиме параллелизма.|  
|[Метод concurrent\_priority\_queue::try\_pop](../Topic/concurrent_priority_queue::try_pop%20Method.md)|Удаляет и возвращает элемент наивысшего приоритета из очереди, если очередь не пуста.  Данный метод безопасен в режиме параллелизма.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Оператор concurrent\_priority\_queue::operator\=](../Topic/concurrent_priority_queue::operator=%20Operator.md)|Перегружен.  Назначает содержимое другого объекта `concurrent_priority_queue` данному.  Данный метод не безопасен в режиме параллелизма.|  
  
## Заметки  
 Подробные сведения о классе `concurrent_priority_queue` содержатся в разделе [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Иерархия наследования  
 `concurrent_priority_queue`  
  
## Требования  
 **Заголовок:** concurrent\_priority\_queue.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md)