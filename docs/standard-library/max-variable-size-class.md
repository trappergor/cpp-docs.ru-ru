---
title: "Класс max_variable_size | Microsoft Docs"
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
  - "stdext::max_variable_size"
  - "allocators/stdext::max_variable_size"
  - "stdext.max_variable_size"
  - "max_variable_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_variable_size - класс"
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс max_variable_size
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает [Макс. класс](../standard-library/allocators-header.md) ограничивающий [freelist](../Topic/freelist%20Class.md) выделен объект до максимальной длины, примерно пропорционально количество блоков памяти.  
  
## Синтаксис  
  
```  
class max_variable_size  
```  
  
### Конструкторы  
  
|||  
|-|-|  
|[max\_variable\_size](../Topic/max_variable_size::max_variable_size.md)|Создает объект типа `max_variable_size`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[выделенные](../Topic/max_variable_size::allocated.md)|Увеличивает число блоков памяти.|  
|[освобождена](../Topic/max_variable_size::deallocated.md)|Уменьшает количество выделенных блоков памяти.|  
|[Полный](../Topic/max_variable_size::full.md)|Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.|  
|[выпущена](../Topic/max_variable_size::released.md)|Уменьшает количество памяти блоки на свободного списка.|  
|[Сохранить](../Topic/max_variable_size::saved.md)|Увеличивает число блоков памяти свободного списка.|  
  
## Требования  
 **Заголовок:** \<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<allocators\>](../standard-library/allocators-header.md)