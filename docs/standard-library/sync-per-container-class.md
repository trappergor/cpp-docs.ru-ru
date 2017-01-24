---
title: "Класс sync_per_container | Microsoft Docs"
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
  - "stdext.sync_per_container"
  - "sync_per_container"
  - "stdext::sync_per_container"
  - "allocators/stdext::sync_per_container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_per_container - класс"
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс sync_per_container
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает [фильтр синхронизации](../standard-library/allocators-header.md), который предоставляет отдельный объект кэша для каждого объекта распределителя.  
  
## Синтаксис  
  
```  
template <class Cache> class sync_per_container  
    : public Cache  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Cache`|Тип кэша, связанный с фильтром синхронизации.  Это может быть [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md) или [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[equals](../Topic/sync_per_container::equals.md)|Сравнение на равенство 2 кэша.|  
  
## Требования  
 **Заголовок:**\<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<allocators\>](../standard-library/allocators-header.md)