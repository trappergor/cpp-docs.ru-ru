---
title: "Класс allocator_base | Microsoft Docs"
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
  - "allocators.allocator_base"
  - "stdext.allocators.allocator_base"
  - "allocator_base"
  - "allocators/stdext::allocator_base"
  - "stdext::allocator_base"
  - "stdext::allocators::allocator_base"
  - "allocators/stdext::allocators::allocator_base"
  - "allocators::allocator_base"
  - "stdext.allocator_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_base - класс"
ms.assetid: f920b45f-2a88-4bb0-8ead-b6126b426ed4
caps.latest.revision: 17
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс allocator_base
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет базовый класс и общие функции, необходимые для создания определяемого пользователем распределителя из фильтра синхронизации.  
  
## Синтаксис  
  
```  
template <class Type, class Sync> class allocator_base  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Type`|Тип элементов, распределяемых распределителем.|  
|`Sync`|Политика синхронизации распределителя: [Класс sync\_none](../standard-library/sync-none-class.md), [Класс sync\_per\_container](../standard-library/sync-per-container-class.md), [Класс sync\_per\_thread](../standard-library/sync-per-thread-class.md) или [Класс sync\_shared](../Topic/sync_shared%20Class.md).|  
  
### Конструкторы  
  
|||  
|-|-|  
|[allocator\_base](../Topic/allocator_base::allocator_base.md)|Создает объект типа `allocator_base`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[const\_pointer](../Topic/allocator_base::const_pointer.md)|Тип, предоставляющий постоянный указатель на тип объекта, управляемого распределителем.|  
|[const\_reference](../Topic/allocator_base::const_reference.md)|Тип, предоставляющий постоянную ссылку на тип объекта, управляемого распределителем.|  
|[difference\_type](../Topic/allocator_base::difference_type.md)|Тип целого числа со знаком, который может представлять разницу между значениями указателей на тип объекта, управляемого распределителем.|  
|[pointer](../Topic/allocator_base::pointer.md)|Тип, предоставляющий указатель на тип объекта, управляемого распределителем.|  
|[ссылка](../Topic/allocator_base::reference.md)|Тип, предоставляющий ссылку на тип объекта, управляемого распределителем.|  
|[size\_type](../Topic/allocator_base::size_type.md)|Тип целого числа без знака, который может представлять длину любой последовательности, которую может выделить объект класса шаблона `allocator_base`.|  
|[value\_type](../Topic/allocator_base::value_type.md)|Тип, управляемый распределителем.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[\_Charalloc](../Topic/allocator_base::_Charalloc.md)|Выделяет память для массива типа `char`.|  
|[\_Chardealloc](../Topic/allocator_base::_Chardealloc.md)|Освобождает хранилище для массива, содержащего элементы типа `char`.|  
|[адрес](../Topic/allocator_base::address.md)|Находит адрес объекта, значение которого задано.|  
|[allocate](../Topic/allocator_base::allocate.md)|Выделяет блок памяти, достаточный для хранения по крайней мере некоторого указанного числа элементов.|  
|[construct](../Topic/allocator_base::construct.md)|Создает определенный тип объекта по указанному адресу, инициализированный с использованием заданного значения.|  
|[deallocate](../Topic/allocator_base::deallocate.md)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|  
|[удаление](../Topic/allocator_base::destroy.md)|Вызывает деструктор объектов без освобождения памяти, в которой хранился объект.|  
|[max\_size](../Topic/allocator_base::max_size.md)|Возвращает количество элементов типа `Type`, которые могут быть выделены объектом класса в пределах имеющейся свободной памяти.|  
  
## Требования  
 **Заголовок:** \<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<allocators\>](../standard-library/allocators-header.md)