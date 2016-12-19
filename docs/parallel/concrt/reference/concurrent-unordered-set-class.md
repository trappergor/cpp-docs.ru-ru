---
title: "Класс concurrent_unordered_set | Microsoft Docs"
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
  - "concurrent_unordered_set/concurrency::concurrent_unordered_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_unordered_set - класс"
ms.assetid: c61f9a9a-4fd9-491a-9251-e300737ecf4b
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс concurrent_unordered_set
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `concurrent_unordered_set` — это безопасный в режиме параллелизма контейнер, который управляет последовательностью элементов типа \_Key\_type переменной длины.  Последовательность представлена таким образом, который позволяет параллельно\-безопасно выполнять операции присоединения, получения доступа к элементу, доступа к итератору и обхода итератора.  
  
## Синтаксис  
  
```  
template <  
   typename _Key_type,  
   typename _Hasher = std::tr1::hash<_Key_type>,  
   typename _Key_equality = std::equal_to<_Key_type>,  
   typename _Allocator_type = std::allocator<_Key_type>  
>  
, typename _Key_equality = std::equal_to<_Key_type>, typename _Allocator_type = std::allocator<_Key_type> > class concurrent_unordered_set : public details::_Concurrent_hash< details::_Concurrent_unordered_set_traits<_Key_type, details::_Hash_compare<_Key_type, _Hasher, _Key_equality>, _Allocator_type, false> >;  
```  
  
#### Параметры  
 `_Key_type`  
 Тип ключа.  
  
 `_Hasher`  
 Тип объекта хэш\-функции.  Этот аргумент является необязательным и значение по умолчанию — `std::tr1::hash<``_Key_type``>`.  
  
 `_Key_equality`  
 Тип объекта функции сравнения на предмет равенства.  Этот аргумент является необязательным и значение по умолчанию — `std::equal_to<``_Key_type``>`.  
  
 `_Allocator_type`  
 Тип, представляющий хранимый объект распределителя, инкапсулирующий сведения о распределении и освобождении памяти для параллельного неупорядоченного набора.  Этот аргумент является необязательным и значение по умолчанию — `std::allocator<``_Key_type``>`.  
  
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
|`pointer`|Тип указателя на элемент.|  
|`reference`|Тип ссылки на элемент.|  
|`size_type`|Тип беззнакового расстояния между двумя элементами.|  
|`value_type`|Тип элемента.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор concurrent\_unordered\_set::concurrent\_unordered\_set](../Topic/concurrent_unordered_set::concurrent_unordered_set%20Constructor.md)|Перегружен.  Создает параллельный неупорядоченный набор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод concurrent\_unordered\_set::hash\_function](../Topic/concurrent_unordered_set::hash_function%20Method.md)|Возвращает объект сохраненной хэш\-функции.|  
|[Метод concurrent\_unordered\_set::insert](../Topic/concurrent_unordered_set::insert%20Method.md)|Перегружен.  Добавляет элементы в объект `concurrent_unordered_set`.|  
|[Метод concurrent\_unordered\_set::key\_eq](../Topic/concurrent_unordered_set::key_eq%20Method.md)|Возвращает сохраненный объект функции проверки равенства.|  
|[Метод concurrent\_unordered\_set::swap](../Topic/concurrent_unordered_set::swap%20Method.md)|Меняет местами содержимое двух объектов `concurrent_unordered_set`.  Данный метод не безопасен в режиме параллелизма.|  
|[Метод concurrent\_unordered\_set::unsafe\_erase](../Topic/concurrent_unordered_set::unsafe_erase%20Method.md)|Перегружен.  Удаляет элементы из `concurrent_unordered_set` в указанных положениях.  Данный метод не безопасен в режиме параллелизма.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Оператор concurrent\_unordered\_set::operator\=](../Topic/concurrent_unordered_set::operator=%20Operator.md)|Перегружен.  Назначает содержимое другого объекта `concurrent_unordered_set` данному.  Данный метод не безопасен в режиме параллелизма.|  
  
## Заметки  
 Подробные сведения о классе `concurrent_unordered_set` содержатся в разделе [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Иерархия наследования  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_set`  
  
## Требования  
 **Заголовок:** concurrent\_unordered\_set.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md)