---
title: "Класс sync_none | Microsoft Docs"
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
  - "stdext.sync_none"
  - "sync_none"
  - "allocators/stdext::sync_none"
  - "stdext::sync_none"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_none - класс"
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс sync_none
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает [фильтр синхронизации](../standard-library/allocators-header.md), который не предоставляет какой\-либо синхронизации.  
  
## Синтаксис  
  
```  
template <class Cache> class sync_none  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Cache`|Тип кэша, связанный с фильтром синхронизации.  Это может быть [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md) или [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[выделите](../Topic/sync_none::allocate.md)|Выделяет блок памяти.|  
|[отменить](../Topic/sync_none::deallocate.md)|Освобождает заданное число объектов из начала хранилища в указанной позиции.|  
|[equals](../Topic/sync_none::equals.md)|Сравнение на равенство 2 кэша.|  
  
## Требования  
 **Заголовок:**\<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<allocators\>](../standard-library/allocators-header.md)