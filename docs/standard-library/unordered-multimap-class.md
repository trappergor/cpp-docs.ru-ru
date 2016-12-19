---
title: "Класс unordered_multimap | Microsoft Docs"
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
  - "unordered_map/std::tr1::unordered_multimap"
  - "tr1.unordered_multimap"
  - "unordered_multimap"
  - "std.tr1.unordered_multimap"
  - "tr1::unordered_multimap"
  - "std::tr1::unordered_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_multimap - класс"
  - "unordered_multimap - класс [TR1]"
ms.assetid: 4baead6c-5870-4b85-940f-a47d6b891c27
caps.latest.revision: 28
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс unordered_multimap
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот шаблонный класс описывает объект, управляющий последовательностью элементов типа `std::pair<const Key, Ty>` переменной длины.  Последовательность слабо упорядочена хэш\-функцией, которая разделяет последовательность в упорядоченный набор подпоследовательностей, называемых блоками.  В каждом блоке функция сравнения определяет, упорядочена ли каждая пара элементов соответствующим образом.  Каждый элемент содержит два объекта: ключ и значение сортировки.  Последовательность представляется в виде, позволяющем выполнять поиск, вставку и удаление произвольного элемента несколькими операциями, которые могут не зависеть от числа элементов в последовательности \(постоянное время\), по крайней мере, когда все блоки имеют примерно одинаковую длину.  В худшем случае, когда все элементы находятся в одном блоке, количество операций пропорционально количеству элементов в последовательности \(линейное время\).  Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.  
  
## Синтаксис  
  
```  
template<class Key,  
    class Ty,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<Key> >  
    class unordered_multimap;  
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
|[unordered\_multimap::allocator\_type](../Topic/unordered_multimap::allocator_type.md)|Тип распределителя для управления хранилищем.|  
|[unordered\_multimap::const\_iterator](../Topic/unordered_multimap::const_iterator.md)|Тип постоянного итератора для управляемой последовательности.|  
|[unordered\_multimap::const\_local\_iterator](../Topic/unordered_multimap::const_local_iterator.md)|Тип постоянного итератора блока для управляемой последовательности.|  
|[unordered\_multimap::const\_pointer](../Topic/unordered_multimap::const_pointer.md)|Тип постоянного указателя на элемент.|  
|[unordered\_multimap::const\_reference](../Topic/unordered_multimap::const_reference.md)|Тип постоянной ссылки на элемент.|  
|[unordered\_multimap::difference\_type](../Topic/unordered_multimap::difference_type.md)|Тип расстояния со знаком между двумя элементами.|  
|[unordered\_multimap::hasher](../Topic/unordered_multimap::hasher.md)|Тип хэш\-функции.|  
|[unordered\_multimap::iterator](../Topic/unordered_multimap::iterator.md)|Тип итератора для управляемой последовательности.|  
|[unordered\_multimap::key\_equal](../Topic/unordered_multimap::key_equal.md)|Тип функции сравнения.|  
|[unordered\_multimap::key\_type](../Topic/unordered_multimap::key_type.md)|Тип ключа упорядочения.|  
|[unordered\_multimap::local\_iterator](../Topic/unordered_multimap::local_iterator.md)|Тип итератора блока для управляемой последовательности.|  
|[unordered\_multimap::mapped\_type](../Topic/unordered_multimap::mapped_type.md)|Тип сопоставленного значения, связанного с каждым ключом.|  
|[unordered\_multimap::pointer](../Topic/unordered_multimap::pointer.md)|Тип указателя на элемент.|  
|[unordered\_multimap::reference](../Topic/unordered_multimap::reference.md)|Тип ссылки на элемент.|  
|[unordered\_multimap::size\_type](../Topic/unordered_multimap::size_type.md)|Тип беззнакового расстояния между двумя элементами.|  
|[unordered\_multimap::value\_type](../Topic/unordered_multimap::value_type.md)|Тип элемента.|  
  
|||  
|-|-|  
|Функция\-член|Описание|  
|[unordered\_multimap::begin](../Topic/unordered_multimap::begin.md)|Задает начало управляемой последовательности.|  
|[unordered\_multimap::bucket](../Topic/unordered_multimap::bucket.md)|Получает номер блока для значения ключа.|  
|[unordered\_multimap::bucket\_count](../Topic/unordered_multimap::bucket_count.md)|Получает количество блоков.|  
|[unordered\_multimap::bucket\_size](../Topic/unordered_multimap::bucket_size.md)|Получает размер блока.|  
|[unordered\_multimap::cbegin](../Topic/unordered_multimap::cbegin.md)|Задает начало управляемой последовательности.|  
|[unordered\_multimap::cend](../Topic/unordered_multimap::cend.md)|Задает конец управляемой последовательности.|  
|[unordered\_multimap::clear](../Topic/unordered_multimap::clear.md)|Удаляет все элементы.|  
|[unordered\_multimap::count](../Topic/unordered_multimap::count.md)|Определяет количество элементов, соответствующих заданному ключу.|  
|[unordered\_multimap::emplace](../Topic/unordered_multimap::emplace.md)|Добавляет элемент, созданный на месте.|  
|[unordered\_multimap::emplace\_hint](../Topic/unordered_multimap::emplace_hint.md)|Добавляет элемент, созданный на месте, с подсказкой.|  
|[unordered\_multimap::empty](../Topic/unordered_multimap::empty.md)|Проверяет отсутствие элементов.|  
|[unordered\_multimap::end](../Topic/unordered_multimap::end.md)|Задает конец управляемой последовательности.|  
|[unordered\_multimap::equal\_range](../Topic/unordered_multimap::equal_range.md)|Находит диапазон, соответствующий указанному ключу.|  
|[unordered\_multimap::erase](../Topic/unordered_multimap::erase.md)|Удаляет элементы в указанных позициях.|  
|[unordered\_multimap::find](../Topic/unordered_multimap::find.md)|Определяет элемент, соответствующий указанному ключу.|  
|[unordered\_multimap::get\_allocator](../Topic/unordered_multimap::get_allocator.md)|Возвращает сохраненный объект распределителя.|  
|[unordered\_multimap::hash\_function](../Topic/unordered_multimap::hash_function.md)|Получает сохраненный объект хэш\-функции.|  
|[unordered\_multimap::insert](../Topic/unordered_multimap::insert.md)|Добавляет элементы.|  
|[unordered\_multimap::key\_eq](../Topic/unordered_multimap::key_eq.md)|Получает сохраненный объект функции сравнения.|  
|[unordered\_multimap::load\_factor](../Topic/unordered_multimap::load_factor.md)|Подсчитывает среднее число элементов в блоке.|  
|[unordered\_multimap::max\_bucket\_count](../Topic/unordered_multimap::max_bucket_count.md)|Получает максимальное количество блоков.|  
|[unordered\_multimap::max\_load\_factor](../Topic/unordered_multimap::max_load_factor.md)|Возвращает или задает максимальное количество элементов в блоке.|  
|[unordered\_multimap::max\_size](../Topic/unordered_multimap::max_size.md)|Возвращает максимальный размер управляемой последовательности.|  
|[unordered\_multimap::rehash](../Topic/unordered_multimap::rehash.md)|Повторно создает хэш\-таблицу.|  
|[unordered\_multimap::size](../Topic/unordered_multimap::size.md)|Подсчитывает количество элементов.|  
|[unordered\_multimap::swap](../Topic/unordered_multimap::swap.md)|Меняет местами содержимое двух контейнеров.|  
|[unordered\_multimap::unordered\_multimap](../Topic/unordered_multimap::unordered_multimap.md)|Создает объект контейнера.|  
  
|||  
|-|-|  
|Оператор|Описание|  
|[unordered\_multimap::operator\=](../Topic/unordered_multimap::operator=.md)|Копирует хэш\-таблицу.|  
  
## Заметки  
 Объект упорядочивает управляемую им последовательность путем вызова двух сохраненных объектов, объекта функции сравнения типа [unordered\_multimap::key\_equal](../Topic/unordered_multimap::key_equal.md) и объекта хэш\-функции типа [unordered\_multimap::hasher](../Topic/unordered_multimap::hasher.md).  Доступ к первому сохраненному объекту можно получить, вызвав функцию\-член [unordered\_multimap::key\_eq](../Topic/unordered_multimap::key_eq.md)`()`; доступ ко второму сохраненному объекту выполняется путем вызова функции\-члена [unordered\_multimap::hash\_function](../Topic/unordered_multimap::hash_function.md)`()`.  В частности, для всех значений `X` и `Y` типа `Key` вызов `key_eq()(X, Y)` возвращает значение true, только если два значения аргументов имеют соответствующий порядок; вызов `hash_function()(keyval)` создает распределение значений типа `size_t`.  В отличие от шаблонного класса [Класс unordered\_map](../standard-library/unordered-map-class.md) объект шаблонного класса `unordered_multimap` не гарантирует, что `key_eq()(X, Y)` всегда имеет значение false для любых двух элементов управляемой последовательности. \(Ключи не обязательно должны быть уникальными.\)  
  
 Объект также хранит максимальный коэффициент нагрузки, который определяет максимальное желаемое среднее количество элементов в блоке.  Если вставка элемента вызывает превышение значением [unordered\_multimap::load\_factor](../Topic/unordered_multimap::load_factor.md)`()` максимального коэффициента нагрузки, контейнер увеличивает количество блоков и перестраивает хэш\-таблицу по мере необходимости.  
  
 Фактический порядок элементов в управляемой последовательности зависит от хэш\-функции, функции сравнения, порядка вставки, максимального коэффициента нагрузки и текущего числа блоков.  Обычно невозможно предсказать порядок элементов в управляемой последовательности.  Однако всегда можно сохранять уверенность, что любое подмножество элементов, имеющих соответствующий порядок, будет расположено по соседству в управляемой последовательности.  
  
 Объект выделяет и освобождает хранилище для управляемой им последовательности с помощью сохраненного объекта распределителя типа [unordered\_multimap::allocator\_type](../Topic/unordered_multimap::allocator_type.md).  Такой объект распределителя должен иметь такой же внешний интерфейс, как объект шаблонного класса `allocator`.  Обратите внимание, что сохраненный объект распределителя не копируется, когда назначается объект контейнера.  
  
## Требования  
 **Заголовок:** \<unordered\_map\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<unordered\_map\>](../standard-library/unordered-map.md)   
 [Контейнеры](../Topic/Containers%20\(Modern%20C++\).md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)