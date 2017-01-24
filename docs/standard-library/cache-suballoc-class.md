---
title: "Класс cache_suballoc | Microsoft Docs"
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
  - "stdext.cache_suballoc"
  - "allocators/stdext::cache_suballoc"
  - "stdext::cache_suballoc"
  - "cache_suballoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_suballoc - класс"
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
caps.latest.revision: 17
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс cache_suballoc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет [Блокировать распределителя](../standard-library/allocators-header.md) выделяет и освобождает блоки памяти одного размера.  
  
## Синтаксис  
  
```  
template <std::size_t Sz, size_t Nelts = 20> class cache_suballoc  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Sz`|Число элементов в массиве должен быть выделен.|  
  
## Заметки  
 Класс cache\_suballoc шаблона сохраняет блоки памяти, освобожденных в свободного списка с неограниченными длины с помощью `freelist<sizeof(Type), max_unbounded>`, и suballocates блоки памяти из большего размера блока, выделенные с помощью `operator new` при свободного списка пуст.  
  
 Каждый блок содержит `Sz * Nelts` байт свободной памяти и данных, `operator new` и `operator delete` требуют. Выделенные фрагменты, никогда не будут освобождены.  
  
### Конструкторы  
  
|||  
|-|-|  
|[cache\_suballoc](../Topic/cache_suballoc::cache_suballoc.md)|Создает объект типа `cache_suballoc`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[allocate](../Topic/cache_suballoc::allocate.md)|Выделяет блок памяти.|  
|[deallocate](../Topic/cache_suballoc::deallocate.md)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|  
  
## Требования  
 **Заголовок:** \<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<allocators\>](../standard-library/allocators-header.md)