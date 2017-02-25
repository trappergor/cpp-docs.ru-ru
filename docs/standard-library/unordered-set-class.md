---
title: "Класс unordered_set | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.unordered_set"
  - "std::tr1::unordered_set"
  - "unordered_set/std::tr1::unordered_set"
  - "tr1::unordered_set"
  - "unordered_set"
  - "tr1.unordered_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_set - класс"
  - "unordered_set - класс [TR1]"
ms.assetid: ac08084e-05a7-48c0-9ae4-d40c529922dd
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# Класс unordered_set
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот шаблонный класс описывает объект, управляющий последовательностью элементов типа `const Key` переменной длины.  Последовательность слабо упорядочена хэш\-функцией, которая разделяет последовательность в упорядоченный набор подпоследовательностей, называемых блоками.  В каждом блоке функция сравнения определяет, упорядочена ли каждая пара элементов соответствующим образом.  Каждый элемент используется в качестве ключа сортировки и в качестве значения.  Последовательность представляется в виде, позволяющем выполнять поиск, вставку и удаление произвольного элемента несколькими операциями, которые могут не зависеть от числа элементов в последовательности \(постоянное время\), по крайней мере, когда все блоки имеют примерно одинаковую длину.  В худшем случае, когда все элементы находятся в одном блоке, количество операций пропорционально количеству элементов в последовательности \(линейное время\).  Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.  
  
## Синтаксис  
  
```  
template<class Key,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<Key> >  
    class unordered_set;  
```  
  
#### Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Key`|Тип ключа.|  
|`Hash`|Тип объекта хэш\-функции.|  
|`Pred`|Тип объекта функции сравнения на предмет равенства.|  
|`Alloc`|Класс распределителя.|  
  
## Члены  
  
|||  
|-|-|  
|Определение типа|Описание|  
|[unordered\_set::allocator\_type](../Topic/unordered_set::allocator_type.md)|Тип распределителя для управления хранилищем.|  
|[unordered\_set::const\_iterator](../Topic/unordered_set::const_iterator.md)|Тип постоянного итератора для управляемой последовательности.|  
|[unordered\_set::const\_local\_iterator](../Topic/unordered_set::const_local_iterator.md)|Тип постоянного итератора блока для управляемой последовательности.|  
|[unordered\_set::const\_pointer](../Topic/unordered_set::const_pointer.md)|Тип постоянного указателя на элемент.|  
|[unordered\_set::const\_reference](../Topic/unordered_set::const_reference.md)|Тип постоянной ссылки на элемент.|  
|[unordered\_set::difference\_type](../Topic/unordered_set::difference_type.md)|Тип расстояния со знаком между двумя элементами.|  
|[unordered\_set::hasher](../Topic/unordered_set::hasher.md)|Тип хэш\-функции.|  
|[unordered\_set::iterator](../Topic/unordered_set::iterator.md)|Тип итератора для управляемой последовательности.|  
|[unordered\_set::key\_equal](../Topic/unordered_set::key_equal.md)|Тип функции сравнения.|  
|[unordered\_set::key\_type](../Topic/unordered_set::key_type.md)|Тип ключа упорядочения.|  
|[unordered\_set::local\_iterator](../Topic/unordered_set::local_iterator.md)|Тип итератора блока для управляемой последовательности.|  
|[unordered\_set::pointer](../Topic/unordered_set::pointer.md)|Тип указателя на элемент.|  
|[unordered\_set::reference](../Topic/unordered_set::reference.md)|Тип ссылки на элемент.|  
|[unordered\_set::size\_type](../Topic/unordered_set::size_type.md)|Тип беззнакового расстояния между двумя элементами.|  
|[unordered\_set::value\_type](../Topic/unordered_set::value_type.md)|Тип элемента.|  
  
|||  
|-|-|  
|Функция\-член|Описание|  
|[unordered\_set::begin](../Topic/unordered_set::begin.md)|Задает начало управляемой последовательности.|  
|[unordered\_set::bucket](../Topic/unordered_set::bucket.md)|Получает номер блока для значения ключа.|  
|[unordered\_set::bucket\_count](../Topic/unordered_set::bucket_count.md)|Получает количество блоков.|  
|[unordered\_set::bucket\_size](../Topic/unordered_set::bucket_size.md)|Получает размер блока.|  
|[unordered\_set::cbegin](../Topic/unordered_set::cbegin.md)|Задает начало управляемой последовательности.|  
|[unordered\_set::cend](../Topic/unordered_set::cend.md)|Задает конец управляемой последовательности.|  
|[unordered\_set::clear](../Topic/unordered_set::clear.md)|Удаляет все элементы.|  
|[unordered\_set::count](../Topic/unordered_set::count.md)|Определяет количество элементов, соответствующих заданному ключу.|  
|[unordered\_set::emplace](../Topic/unordered_set::emplace.md)|Добавляет элемент, созданный на месте.|  
|[unordered\_set::emplace\_hint](../Topic/unordered_set::emplace_hint.md)|Добавляет элемент, созданный на месте, с подсказкой.|  
|[unordered\_set::empty](../Topic/unordered_set::empty.md)|Проверяет отсутствие элементов.|  
|[unordered\_set::end](../Topic/unordered_set::end.md)|Задает конец управляемой последовательности.|  
|[unordered\_set::equal\_range](../Topic/unordered_set::equal_range.md)|Находит диапазон, соответствующий указанному ключу.|  
|[unordered\_set::erase](../Topic/unordered_set::erase.md)|Удаляет элементы в указанных позициях.|  
|[unordered\_set::find](../Topic/unordered_set::find.md)|Определяет элемент, соответствующий указанному ключу.|  
|[unordered\_set::get\_allocator](../Topic/unordered_set::get_allocator.md)|Возвращает сохраненный объект распределителя.|  
|[unordered\_set::hash\_function](../Topic/unordered_set::hash_function.md)|Получает сохраненный объект хэш\-функции.|  
|[unordered\_set::insert](../Topic/unordered_set::insert.md)|Добавляет элементы.|  
|[unordered\_set::key\_eq](../Topic/unordered_set::key_eq.md)|Получает сохраненный объект функции сравнения.|  
|[unordered\_set::load\_factor](../Topic/unordered_set::load_factor.md)|Подсчитывает среднее число элементов в блоке.|  
|[unordered\_set::max\_bucket\_count](../Topic/unordered_set::max_bucket_count.md)|Получает максимальное количество блоков.|  
|[unordered\_set::max\_load\_factor](../Topic/unordered_set::max_load_factor.md)|Возвращает или задает максимальное количество элементов в блоке.|  
|[unordered\_set::max\_size](../Topic/unordered_set::max_size.md)|Возвращает максимальный размер управляемой последовательности.|  
|[unordered\_set::rehash](../Topic/unordered_set::rehash.md)|Повторно создает хэш\-таблицу.|  
|[unordered\_set::size](../Topic/unordered_set::size.md)|Подсчитывает количество элементов.|  
|[unordered\_set::swap](../Topic/unordered_set::swap.md)|Меняет местами содержимое двух контейнеров.|  
|[unordered\_set::unordered\_set](../Topic/unordered_set::unordered_set.md)|Создает объект контейнера.|  
  
|||  
|-|-|  
|Операторы|Описание|  
|[unordered\_set::operator\=](../Topic/unordered_set::operator=.md)|Копирует хэш\-таблицу.|  
  
## Заметки  
 Объект упорядочивает управляемую им последовательность путем вызова двух сохраненных объектов, объекта функции сравнения типа [unordered\_set::key\_equal](../Topic/unordered_set::key_equal.md) и объекта хэш\-функции типа [unordered\_set::hasher](../Topic/unordered_set::hasher.md).  Доступ к первому сохраненному объекту можно получить, вызвав функцию\-член [unordered\_set::key\_eq](../Topic/unordered_set::key_eq.md)`()`; доступ ко второму сохраненному объекту выполняется путем вызова функции\-члена [unordered\_set::hash\_function](../Topic/unordered_set::hash_function.md)`()`.  В частности, для всех значений `X` и `Y` типа `Key` вызов `key_eq()(X, Y)` возвращает значение true, только если два значения аргументов имеют соответствующий порядок; вызов `hash_function()(keyval)` создает распределение значений типа `size_t`.  В отличие от класса шаблона [Класс unordered\_multiset](../standard-library/unordered-multiset-class.md) объект класса шаблона `unordered_set` гарантирует, что `key_eq()(X, Y)` всегда имеет значение false для любых двух элементов управляемой последовательности. \(Ключи уникальны\).  
  
 Объект также хранит максимальный коэффициент нагрузки, который определяет максимальное желаемое среднее количество элементов в блоке.  Если вставка элемента вызывает превышение значением [unordered\_set::load\_factor](../Topic/unordered_set::load_factor.md)`()` максимального коэффициента нагрузки, контейнер увеличивает количество блоков и перестраивает хэш\-таблицу по мере необходимости.  
  
 Фактический порядок элементов в управляемой последовательности зависит от хэш\-функции, функции сравнения, порядка вставки, максимального коэффициента нагрузки и текущего числа блоков.  Обычно невозможно предсказать порядок элементов в управляемой последовательности.  Однако всегда можно сохранять уверенность, что любое подмножество элементов, имеющих соответствующий порядок, будет расположено по соседству в управляемой последовательности.  
  
 Объект выделяет и освобождает хранилище для управляемой им последовательности с помощью сохраненного объекта распределителя типа [unordered\_set::allocator\_type](../Topic/unordered_set::allocator_type.md).  Такой объект распределителя должен иметь такой же внешний интерфейс, как объект шаблонного класса `allocator`.  Обратите внимание, что сохраненный объект распределителя не копируется, когда назначается объект контейнера.  
  
## Требования  
 **Заголовок:** \<unordered\_set\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<unordered\_set\>](../standard-library/unordered-set.md)   
 [Контейнеры](../Topic/Containers%20\(Modern%20C++\).md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)