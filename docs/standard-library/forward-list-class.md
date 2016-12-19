---
title: "Класс forward_list | Microsoft Docs"
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
  - "std::forward_list"
  - "forward_list"
  - "forward_list/std::forward_list"
  - "std.forward_list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "forward_list - класс"
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
caps.latest.revision: 25
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс forward_list
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, управляющий последовательностью элементов переменной длины.  Последовательность хранится в виде однонаправленного связного списка узлов, каждый из которых содержит член типа `Type`.  
  
## Синтаксис  
  
```  
template<  
    class Type,   
    class Allocator = allocator<Type>   
>  
class forward_list   
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`Type`|Тип данных элементов, сохраняемых в forward\_list.|  
|`Allocator`|Сохраненный объект распределителя, содержащий сведения о распределении и отмене распределения памяти для списка forward\_list.  Этот параметр является необязательным.  Значение по умолчанию — allocator\<`Type`\>.|  
  
## Заметки  
 Объект `forward_list` выделяет и освобождает память для управляемой им последовательности с помощью сохраненного объекта класса `Allocator`, основанного на [Класс allocator](../standard-library/allocator-class.md) \(который часто называют `std::allocator)`\).  Дополнительные сведения см. в статье [Распределители](../Topic/Allocators.md).  У объекта распределителя должен быть такой же внешний интерфейс, как у объекта класса шаблона `allocator`.  
  
> [!NOTE]
>  Сохраненный объект распределителя не копируется, когда назначается объект контейнера.  
  
 Итераторы, указатели и ссылки могут стать недопустимыми, если элементы их управляемой последовательности удаляются c помощью `forward_list`.  Операции вставки и срезов, выполняемые над управляемой последовательностью с помощью `forward_list`, не делают итераторы недействительными.  
  
 Дополнения к управляемой последовательности могут возникнуть при вызове метода [forward\_list::insert\_after](../Topic/forward_list::insert_after.md), который является единственной функцией\-членом, вызывающей конструктор `Type(const _Type&)`.  `forward_list` также может вызывать конструкторы перемещения.  Если такое выражение создает исключение, объект\-контейнер не вставляет новые элементы и повторно создает исключение.  Таким образом объект класса шаблона `forward_list` остается в известном состоянии при возникновении таких исключений.  
  
### Конструкторы  
  
|||  
|-|-|  
|[forward\_list](../Topic/forward_list::forward_list.md)|Создает объект типа `forward_list`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/forward_list::allocator_type.md)|Тип, представляющий класс распределителя для объекта прямого списка.|  
|[const\_iterator](../Topic/forward_list::const_iterator.md)|Тип, предоставляющий константный итератор для прямого списка.|  
|[const\_pointer](../Topic/forward_list::const_pointer.md)|Тип, предоставляющий указатель на элемент `const` в прямом списке.|  
|[const\_reference](../Topic/forward_list::const_reference.md)|Тип, предоставляющий константную ссылку на элемент в прямом списке.|  
|[difference\_type](../Topic/forward_list::difference_type.md)|Тип целого числа со знаком, который можно использовать для представления количества элементов в прямом списке в диапазоне между элементами, на которые указывают итераторы.|  
|[iterator](../Topic/forward_list::iterator.md)|Тип, предоставляющий итератор для прямого списка.|  
|[pointer](../Topic/forward_list::pointer.md)|Тип, предоставляющий указатель на элемент в прямом списке.|  
|[ссылка](../Topic/forward_list::reference.md)|Тип, предоставляющий ссылку на элемент в прямом списке.|  
|[size\_type](../Topic/forward_list::size_type.md)|Тип, представляющий беззнаковое расстояние между двумя элементами.|  
|[value\_type](../Topic/forward_list::value_type.md)|Тип, представляющий тип элемента, хранящегося в прямом списке.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[assign](../Topic/forward_list::assign.md)|Удаляет элементы из прямого списка и копирует новый набор элементов в целевой прямой список.|  
|[before\_begin](../Topic/forward_list::before_begin.md)|Возвращает итератор, указывающий на позицию перед первым элементом в прямом списке.|  
|[begin](../Topic/forward_list::begin.md)|Возвращает итератор, указывающий на первый элемент в прямом списке.|  
|[cbefore\_begin](../Topic/forward_list::cbefore_begin.md)|Возвращает константный итератор, указывающий на позицию перед первым элементом в прямом списке.|  
|[cbegin](../Topic/forward_list::cbegin.md)|Возвращает константный итератор, обращающийся к первому элементу в прямом списке.|  
|[cend](../Topic/forward_list::cend.md)|Возвращает константный итератор, адресующий расположение после последнего элемента в прямом списке.|  
|[очистить](../Topic/forward_list::clear.md)|Удаляет все элементы прямого списка.|  
|[emplace\_after](../Topic/forward_list::emplace_after.md)|Создает с перемещением новый элемент после указанной позиции.|  
|[emplace\_front](../Topic/forward_list::emplace_front.md)|Добавляет элемент, созданный на месте, в начало списка.|  
|[пустой](../Topic/forward_list::empty.md)|Проверяет, пуст ли прямой список.|  
|[end](../Topic/forward_list::end.md)|Возвращает итератор, адресующий расположение после последнего элемента в прямом списке.|  
|[erase\_after](../Topic/forward_list::erase_after.md)|Удаляет элементы из прямого списка после указанной позиции.|  
|[front](../Topic/forward_list::front.md)|Возвращает ссылку на первый элемент в прямом списке.|  
|[get\_allocator](../Topic/forward_list::get_allocator.md)|Возвращает копию объекта объекта распределителя, использованного для создания прямого списка.|  
|[insert\_after](../Topic/forward_list::insert_after.md)|Добавляет элементы в прямой список после указанной позиции.|  
|[max\_size](../Topic/forward_list::max_size.md)|Возвращает максимальную длину прямого списка.|  
|[объединить](../Topic/forward_list::merge.md)|Удаляет элементы из списка аргументов, вставляет их в целевой прямой список и сортирует новый объединенный набор элементов по возрастанию или в ином указанном порядке.|  
|[pop\_front](../Topic/forward_list::pop_front.md)|Удаляет элемент в начале прямого списка.|  
|[push\_front](../Topic/forward_list::push_front.md)|Добавляет элемент в начало прямого списка.|  
|[remove](../Topic/forward_list::remove.md)|Удаляет из прямого списка элементы, совпадающие с заданным значением.|  
|[remove\_if](../Topic/forward_list::remove_if.md)|Удаляет из прямого списка элементы, для которых выполняется заданное условие.|  
|[изменение размера](../Topic/forward_list::resize.md)|Указывает новый размер прямого списка.|  
|[reverse](../Topic/forward_list::reverse.md)|Изменяет порядок следования элементов в прямом списке на обратный.|  
|[sort](../Topic/forward_list::sort.md)|Упорядочивает элементы по возрастанию или по порядку, указанному предикатом.|  
|[splice\_after](../Topic/forward_list::splice_after.md)|Восстанавливает ссылки между узлами.|  
|[swap](../Topic/forward_list::swap.md)|Меняет местами элементы двух прямых списков.|  
|[unique](../Topic/forward_list::unique.md)|Удаляет смежные элементы, которые прошли заданный тест.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator \=](../Topic/forward_list::operator=.md)|Заменяет элементы прямого списка копией другого прямого списка.|  
  
## Требования  
 **Заголовок:** \<forward\_list\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<forward\_list\>](../standard-library/forward-list.md)