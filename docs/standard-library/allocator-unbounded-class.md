---
title: "Класс allocator_unbounded | Microsoft Docs"
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
  - "stdext::allocators::allocator_unbounded"
  - "allocator_unbounded"
  - "allocators/stdext::allocator_unbounded"
  - "allocators::allocator_unbounded"
  - "allocators/stdext::allocators::allocator_unbounded"
  - "allocators.allocator_unbounded"
  - "stdext.allocators.allocator_unbounded"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_unbounded - класс"
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
caps.latest.revision: 17
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс allocator_unbounded
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, который управляет выделение и освобождение памяти для объектов типа `Type` использование кэша управлянная длина типа [cache\_freelist](../standard-library/cache-freelist-class.md) с [max\_unbounded](../standard-library/max-unbounded-class.md).  
  
## Синтаксис  
  
```  
template <class Type>  
    class allocator_unbounded;  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Type`|Тип элементов, выбранных распределителем.|  
  
## Заметки  
 Макрос [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) передает этот класс в качестве параметра `name` в следующую инструкцию: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`  
  
## Требования  
 **Заголовок:**\<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<allocators\>](../standard-library/allocators-header.md)