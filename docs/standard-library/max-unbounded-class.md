---
title: "Класс max_unbounded | Microsoft Docs"
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
  - "allocators/stdext::max_unbounded"
  - "stdext::max_unbounded"
  - "stdext.max_unbounded"
  - "max_unbounded"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_unbounded - класс"
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс max_unbounded
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает [Макс. класс](../standard-library/allocators-header.md) объект, который не ограничивает максимальную длину [freelist](../Topic/freelist%20Class.md) объекта.  
  
## Синтаксис  
  
```  
class max_unbounded  
```  
  
### Функции\-члены  
  
|||  
|-|-|  
|[выделенные](../Topic/max_unbounded::allocated.md)|Увеличивает число блоков памяти.|  
|[освобождена](../Topic/max_unbounded::deallocated.md)|Уменьшает количество выделенных блоков памяти.|  
|[Полный](../Topic/max_unbounded::full.md)|Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.|  
|[выпущена](../Topic/max_unbounded::released.md)|Уменьшает количество памяти блоки на свободного списка.|  
|[Сохранить](../Topic/max_unbounded::saved.md)|Увеличивает число блоков памяти свободного списка.|  
  
## Требования  
 **Заголовок:** \<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<allocators\>](../standard-library/allocators-header.md)