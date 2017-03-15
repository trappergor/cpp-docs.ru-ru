---
title: "Класс allocator_suballoc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators::allocator_suballoc"
  - "allocator_suballoc"
  - "stdext.allocators.allocator_suballoc"
  - "allocators/stdext::allocators::allocator_suballoc"
  - "stdext::allocators::allocator_suballoc"
  - "allocators/stdext::allocator_suballoc"
  - "allocators.allocator_suballoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_suballoc - класс"
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Класс allocator_suballoc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, который управляет выделением и освобождением памяти для объектов типа `Type` Использование кэша типа [cache\_suballoc](../standard-library/cache-suballoc-class.md).  
  
## Синтаксис  
  
```  
template <class Type>  
    class allocator_suballoc;  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Type`|Тип элементов, распределяемых распределителем.|  
  
## Заметки  
 [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) Макрос передает этот класс как `name` параметр в следующей инструкции: `ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`  
  
## Требования  
 **Заголовок:** \<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<allocators\>](../standard-library/allocators-header.md)