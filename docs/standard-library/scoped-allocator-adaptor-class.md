---
title: "Класс scoped_allocator_adaptor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.scoped_allocator_adaptor"
  - "scoped_allocator_adaptor"
  - "scoped_allocator/std::scoped_allocator_adaptor"
  - "std::scoped_allocator_adaptor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс scoped_allocator_adaptor"
ms.assetid: 0d9b06a1-9a4a-4669-9470-8805cae48e89
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Класс scoped_allocator_adaptor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет вложить один распределителей.  
  
## Синтаксис  
  
```cpp  
template<class Outer, class... Inner>  
    class scoped_allocator_adaptor;  
```  
  
## Заметки  
 Класс шаблона инкапсулирует вложить один одного или нескольких распределителей.  Каждый такой класс имеет внешний распределитель типа `outer_allocator_type`, синонима для `Outer`, открытая база объекта `scoped_allocator_adaptor`.  `Outer` используется для распределения памяти, который будет использовать контейнер.  Можно получить ссылку на этот базовый объект распределителя путем вызова `outer_allocator`.  
  
 Оставшаяся часть вложение имеет тип `inner_allocator_type`.  Внутренний распределитель используется для распределения памяти для элементов внутри контейнера.  Можно получить ссылку на хранимый объект этого типа путем вызова `inner_allocator`.  Если `Inner...` не установлено, `inner_allocator_type` имеет тип `scoped_allocator_adaptor<Inner...>` и `inner_allocator` обозначает объект\-член.  В противном случае `inner_allocator_type` имеет тип `scoped_allocator_adaptor<Outer>` и `inner_allocator` обозначает весь объект.  
  
 Вложить один предполагает, что он поддерживает произвольную глубину, повторяющ его самый внутренний инкапсулированный распределитель по мере необходимости.  
  
 Несколько подходов, которые не входят в состав видимой помощи интерфейса в описание расширения функциональности этого класса шаблона.  *внешний распределитель* посредничает все вызовы конструкции и удаляет методы.  Она является рекурсивной определяется функцией `OUTERMOST(X)`, где `OUTERMOST(X)` одно из следующих действий.  
  
-   Если `X.outer_allocator()` с правильным форматом, `OUTERMOST(X)``OUTERMOST(X.outer_allocator())`.  
  
-   В противном случае `OUTERMOST(X)` является `X`.  
  
 3 Типа определяются для экспозиция:  
  
|Тип|Описание|  
|---------|--------------|  
|`Outermost`|Тип `OUTERMOST(*this)`.|  
|`Outermost_traits`|`allocator_traits<Outermost>`|  
|`Outer_traits`|`allocator_traits<Outer>`|  
  
### конструкторов;  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор scoped\_allocator\_adaptor::scoped\_allocator\_adaptor](../Topic/scoped_allocator_adaptor::scoped_allocator_adaptor%20Constructor.md)|Создает объект `scoped_allocator_adaptor`.|  
  
### Определения типов  
  
|Name|Описание|  
|----------|--------------|  
|`const_pointer`|Этот тип является синонимом `const_pointer`, связанный с распределителем `Outer`.|  
|`const_void_pointer`|Этот тип является синонимом `const_void_pointer`, связанный с распределителем `Outer`.|  
|`difference_type`|Этот тип является синонимом `difference_type`, связанный с распределителем `Outer`.|  
|`inner_allocator_type`|Этот тип является синонимом типа вложенных переходники `scoped_allocator_adaptor<Inner...>`.|  
|`outer_allocator_type`|Этот тип является синонимом типа базового распределителя `Outer`.|  
|`pointer`|Этот тип является синонимом `pointer`, связанного с распределителем `Outer`.|  
|`propagate_on_container_copy_assignment`|Тип содержит значение true только в том случае, если `Outer_traits::propagate_on_container_copy_assignment` содержит значение true или `inner_allocator_type::propagate_on_container_copy_assignment` содержит значение true.|  
|`propagate_on_container_move_assignment`|Тип содержит значение true только в том случае, если `Outer_traits::propagate_on_container_move_assignment` содержит значение true или `inner_allocator_type::propagate_on_container_move_assignment` содержит значение true.|  
|`propagate_on_container_swap`|Тип содержит значение true только в том случае, если `Outer_traits::propagate_on_container_swap` содержит значение true или `inner_allocator_type::propagate_on_container_swap` содержит значение true.|  
|`size_type`|Этот тип является синонимом `size_type`, связанного с распределителем `Outer`.|  
|`value_type`|Этот тип является синонимом `value_type`, связанного с распределителем `Outer`.|  
|`void_pointer`|Этот тип является синонимом `void_pointer`, связанного с распределителем `Outer`.|  
  
### структурам;  
  
|Name|Описание|  
|----------|--------------|  
|[Структура scoped\_allocator\_adaptor::rebind](../Topic/scoped_allocator_adaptor::rebind%20Struct.md)|Определяет тип `Outer::rebind<Other>::other` синонимом `scoped_allocator_adaptor<Other, Inner...>`.|  
  
### Методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод scoped\_allocator\_adaptor::allocate](../Topic/scoped_allocator_adaptor::allocate%20Method.md)|Выделяет память с помощью распределителя `Outer`.|  
|[Метод scoped\_allocator\_adaptor::construct](../Topic/scoped_allocator_adaptor::construct%20Method.md)|Создает объект.|  
|[Метод scoped\_allocator\_adaptor::deallocate](../Topic/scoped_allocator_adaptor::deallocate%20Method.md)|Отменить объекты с помощью внешнего распределителя.|  
|[Метод scoped\_allocator\_adaptor::destroy](../Topic/scoped_allocator_adaptor::destroy%20Method.md)|Удаляет указанный объект.|  
|[Метод scoped\_allocator\_adaptor::inner\_allocator](../Topic/scoped_allocator_adaptor::inner_allocator%20Method.md)|Извлекает ссылку на сохраненный объект типа `inner_allocator_type`.|  
|[Метод scoped\_allocator\_adaptor::max\_size](../Topic/scoped_allocator_adaptor::max_size%20Method.md)|Указывает максимальное количество объектов, которые могут быть выбраны внешний распределителем.|  
|[Метод scoped\_allocator\_adaptor::outer\_allocator](../Topic/scoped_allocator_adaptor::outer_allocator%20Method.md)|Извлекает ссылку на сохраненный объект типа `outer_allocator_type`.|  
|[Метод scoped\_allocator\_adaptor::select\_on\_container\_copy\_construction](../Topic/scoped_allocator_adaptor::select_on_container_copy_construction%20Method.md)|Создает новый объект `scoped_allocator_adaptor` с каждым сохраненный объект распределителя инициализированный вызовом `select_on_container_copy_construction` для соответствующего распределителя.|  
  
## Требования  
 **Заголовок:**\<scoped\_allocator\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)