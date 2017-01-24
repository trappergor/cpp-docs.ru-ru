---
title: "Класс rts_alloc | Microsoft Docs"
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
  - "stdext::rts_alloc"
  - "allocators/stdext::rts_alloc"
  - "rts_alloc"
  - "stdext.rts_alloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rts_alloc - класс"
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс rts_alloc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс шаблона rts\_alloc описывает [фильтр](../standard-library/allocators-header.md), содержащий массив экземпляров кэша, и определяет, какой экземпляр нужно использовать для выделения и освобождения во время выполнения, а не во время компиляции.  
  
## Синтаксис  
  
```  
template <class Cache> class rts_alloc  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Cache`|Тип экземпляров кэша, содержащихся в массиве.  Возможные типы: [Класс cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md) или [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
  
## Заметки  
 Этот класс шаблона содержит несколько экземпляров распределителей блоков и определяет, какой экземпляр нужно использовать для выделения и освобождения во время выполнения, а не во время компиляции.  Он используется с компиляторами, которые не могут скомпилировать повторную привязку.  
  
### Функции\-члены  
  
|||  
|-|-|  
|[allocate](../Topic/rts_alloc::allocate.md)|Выделяет блок памяти.|  
|[deallocate](../Topic/rts_alloc::deallocate.md)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|  
|[равно](../Topic/rts_alloc::equals.md)|Сравнивает два кэша на равенство.|  
  
## Требования  
 **Заголовок:** \<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md)   
 [\<allocators\>](../standard-library/allocators-header.md)