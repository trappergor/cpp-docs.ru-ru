---
title: "Класс max_fixed_size | Microsoft Docs"
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
  - "allocators/stdext::max_fixed_size"
  - "max_fixed_size"
  - "stdext::max_fixed_size"
  - "stdext.max_fixed_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_fixed_size - класс"
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс max_fixed_size
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание объекта [максимальный класс](../standard-library/allocators-header.md), что ограничения объект [freelist](../Topic/freelist%20Class.md) в фиксированной максимальной длины.  
  
## Синтаксис  
  
```  
template <std::size_t Max> class max_fixed_size  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Max`|Максимальный класс, определяющий максимальное количество элементов для хранения в `freelist`.|  
  
### конструкторов;  
  
|||  
|-|-|  
|[max\_fixed\_size](../Topic/max_fixed_size::max_fixed_size.md)|Создает объект типа `max_fixed_size`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[выбранный](../Topic/max_fixed_size::allocated.md)|Увеличивает число блоков выделения памяти.|  
|[отменено распределение](../Topic/max_fixed_size::deallocated.md)|Уменьшает число блоков выделения памяти.|  
|[полная](../Topic/max_fixed_size::full.md)|Возвращает значение, которое указывает, должны ли несколько блоков памяти добавляться к свободному список.|  
|[выпущено](../Topic/max_fixed_size::released.md)|Уменьшает число блоков памяти в свободном списке.|  
|[сохраненный](../Topic/max_fixed_size::saved.md)|Увеличивает число блоков памяти в свободном списке.|  
  
## Требования  
 **Заголовок:**\<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<allocators\>](../standard-library/allocators-header.md)