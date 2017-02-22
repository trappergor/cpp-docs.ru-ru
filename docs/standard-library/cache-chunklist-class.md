---
title: "Класс cache_chunklist | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators/stdext::cache_chunklist"
  - "stdext.cache_chunklist"
  - "stdext::cache_chunklist"
  - "cache_chunklist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_chunklist - класс"
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Класс cache_chunklist
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет [распределитель блока](../standard-library/allocators-header.md), выделение и отменить блоки памяти одного размера.  
  
## Синтаксис  
  
```  
template <std::size_t Sz, std::size_t Nelts = 20> class cache_chunklist  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Sz`|Количество элементов в массиве, который для выделения.|  
  
## Заметки  
 Этот класс шаблона используется `operator new` для выделения блоков сырцовой suballocating блоки памяти, чтобы выделить хранилище для блока памяти; он хранит отмененные распределение блоков памяти в списке свободном отдельно для каждого блока, и использует `operator delete` для отмены блок, если ни один из его блоков памяти в использовании.  
  
 Каждый блок памяти содержит байты `Sz` годной к использованию памяти и указателя в блоке, он принадлежит.  Каждый блок содержит блоки памяти `Nelts`, 3 указателя, int и данные, `operator new` и `operator delete` требуют.  
  
### конструкторов;  
  
|||  
|-|-|  
|[cache\_chunklist](../Topic/cache_chunklist::cache_chunklist.md)|Создает объект типа `cache_chunklist`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[выделите](../Topic/cache_chunklist::allocate.md)|Выделяет блок памяти.|  
|[отменить](../Topic/cache_chunklist::deallocate.md)|Освобождает заданное число объектов из начала хранилища в указанной позиции.|  
  
## Требования  
 **Заголовок:**\<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<allocators\>](../standard-library/allocators-header.md)