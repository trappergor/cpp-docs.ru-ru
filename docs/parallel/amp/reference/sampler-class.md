---
title: "Класс sampler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Класс sampler
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс образца вычисляет сведения о конфигурации выборки, которые будут использоваться для выборки текстуры.  
  
## Синтаксис  
  
```  
class sampler;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор sampler::sampler](../Topic/sampler::sampler%20Constructor.md)|Перегружен.  Создает экземпляр дискретизатора.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод sampler::get\_address\_mode](../Topic/sampler::get_address_mode%20Method.md)|Возвращает объект `address_mode`, связанный с объектом дискретизатора.|  
|[Метод sampler::get\_border\_color](../Topic/sampler::get_border_color%20Method.md)|Возвращает цвет границы, связанного с объектом образца.|  
|[Метод sampler::get\_filter\_mode](../Topic/sampler::get_filter_mode%20Method.md)|Возвращает объект `filter_mode`, связанный с объектом дискретизатора.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор sampler::operator\=](../Topic/sampler::operator=%20Operator.md)|Перегружен.  Оператор присваивания.|  
  
### Открытые члены данных  
  
|Name|Описание|  
|----------|--------------|  
|[Элемент данных sampler::address\_mode](../Topic/sampler::address_mode%20Data%20Member.md)|Получает режим адресации объекта `sampler`.|  
|[Элемент данных sampler::border\_color](../Topic/sampler::border_color%20Data%20Member.md)|Получает цвет границы объекта `sampler`.|  
|[Элемент данных sampler::filter\_mode](../Topic/sampler::filter_mode%20Data%20Member.md)|Получает режим фильтрации объекта `sampler`.|  
  
## Иерархия наследования  
 `sampler`  
  
## Требования  
 **Заголовок:** amp\_graphics.h  
  
 **Пространство имен:** concurrency::graphics  
  
## См. также  
 [Пространство имен Concurrency::graphics](../../../parallel/amp/reference/concurrency-graphics-namespace.md)