---
title: "Класс allocator_newdel | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators::allocator_newdel"
  - "allocators/stdext::allocators::allocator_newdel"
  - "stdext.allocators.allocator_newdel"
  - "allocators/stdext::allocator_newdel"
  - "allocator_newdel"
  - "stdext::allocators::allocator_newdel"
  - "allocators.allocator_newdel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_newdel - класс"
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# Класс allocator_newdel
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Реализует распределитель, использующий `operator delete` для отмены блок памяти и `operator new`, чтобы выделить блок памяти.  
  
## Синтаксис  
  
```  
template <class Type>  
    class allocator_newdel;  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Type`|Тип элементов, выбранных распределителем.|  
  
## Заметки  
 Макрос [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) передает этот класс в качестве параметра `name` в следующую инструкцию: `ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`  
  
## Требования  
 **Заголовок:**\<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<allocators\>](../standard-library/allocators-header.md)