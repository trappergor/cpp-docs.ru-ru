---
title: "Класс location | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::location"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "location - класс"
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Класс location
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Абстракция фактического месторасположения на оборудовании.  
  
## Синтаксис  
  
```  
class location;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор location::location](../Topic/location::location%20Constructor.md)|Перегружен.  Создает объект `location`.|  
|[Деструктор location::~location](../Topic/location::~location%20Destructor.md)|Удаляет объект `location`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод location::current](../Topic/location::current%20Method.md)|Возвращает объект, представляющий наиболее определенное расположение `location`, выполняемое вызывающим потоком.|  
|[Метод location::from\_numa\_node](../Topic/location::from_numa_node%20Method.md)|Возвращает объект `location`, представляющий заданный узел NUMA.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Оператор location::operator\!\=](../Topic/location::operator!=%20Operator.md)|Определяет, представляют ли два объекта `location` различные расположения.|  
|[Оператор location::operator\=](../Topic/location::operator=%20Operator.md)|Назначает содержимое другого объекта `location` данному.|  
|[Оператор location::operator\=\=](../Topic/location::operator==%20Operator.md)|Определяет, представляют ли два объекта `location` одно расположение.|  
  
## Иерархия наследования  
 `location`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)