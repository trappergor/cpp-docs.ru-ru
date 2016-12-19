---
title: "Класс concurrent_unordered_multiset | Microsoft Docs"
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
  - "concurrent_unordered_set/concurrency::concurrent_unordered_multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_unordered_multiset - класс"
ms.assetid: 219d7d67-1ff0-45f4-9400-e9cc272991a4
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс concurrent_unordered_multiset
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `concurrent_unordered_multiset` — это безопасный в режиме параллелизма контейнер, который управляет последовательностью элементов типа \_Key\_type переменной длины.  Последовательность представлена таким образом, который позволяет параллельно\-безопасно выполнять операции присоединения, получения доступа к элементу, доступа к итератору и обхода итератора.  
  
## Синтаксис  
  
```  
template <  
   typename _Key_type,  
   typename _Hasher = std::tr1::hash<_Key_type>,  
   typename _Key_equality = std::equal_to<_Key_type>,  
   typename _Allocator_type = std::allocator<_Key_type>  
>  
, typename _Key_equality = std::equal_to<_Key_type>, typename _Allocator_type = std::allocator<_Key_type> > class concurrent_unordered_multiset : public details::_Concurrent_hash< details::_Concurrent_unordered_set_traits<_Key_type, details::_Hash_compare<_Key_type, _Hasher, _Key_equality>, _Allocator_type, true> >;  
```  
  
#### Параметры  
 `_Key_type`  
 Тип ключа.  
  
 `_Hasher`  
 Тип объекта хэш\-функции.  Этот аргумент является необязательным и значение по умолчанию — `std::tr1::hash<``_Key_type``>`.  
  
 `_Key_equality`  
 Тип объекта функции сравнения на предмет равенства.  Этот аргумент является необязательным и значение по умолчанию — `std::equal_to<``_Key_type``>`.  
  
 `_Allocator_type`  
 Тип, представляющий хранимый объект распределителя, инкапсулирующий сведения о распределении и освобождении памяти для параллельного вектора.  Этот аргумент является необязательным и значение по умолчанию — `std::allocator<``_Key_type``>`.  
  
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
|[Конструктор concurrent\_unordered\_multiset::concurrent\_unordered\_multiset](../Topic/concurrent_unordered_multiset::concurrent_unordered_multiset%20Constructor.md)|Перегружен.  Создает параллельное неупорядоченное мультимножество.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод concurrent\_unordered\_multiset::hash\_function](../Topic/concurrent_unordered_multiset::hash_function%20Method.md)|Возвращает объект сохраненной хэш\-функции.|  
|[Метод concurrent\_unordered\_multiset::insert](../Topic/concurrent_unordered_multiset::insert%20Method.md)|Перегружен.  Добавляет элементы в объект `concurrent_unordered_multiset`.|  
|[Метод concurrent\_unordered\_multiset::key\_eq](../Topic/concurrent_unordered_multiset::key_eq%20Method.md)|Сохраненный объект функции проверки равенства.|  
|[Метод concurrent\_unordered\_multiset::swap](../Topic/concurrent_unordered_multiset::swap%20Method.md)|Меняет местами содержимое двух объектов `concurrent_unordered_multiset`.  Данный метод не безопасен в режиме параллелизма.|  
|[Метод concurrent\_unordered\_multiset::unsafe\_erase](../Topic/concurrent_unordered_multiset::unsafe_erase%20Method.md)|Перегружен.  Удаляет элементы из `concurrent_unordered_multiset` в указанных положениях.  Данный метод не безопасен в режиме параллелизма.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Оператор concurrent\_unordered\_multiset::operator\=](../Topic/concurrent_unordered_multiset::operator=%20Operator.md)|Перегружен.  Назначает содержимое другого объекта `concurrent_unordered_multiset` данному.  Данный метод не безопасен в режиме параллелизма.|  
  
## Заметки  
 Подробные сведения о классе `concurrent_unordered_multiset` содержатся в разделе [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Иерархия наследования  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_multiset`  
  
## Требования  
 **Заголовок:** concurrent\_unordered\_set.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md)