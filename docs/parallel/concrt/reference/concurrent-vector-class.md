---
title: "Класс concurrent_vector | Microsoft Docs"
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
  - "concurrent_vector/Concurrency::concurrent_vector"
  - "concurrent_vector/concurrency::concurrent_vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_vector - класс"
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс concurrent_vector
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `concurrent_vector` является классом\-контейнером последовательности, позволяющим произвольный доступ к любому элементу.  Позволяет параллельно\-безопасно выполнять операции присоединения, получения доступа к элементу, доступа к итератору и обхода итератора.  
  
## Синтаксис  
  
```  
template<  
   typename _Ty,  
   class _Ax  
>  
class concurrent_vector: protected details::_Allocator_base<_Ty, _Ax>, private details::_Concurrent_vector_base_v4;  
```  
  
#### Параметры  
 `_Ty`  
 Тип данных элементов, хранимых в векторе.  
  
 `_Ax`  
 Тип, представляющий хранимый объект распределителя, инкапсулирующий сведения о распределении и освобождении памяти для параллельного вектора.  Этот аргумент является необязательным и значение по умолчанию — `allocator<``_Ty``>`.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`allocator_type`|Тип, представляющий класс распределителя для параллельного вектора.|  
|`const_iterator`|Тип, который предоставляет итератор произвольного доступа, который может читать элемент `const` в параллельном векторе.|  
|`const_pointer`|Тип, который предоставляет указатель на элемент `const` в параллельном векторе.|  
|`const_reference`|Тип, предоставляющий ссылку на элемент `const`, хранящийся в параллельном векторе для чтения и выполнения операций `const`.|  
|`const_reverse_iterator`|Тип, который предоставляет итератор произвольного доступа, который может читать любой элемент `const` в параллельном векторе.|  
|`difference_type`|Тип, предоставляющий расстояние со знаком между двумя элементами в параллельном векторе.|  
|`iterator`|Тип, который предоставляет итератор произвольного доступа, который может читать любой элемент в параллельном векторе.  Изменение элемента с помощью итератора не является параллельно\-безопасным.|  
|`pointer`|Тип, который предоставляет указатель на элемент в параллельном векторе.|  
|`reference`|Тип, который предоставляет ссылку на элемент, хранящийся в параллельном векторе.|  
|`reverse_iterator`|Тип, который предоставляет итератор произвольного доступа, который может читать любой элемент в обратном параллельном векторе.  Изменение элемента с помощью итератора не является параллельно\-безопасным.|  
|`size_type`|Тип, который подсчитывает число элементов в параллельном векторе.|  
|`value_type`|Тип, который представляет тип данных, хранящийся в параллельном векторе.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор concurrent\_vector::concurrent\_vector](../Topic/concurrent_vector::concurrent_vector%20Constructor.md)|Перегружен.  Создает параллельный вектор.|  
|[Деструктор concurrent\_vector::~concurrent\_vector](../Topic/concurrent_vector::~concurrent_vector%20Destructor.md)|Удаляет все элементы и уничтожает параллельный вектор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод concurrent\_vector::assign](../Topic/concurrent_vector::assign%20Method.md)|Перегружен.  Удаляет элементы параллельного вектор и присваивает ему либо `_N` копий `_Item` или значения, заданные диапазоном итератора \[`_Begin`, `_End`\).  Данный метод не безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::at](../Topic/concurrent_vector::at%20Method.md)|Перегружен.  Предоставляет доступ к элементу с заданным индексом в параллельном векторе.  Этот метод является параллельно\-безопасным для операций чтения, а также при росте вектора, до тех пор, пока гарантируется, что значение `_Index` меньше, чем размер параллельного вектора.|  
|[Метод concurrent\_vector::back](../Topic/concurrent_vector::back%20Method.md)|Перегружен.  Возвращает ссылку или ссылка `const` на последний элемент в параллельном векторе.  Если параллельный вектор пуст, возвращаемое значение не определено.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::begin](../Topic/concurrent_vector::begin%20Method.md)|Перегружен.  Возвращает итератор типа `iterator` или `const_iterator` к началу параллельного вектора.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::capacity](../Topic/concurrent_vector::capacity%20Method.md)|Возвращает максимальный размер, до которого может расти параллельный вектор без необходимости выделить больше памяти.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::cbegin](../Topic/concurrent_vector::cbegin%20Method.md)|Возвращает итератор типа `const_iterator` к началу параллельного вектора.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::cend](../Topic/concurrent_vector::cend%20Method.md)|Возвращает итератор типа `const_iterator` к концу параллельного вектора.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::clear](../Topic/concurrent_vector::clear%20Method.md)|Удаляет все элементы в параллельном векторе.  Данный метод не безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::crbegin](../Topic/concurrent_vector::crbegin%20Method.md)|Возвращает итератор типа `const_reverse_iterator` к началу параллельного вектора.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::crend](../Topic/concurrent_vector::crend%20Method.md)|Возвращает итератор типа `const_reverse_iterator` к концу параллельного вектора.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::empty](../Topic/concurrent_vector::empty%20Method.md)|Проверяет, пуста ли параллельный вектор в момент, когда этот метод вызывается.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::end](../Topic/concurrent_vector::end%20Method.md)|Перегружен.  Возвращает итератор типа `iterator` или `const_iterator` к концу параллельного вектора.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::front](../Topic/concurrent_vector::front%20Method.md)|Перегружен.  Возвращает ссылку или ссылка `const` на первый элемент в параллельном векторе.  Если параллельный вектор пуст, возвращаемое значение не определено.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::get\_allocator](../Topic/concurrent_vector::get_allocator%20Method.md)|Возвращает копию распределителя, используемого для создания параллельного вектора.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::grow\_by](../Topic/concurrent_vector::grow_by%20Method.md)|Перегружен.  Увеличивает данный параллельный вектор на `_Delta` элементов.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::grow\_to\_at\_least](../Topic/concurrent_vector::grow_to_at_least%20Method.md)|Увеличивает данный параллельный вектор до тех пор, пока он не имеет по крайней мере `_N` элементов.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::max\_size](../Topic/concurrent_vector::max_size%20Method.md)|Возвращает максимальное число элементов, которое может содержать параллельный вектор.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::push\_back](../Topic/concurrent_vector::push_back%20Method.md)|Перегружен.  Добавляет заданный элемент в конец параллельного вектор.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::rbegin](../Topic/concurrent_vector::rbegin%20Method.md)|Перегружен.  Возвращает итератор типа `reverse_iterator` или `const_reverse_iterator` к началу параллельного вектора.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::rend](../Topic/concurrent_vector::rend%20Method.md)|Перегружен.  Возвращает итератор типа `reverse_iterator` или `const_reverse_iterator` к концу параллельного вектора.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::reserve](../Topic/concurrent_vector::reserve%20Method.md)|Выделяет достаточно места для увеличения параллельного вектора до размера `_N` без необходимости выделить больше памяти позднее.  Данный метод не безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::resize](../Topic/concurrent_vector::resize%20Method.md)|Перегружен.  Изменение размера параллельного вектора на запрошенный размер, удаляя или добавляя элементов при необходимости.  Данный метод не безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::shrink\_to\_fit](../Topic/concurrent_vector::shrink_to_fit%20Method.md)|Сжимает внутреннее представление параллельного вектора, чтобы сократить фрагментацию и оптимизировать использование памяти.  Данный метод не безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::size](../Topic/concurrent_vector::size%20Method.md)|Возвращает число элементов в параллельном векторе.  Данный метод безопасен в режиме параллелизма.|  
|[Метод concurrent\_vector::swap](../Topic/concurrent_vector::swap%20Method.md)|Меняет местами содержимое двух параллельных векторов.  Данный метод не безопасен в режиме параллелизма.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[concurrent\_vector::operatorOperator](../Topic/concurrent_vector::operatorOperator.md)|Перегружен.  Предоставляет доступ к элементу с заданным индексом в параллельном векторе.  Этот метод является параллельно\-безопасным для операций чтения, а также при росте вектора, до тех пор, пока гарантируется, что значение `_Index` меньше, чем размер параллельного вектора.|  
|[Оператор concurrent\_vector::operator\=](../Topic/concurrent_vector::operator=%20Operator.md)|Перегружен.  Назначает содержимое другого объекта `concurrent_vector` данному.  Данный метод не безопасен в режиме параллелизма.|  
  
## Заметки  
 Подробные сведения о классе `concurrent_vector` содержатся в разделе [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Иерархия наследования  
 `_Concurrent_vector_base_v4`  
  
 `_Allocator_base`  
  
 `concurrent_vector`  
  
## Требования  
 **Заголовок:** concurrent\_vector.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md)