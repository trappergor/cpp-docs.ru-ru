---
title: "Класс cache_freelist | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext.cache_freelist"
  - "allocators/stdext::cache_freelist"
  - "stdext::cache_freelist"
  - "cache_freelist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_freelist - класс"
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс cache_freelist
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет [Блокировать распределителя](../standard-library/allocators-header.md) выделяет и освобождает блоки памяти одного размера.  
  
## Синтаксис  
  
```  
template <std::size_t Sz, class Max> class cache_freelist  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Sz`|Число элементов в массиве должен быть выделен.|  
|`Max`|Max класс, представляющий максимальный размер свободного списка. Это может быть [max\_fixed\_size](../standard-library/max-fixed-size-class.md), [max\_none](../Topic/max_none%20Class.md), [max\_unbounded](../standard-library/max-unbounded-class.md), или [max\_variable\_size](../standard-library/max-variable-size-class.md).|  
  
## Заметки  
 Класс cache\_freelist шаблона ведет список свободных блоков памяти размером `Sz`. При заполнении свободного списка использует `operator delete` для освобождения памяти блокируется. При пустом свободного списка использует `operator new` выделить новые блоки памяти. Максимальный размер свободного списка определяется классом, переданный max класс `Max` параметр.  
  
 Каждый блок памяти содержит `Sz` байт свободной памяти и данных, `operator new` и `operator delete` требуют.  
  
### Конструкторы  
  
|||  
|-|-|  
|[cache\_freelist](../Topic/cache_freelist::cache_freelist.md)|Создает объект типа `cache_freelist`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[allocate](../Topic/cache_freelist::allocate.md)|Выделяет блок памяти.|  
|[deallocate](../Topic/cache_freelist::deallocate.md)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|  
  
## Требования  
 **Заголовок:** \<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<allocators\>](../standard-library/allocators-header.md)