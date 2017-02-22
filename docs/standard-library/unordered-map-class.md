---
title: "Класс unordered_map | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::unordered_map"
  - "std.tr1.unordered_map"
  - "tr1.unordered_map"
  - "tr1::unordered_map"
  - "unordered_map"
  - "unordered_map/std::tr1::unordered_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_map - класс"
  - "unordered_map - класс [TR1]"
ms.assetid: 7cf7cfa1-16e7-461c-a9b2-3b8d8ec24e0d
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс unordered_map
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот шаблонный класс описывает объект, управляющий последовательностью элементов типа `std::pair<const Key, Ty>` переменной длины.  Последовательность слабо упорядочена хэш\-функцией, которая разделяет последовательность в упорядоченный набор подпоследовательностей, называемых блоками.  В каждом блоке функция сравнения определяет, упорядочена ли каждая пара элементов соответствующим образом.  Каждый элемент содержит два объекта: ключ и значение сортировки.  Последовательность представляется в виде, позволяющем выполнять поиск, вставку и удаление произвольного элемента несколькими операциями, которые могут не зависеть от числа элементов в последовательности \(постоянное время\), по крайней мере, когда все блоки имеют примерно одинаковую длину.  В худшем случае, когда все элементы находятся в одном блоке, количество операций пропорционально количеству элементов в последовательности \(линейное время\).  Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.  
  
## Синтаксис  
  
```  
template<class Key,  
    class Ty,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<std::pair<const Key, Ty> > >  
    class unordered_map;  
```  
  
#### Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Key`|Тип ключа.|  
|`Ty`|Сопоставленный тип.|  
|`Hash`|Тип объекта хэш\-функции.|  
|`Pred`|Тип объекта функции сравнения на предмет равенства.|  
|`Alloc`|Класс распределителя.|  
  
## Члены  
  
|||  
|-|-|  
|Определение типа|Описание|  
|[unordered\_map::allocator\_type](../Topic/unordered_map::allocator_type.md)|Тип распределителя для управления хранилищем.|  
|[unordered\_map::const\_iterator](../Topic/unordered_map::const_iterator.md)|Тип постоянного итератора для управляемой последовательности.|  
|[unordered\_map::const\_local\_iterator](../Topic/unordered_map::const_local_iterator.md)|Тип постоянного итератора блока для управляемой последовательности.|  
|[unordered\_map::const\_pointer](../Topic/unordered_map::const_pointer.md)|Тип постоянного указателя на элемент.|  
|[unordered\_map::const\_reference](../Topic/unordered_map::const_reference.md)|Тип постоянной ссылки на элемент.|  
|[unordered\_map::difference\_type](../Topic/unordered_map::difference_type.md)|Тип расстояния со знаком между двумя элементами.|  
|[unordered\_map::hasher](../Topic/unordered_map::hasher.md)|Тип хэш\-функции.|  
|[unordered\_map::iterator](../Topic/unordered_map::iterator.md)|Тип итератора для управляемой последовательности.|  
|[unordered\_map::key\_equal](../Topic/unordered_map::key_equal.md)|Тип функции сравнения.|  
|[unordered\_map::key\_type](../Topic/unordered_map::key_type.md)|Тип ключа упорядочения.|  
|[unordered\_map::local\_iterator](../Topic/unordered_map::local_iterator.md)|Тип итератора блока для управляемой последовательности.|  
|[unordered\_map::mapped\_type](../Topic/unordered_map::mapped_type.md)|Тип сопоставленного значения, связанного с каждым ключом.|  
|[unordered\_map::pointer](../Topic/unordered_map::pointer.md)|Тип указателя на элемент.|  
|[unordered\_map::reference](../Topic/unordered_map::reference.md)|Тип ссылки на элемент.|  
|[unordered\_map::size\_type](../Topic/unordered_map::size_type.md)|Тип беззнакового расстояния между двумя элементами.|  
|[unordered\_map::value\_type](../Topic/unordered_map::value_type.md)|Тип элемента.|  
  
|||  
|-|-|  
|Функция\-член|Описание|  
|[unordered\_map::at](../Topic/unordered_map::at.md)|Поиск элемента с заданным ключом.|  
|[unordered\_map::begin](../Topic/unordered_map::begin.md)|Задает начало управляемой последовательности.|  
|[unordered\_map::bucket](../Topic/unordered_map::bucket.md)|Получает номер блока для значения ключа.|  
|[unordered\_map::bucket\_count](../Topic/unordered_map::bucket_count.md)|Получает количество блоков.|  
|[unordered\_map::bucket\_size](../Topic/unordered_map::bucket_size.md)|Получает размер блока.|  
|[unordered\_map::cbegin](../Topic/unordered_map::cbegin.md)|Задает начало управляемой последовательности.|  
|[unordered\_map::cend](../Topic/unordered_map::cend.md)|Задает конец управляемой последовательности.|  
|[unordered\_map::clear](../Topic/unordered_map::clear.md)|Удаляет все элементы.|  
|[unordered\_map::count](../Topic/unordered_map::count.md)|Определяет количество элементов, соответствующих заданному ключу.|  
|[unordered\_map::emplace](../Topic/unordered_map::emplace.md)|Добавляет элемент, созданный на месте.|  
|[unordered\_map::emplace\_hint](../Topic/unordered_map::emplace_hint.md)|Добавляет элемент, созданный на месте, с подсказкой.|  
|[unordered\_map::empty](../Topic/unordered_map::empty.md)|Проверяет отсутствие элементов.|  
|[unordered\_map::end](../Topic/unordered_map::end.md)|Задает конец управляемой последовательности.|  
|[unordered\_map::equal\_range](../Topic/unordered_map::equal_range.md)|Находит диапазон, соответствующий указанному ключу.|  
|[unordered\_map::erase](../Topic/unordered_map::erase.md)|Удаляет элементы в указанных позициях.|  
|[unordered\_map::find](../Topic/unordered_map::find.md)|Определяет элемент, соответствующий указанному ключу.|  
|[unordered\_map::get\_allocator](../Topic/unordered_map::get_allocator.md)|Возвращает сохраненный объект распределителя.|  
|[unordered\_map::hash\_function](../Topic/unordered_map::hash_function.md)|Получает сохраненный объект хэш\-функции.|  
|[unordered\_map::insert](../Topic/unordered_map::insert.md)|Добавляет элементы.|  
|[unordered\_map::key\_eq](../Topic/unordered_map::key_eq.md)|Получает сохраненный объект функции сравнения.|  
|[unordered\_map::load\_factor](../Topic/unordered_map::load_factor.md)|Подсчитывает среднее число элементов в блоке.|  
|[unordered\_map::max\_bucket\_count](../Topic/unordered_map::max_bucket_count.md)|Получает максимальное количество блоков.|  
|[unordered\_map::max\_load\_factor](../Topic/unordered_map::max_load_factor.md)|Возвращает или задает максимальное количество элементов в блоке.|  
|[unordered\_map::max\_size](../Topic/unordered_map::max_size.md)|Возвращает максимальный размер управляемой последовательности.|  
|[unordered\_map::rehash](../Topic/unordered_map::rehash.md)|Повторно создает хэш\-таблицу.|  
|[unordered\_map::size](../Topic/unordered_map::size.md)|Подсчитывает количество элементов.|  
|[unordered\_map::swap](../Topic/unordered_map::swap.md)|Меняет местами содержимое двух контейнеров.|  
|[unordered\_map::unordered\_map](../Topic/unordered_map::unordered_map.md)|Создает объект контейнера.|  
  
|||  
|-|-|  
|Оператор|Описание|  
|[unordered\_map::operator](../Topic/unordered_map::operator.md)|Находит или вставляет элемент с указанным ключом.|  
|[unordered\_map::operator\=](../Topic/unordered_map::operator=.md)|Копирует хэш\-таблицу.|  
  
## Заметки  
 Объект упорядочивает управляемую им последовательность путем вызова двух сохраненных объектов, объекта функции сравнения типа [unordered\_map::key\_equal](../Topic/unordered_map::key_equal.md) и объекта хэш\-функции типа [unordered\_map::hasher](../Topic/unordered_map::hasher.md).  Доступ к первому сохраненному объекту можно получить, вызвав функцию\-член [unordered\_map::key\_eq](../Topic/unordered_map::key_eq.md)`()`; доступ ко второму сохраненному объекту выполняется путем вызова функции\-члена [unordered\_map::hash\_function](../Topic/unordered_map::hash_function.md)`()`.  В частности, для всех значений `X` и `Y` типа `Key` вызов `key_eq()(X, Y)` возвращает значение true, только если два значения аргументов имеют соответствующий порядок; вызов `hash_function()(keyval)` создает распределение значений типа `size_t`.  В отличие от класса шаблона [Класс unordered\_multimap](../standard-library/unordered-multimap-class.md) объект класса шаблона `unordered_map` гарантирует, что `key_eq()(X, Y)` всегда имеет значение false для любых двух элементов управляемой последовательности. \(Ключи уникальны\).  
  
 Объект также хранит максимальный коэффициент нагрузки, который определяет максимальное желаемое среднее количество элементов в блоке.  Если вставка элемента вызывает превышение значением [unordered\_map::load\_factor](../Topic/unordered_map::load_factor.md)`()` максимального коэффициента нагрузки, контейнер увеличивает количество блоков и перестраивает хэш\-таблицу по мере необходимости.  
  
 Фактический порядок элементов в управляемой последовательности зависит от хэш\-функции, функции сравнения, порядка вставки, максимального коэффициента нагрузки и текущего числа блоков.  Обычно невозможно предсказать порядок элементов в управляемой последовательности.  Однако всегда можно сохранять уверенность, что любое подмножество элементов, имеющих соответствующий порядок, будет расположено по соседству в управляемой последовательности.  
  
 Объект выделяет и освобождает хранилище для управляемой им последовательности с помощью сохраненного объекта распределителя типа [unordered\_map::allocator\_type](../Topic/unordered_map::allocator_type.md).  Такой объект распределителя должен иметь такой же внешний интерфейс, как объект шаблонного класса `allocator`.  Обратите внимание, что сохраненный объект распределителя не копируется, когда назначается объект контейнера.  
  
## Требования  
 **Заголовок:** \<unordered\_map\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [Контейнеры](../Topic/Containers%20\(Modern%20C++\).md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)