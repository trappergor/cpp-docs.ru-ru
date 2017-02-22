---
title: "Класс concurrent_unordered_multimap | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concurrent_unordered_map/concurrency::concurrent_unordered_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_unordered_multimap - класс"
ms.assetid: 4dada5d7-15df-4382-b9c9-348e75b2f3c1
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Класс concurrent_unordered_multimap
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `concurrent_unordered_multimap` — это безопасный в режиме параллелизма контейнер, который управляет последовательностью переменной длины элементов типа `std::pair<const _Key_type, _Element_type>`.  Последовательность представлена таким образом, который позволяет параллельно\-безопасно выполнять операции присоединения, получения доступа к элементу, доступа к итератору и обхода итератора.  
  
## Синтаксис  
  
```  
template <  
   typename _Key_type,  
   typename _Element_type,  
   typename _Hasher = std::tr1::hash<_Key_type>,  
   typename _Key_equality = std::equal_to<_Key_type>,  
   typename _Allocator_type = std::allocator<std::pair<const _Key_type,  
   _Element_type> >  
>  
, typename _Key_equality = std::equal_to<_Key_type>, typename _Allocator_type = std::allocator<std::pair<const _Key_type, _Element_type> > > class concurrent_unordered_multimap : public details::_Concurrent_hash< details::_Concurrent_unordered_map_traits<_Key_type, _Element_type, details::_Hash_compare<_Key_type, _Hasher, _Key_equality>, _Allocator_type, true> >;  
```  
  
#### Параметры  
 `_Key_type`  
 Тип ключа.  
  
 `_Element_type`  
 Сопоставленный тип.  
  
 `_Hasher`  
 Тип объекта хэш\-функции.  Этот аргумент является необязательным и значение по умолчанию — `std::tr1::hash<``_Key_type``>`.  
  
 `_Key_equality`  
 Тип объекта функции сравнения на предмет равенства.  Этот аргумент является необязательным и значение по умолчанию — `std::equal_to<``_Key_type``>`.  
  
 `_Allocator_type`  
 Тип, представляющий хранимый объект распределителя, инкапсулирующий сведения о распределении и освобождении памяти для параллельного вектора.  Этот аргумент является необязательным и значение по умолчанию — `std::allocator<std::pair<``_Key_type`, `_Element_type``>>`.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`allocator_type`|Тип распределителя для управления хранилищем.|  
|`const_iterator`|Тип постоянного итератора для управляемой последовательности.|  
|`const_local_iterator`|Тип постоянного итератора контейнера для управляемой последовательности.|  
|`const_pointer`|Тип постоянного указателя на элемент.|  
|`const_reference`|Тип постоянной ссылки на элемент.|  
|`difference_type`|Тип расстояния со знаком между двумя элементами.|  
|`hasher`|Тип хэш\-функции.|  
|`iterator`|Тип итератора для управляемой последовательности.|  
|`key_equal`|Тип функции сравнения.|  
|`key_type`|Тип ключа упорядочения.|  
|`local_iterator`|Тип итератора контейнера для управляемой последовательности.|  
|`mapped_type`|Тип сопоставленного значения, связанного с каждым ключом.|  
|`pointer`|Тип указателя на элемент.|  
|`reference`|Тип ссылки на элемент.|  
|`size_type`|Тип беззнакового расстояния между двумя элементами.|  
|`value_type`|Тип элемента.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор concurrent\_unordered\_multimap::concurrent\_unordered\_multimap](../Topic/concurrent_unordered_multimap::concurrent_unordered_multimap%20Constructor.md)|Перегружен.  Создает параллельное неупорядоченное мультисопоставление.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод concurrent\_unordered\_multimap::hash\_function](../Topic/concurrent_unordered_multimap::hash_function%20Method.md)|Возвращает объект сохраненной хэш\-функции.|  
|[Метод concurrent\_unordered\_multimap::insert](../Topic/concurrent_unordered_multimap::insert%20Method.md)|Перегружен.  Добавляет элементы в объект `concurrent_unordered_multimap`.|  
|[Метод concurrent\_unordered\_multimap::key\_eq](../Topic/concurrent_unordered_multimap::key_eq%20Method.md)|Возвращает сохраненный объект функции проверки равенства.|  
|[Метод concurrent\_unordered\_multimap::swap](../Topic/concurrent_unordered_multimap::swap%20Method.md)|Меняет местами содержимое двух объектов `concurrent_unordered_multimap`.  Данный метод не безопасен в режиме параллелизма.|  
|[Метод concurrent\_unordered\_multimap::unsafe\_erase](../Topic/concurrent_unordered_multimap::unsafe_erase%20Method.md)|Перегружен.  Удаляет элементы из `concurrent_unordered_multimap` в указанных положениях.  Данный метод не безопасен в режиме параллелизма.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Оператор concurrent\_unordered\_multimap::operator\=](../Topic/concurrent_unordered_multimap::operator=%20Operator.md)|Перегружен.  Назначает содержимое другого объекта `concurrent_unordered_multimap` данному.  Данный метод не безопасен в режиме параллелизма.|  
  
## Заметки  
 Подробные сведения о классе `concurrent_unordered_multimap` содержатся в разделе [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Иерархия наследования  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_multimap`  
  
## Требования  
 **Заголовок:** concurrent\_unordered\_map.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md)