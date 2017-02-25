---
title: "Класс multi_link_registry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::multi_link_registry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multi_link_registry - класс"
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс multi_link_registry
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Объект `multi_link_registry` — это `network_link_registry`, который управляет несколькими исходными блоками или несколькими целевыми блоками.  
  
## Синтаксис  
  
```  
template<  
   class _Block  
>  
class multi_link_registry : public network_link_registry<_Block>;  
```  
  
#### Параметры  
 `_Block`  
 Тип данных блока, хранящихся в объекте `multi_link_registry`.  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор multi\_link\_registry::multi\_link\_registry](../Topic/multi_link_registry::multi_link_registry%20Constructor.md)|Создает объект `multi_link_registry`.|  
|[Деструктор multi\_link\_registry::~multi\_link\_registry](../Topic/multi_link_registry::~multi_link_registry%20Destructor.md)|Уничтожает объект `multi_link_registry`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод multi\_link\_registry::add](../Topic/multi_link_registry::add%20Method.md)|Добавляет ссылку на объект `multi_link_registry`. \(Переопределяет [network\_link\_registry::add](../Topic/network_link_registry::add%20Method.md).\)|  
|[Метод multi\_link\_registry::begin](../Topic/multi_link_registry::begin%20Method.md)|Возвращает итератор на первый элемент в объекте `multi_link_registry`. \(Переопределяет [network\_link\_registry::begin](../Topic/network_link_registry::begin%20Method.md).\)|  
|[Метод multi\_link\_registry::contains](../Topic/multi_link_registry::contains%20Method.md)|Выполняет поиск указанного блока по объекту `multi_link_registry`. \(Переопределяет [network\_link\_registry::contains](../Topic/network_link_registry::contains%20Method.md).\)|  
|[Метод multi\_link\_registry::count](../Topic/multi_link_registry::count%20Method.md)|Подсчитывает количество элементов в объекте `multi_link_registry`. \(Переопределяет [network\_link\_registry::count](../Topic/network_link_registry::count%20Method.md).\)|  
|[Метод multi\_link\_registry::remove](../Topic/multi_link_registry::remove%20Method.md)|Удаляет ссылку из объекта `multi_link_registry`. \(Переопределяет [network\_link\_registry::remove](../Topic/network_link_registry::remove%20Method.md).\)|  
|[Метод multi\_link\_registry::set\_bound](../Topic/multi_link_registry::set_bound%20Method.md)|Устанавливает верхний предел на число ссылок, который может содержать объект `multi_link_registry`.|  
  
## Иерархия наследования  
 [network\_link\_registry](../Topic/network_link_registry%20Class.md)  
  
 `multi_link_registry`  
  
## Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс single\_link\_registry](../Topic/single_link_registry%20Class.md)