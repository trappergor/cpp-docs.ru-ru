---
title: "Класс concurrent_unordered_map | Microsoft Docs"
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
  - "concurrent_unordered_map/concurrency::concurrent_unordered_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_unordered_map - класс"
ms.assetid: b2d879dd-87ef-4af9-a266-a5443fd538b8
caps.latest.revision: 13
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс concurrent_unordered_map
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `concurrent_unordered_map` — это безопасный в режиме параллелизма контейнер, который управляет последовательностью переменной длины элементов типа `std::pair<const _Key_type, _Element_type>`.  Последовательность представлена таким образом, который позволяет параллельно\-безопасно выполнять операции присоединения, получения доступа к элементу, доступа к итератору и обхода итератора.  
  
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
, typename _Key_equality = std::equal_to<_Key_type>, typename _Allocator_type = std::allocator<std::pair<const _Key_type, _Element_type> > > class concurrent_unordered_map : public details::_Concurrent_hash< details::_Concurrent_unordered_map_traits<_Key_type, _Element_type, details::_Hash_compare<_Key_type, _Hasher, _Key_equality>, _Allocator_type, false> >;  
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
 Тип, представляющий хранимый объект распределителя, инкапсулирующий сведения о распределении и освобождении памяти для параллельного не упорядоченного сопоставления.  Этот аргумент является необязательным и значение по умолчанию — `std::allocator<std::pair<``_Key_type`, `_Element_type``>>`.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Name|Описание|  
|----------|--------------|  
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
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор concurrent\_unordered\_map::concurrent\_unordered\_map](../Topic/concurrent_unordered_map::concurrent_unordered_map%20Constructor.md)|Перегружен.  Создает Параллельный Не упорядоченный сопоставление.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод concurrent\_unordered\_map::at](../Topic/concurrent_unordered_map::at%20Method.md)|Перегружен.  Находит элемент в `concurrent_unordered_map` с указанными ключевым значением.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_unordered\_map::hash\_function](../Topic/concurrent_unordered_map::hash_function%20Method.md)|Получает объект сохраненной хэш\-функции.|  
|[Метод concurrent\_unordered\_map::insert](../Topic/concurrent_unordered_map::insert%20Method.md)|Перегружен.  Добавляет элементы в объект `concurrent_unordered_map`.|  
|[Метод concurrent\_unordered\_map::key\_eq](../Topic/concurrent_unordered_map::key_eq%20Method.md)|Возвращает сохраненный объект функции проверки равенства.|  
|[Метод concurrent\_unordered\_map::swap](../Topic/concurrent_unordered_map::swap%20Method.md)|Меняет местами содержимое двух объектов `concurrent_unordered_map`.  Данный метод не безопасен в режиме параллелизма.|  
|[Метод concurrent\_unordered\_map::unsafe\_erase](../Topic/concurrent_unordered_map::unsafe_erase%20Method.md)|Перегружен.  Удаляет элементы из `concurrent_unordered_map` в указанных положениях.  Данный метод не безопасен в режиме параллелизма.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[concurrent\_unordered\_map::operatorOperator](../Topic/concurrent_unordered_map::operatorOperator.md)|Перегружен.  Находит или вставляет элемент с указанным ключом.  Данный метод безопасен в режиме параллелизма.|  
|[Оператор concurrent\_unordered\_map::operator\=](../Topic/concurrent_unordered_map::operator=%20Operator.md)|Перегружен.  Назначает содержимое другого объекта `concurrent_unordered_map` данному.  Данный метод не безопасен в режиме параллелизма.|  
  
## Заметки  
 Подробные сведения о классе `concurrent_unordered_map` содержатся в разделе [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Иерархия наследования  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_map`  
  
## Требования  
 **Заголовок:** concurrent\_unordered\_map.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md)