---
title: "Класс auto_partitioner | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::auto_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_partitioner - класс"
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Класс auto_partitioner
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `auto_partitioner` представляет метод разделения, который алгоритмы `parallel_for`, `parallel_for_each` и `parallel_transform` используют по умолчанию для разделения обрабатываемого диапазона.  Этот метод разделения диапазона обеспечивает как секционирование для распределения нагрузки, так и отмену в циклах.  
  
## Синтаксис  
  
```  
class auto_partitioner;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор auto\_partitioner::auto\_partitioner](../Topic/auto_partitioner::auto_partitioner%20Constructor.md)|Создает объект `auto_partitioner`.|  
|[Деструктор auto\_partitioner::~auto\_partitioner](../Topic/auto_partitioner::~auto_partitioner%20Destructor.md)|Удаляет объект `auto_partitioner`.|  
  
## Иерархия наследования  
 `auto_partitioner`  
  
## Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)