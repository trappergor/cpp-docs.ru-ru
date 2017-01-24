---
title: "Класс sync_per_thread | Microsoft Docs"
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
  - "stdext::sync_per_thread"
  - "sync_per_thread"
  - "allocators/stdext::sync_per_thread"
  - "stdext.sync_per_thread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_per_thread - класс"
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс sync_per_thread
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает [фильтр синхронизации](../standard-library/allocators-header.md), который предоставляет отдельный объект кэша для каждого потока.  
  
## Синтаксис  
  
```  
template <class Cache> class sync_per_thread  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Cache`|Тип кэша, связанный с фильтром синхронизации.  Это может быть [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md) или [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
  
## Заметки  
 Распределителей, использующие `sync_per_thread` могут сравнения равно даже если блоки, выделенные в одном потоке нельзя отменить из другого потока.  При использовании одного из этих выделенных блоков распределителей памяти в одном потоке не следует делать видимыми для других потоков.  На практике это означает, что контейнер, используется один из этих распределителей должен быть получен одним потоком.  
  
### Функции\-члены  
  
|||  
|-|-|  
|[выделите](../Topic/sync_per_thread::allocate.md)|Выделяет блок памяти.|  
|[отменить](../Topic/sync_per_thread::deallocate.md)|Освобождает заданное число объектов из начала хранилища в указанной позиции.|  
|[equals](../Topic/sync_per_thread::equals.md)|Сравнение на равенство 2 кэша.|  
  
## Требования  
 **Заголовок:**\<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<allocators\>](../standard-library/allocators-header.md)