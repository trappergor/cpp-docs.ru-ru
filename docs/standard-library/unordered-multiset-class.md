---
title: "Класс unordered_multiset | Microsoft Docs"
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
  - "tr1::unordered_multiset"
  - "std::tr1::unordered_multiset"
  - "unordered_multiset"
  - "std.tr1.unordered_multiset"
  - "unordered_set/std::tr1::unordered_multiset"
  - "tr1.unordered_multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unordered_multiset - класс"
  - "unordered_multiset - класс [TR1]"
ms.assetid: 70c8dfc5-492a-4af2-84f5-1aa9cb04b71c
caps.latest.revision: 24
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс unordered_multiset
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот шаблонный класс описывает объект, управляющий последовательностью элементов типа `const Key` переменной длины.  Последовательность слабо упорядочена хэш\-функцией, которая разделяет последовательность в упорядоченный набор подпоследовательностей, называемых блоками.  В каждом блоке функция сравнения определяет, упорядочена ли каждая пара элементов соответствующим образом.  Каждый элемент используется в качестве ключа сортировки и в качестве значения.  Последовательность представляется в виде, позволяющем выполнять поиск, вставку и удаление произвольного элемента несколькими операциями, которые могут не зависеть от числа элементов в последовательности \(постоянное время\), по крайней мере, когда все блоки имеют примерно одинаковую длину.  В худшем случае, когда все элементы находятся в одном блоке, количество операций пропорционально количеству элементов в последовательности \(линейное время\).  Кроме того, вставка элементов не делает итераторы недействительными, а при удалении элементов недействительными становятся только итераторы, указывающие на удаленный элемент.  
  
## Синтаксис  
  
```  
template<class Key,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<Key> >  
    class unordered_multiset;  
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
|[unordered\_multiset::allocator\_type](../Topic/unordered_multiset::allocator_type.md)|Тип распределителя для управления хранилищем.|  
|[unordered\_multiset::const\_iterator](../Topic/unordered_multiset::const_iterator.md)|Тип постоянного итератора для управляемой последовательности.|  
|[unordered\_multiset::const\_local\_iterator](../Topic/unordered_multiset::const_local_iterator.md)|Тип постоянного итератора блока для управляемой последовательности.|  
|[unordered\_multiset::const\_pointer](../Topic/unordered_multiset::const_pointer.md)|Тип постоянного указателя на элемент.|  
|[unordered\_multiset::const\_reference](../Topic/unordered_multiset::const_reference.md)|Тип постоянной ссылки на элемент.|  
|[unordered\_multiset::difference\_type](../Topic/unordered_multiset::difference_type.md)|Тип расстояния со знаком между двумя элементами.|  
|[unordered\_multiset::hasher](../Topic/unordered_multiset::hasher.md)|Тип хэш\-функции.|  
|[unordered\_multiset::iterator](../Topic/unordered_multiset::iterator.md)|Тип итератора для управляемой последовательности.|  
|[unordered\_multiset::key\_equal](../Topic/unordered_multiset::key_equal.md)|Тип функции сравнения.|  
|[unordered\_multiset::key\_type](../Topic/unordered_multiset::key_type.md)|Тип ключа упорядочения.|  
|[unordered\_multiset::local\_iterator](../Topic/unordered_multiset::local_iterator.md)|Тип итератора блока для управляемой последовательности.|  
|[unordered\_multiset::pointer](../Topic/unordered_multiset::pointer.md)|Тип указателя на элемент.|  
|[unordered\_multiset::reference](../Topic/unordered_multiset::reference.md)|Тип ссылки на элемент.|  
|[unordered\_multiset::size\_type](../Topic/unordered_multiset::size_type.md)|Тип беззнакового расстояния между двумя элементами.|  
|[unordered\_multiset::value\_type](../Topic/unordered_multiset::value_type.md)|Тип элемента.|  
  
|||  
|-|-|  
|Функция\-член|Описание|  
|[unordered\_multiset::begin](../Topic/unordered_multiset::begin.md)|Задает начало управляемой последовательности.|  
|[unordered\_multiset::bucket](../Topic/unordered_multiset::bucket.md)|Получает номер блока для значения ключа.|  
|[unordered\_multiset::bucket\_count](../Topic/unordered_multiset::bucket_count.md)|Получает количество блоков.|  
|[unordered\_multiset::bucket\_size](../Topic/unordered_multiset::bucket_size.md)|Получает размер блока.|  
|[unordered\_multiset::cbegin](../Topic/unordered_multiset::cbegin.md)|Задает начало управляемой последовательности.|  
|[unordered\_multiset::cend](../Topic/unordered_multiset::cend.md)|Задает конец управляемой последовательности.|  
|[unordered\_multiset::clear](../Topic/unordered_multiset::clear.md)|Удаляет все элементы.|  
|[unordered\_multiset::count](../Topic/unordered_multiset::count.md)|Определяет количество элементов, соответствующих заданному ключу.|  
|[unordered\_multiset::emplace](../Topic/unordered_multiset::emplace.md)|Добавляет элемент, созданный на месте.|  
|[unordered\_multiset::emplace\_hint](../Topic/unordered_multiset::emplace_hint.md)|Добавляет элемент, созданный на месте, с подсказкой.|  
|[unordered\_multiset::empty](../Topic/unordered_multiset::empty.md)|Проверяет отсутствие элементов.|  
|[unordered\_multiset::end](../Topic/unordered_multiset::end.md)|Задает конец управляемой последовательности.|  
|[unordered\_multiset::equal\_range](../Topic/unordered_multiset::equal_range.md)|Находит диапазон, соответствующий указанному ключу.|  
|[unordered\_multiset::erase](../Topic/unordered_multiset::erase.md)|Удаляет элементы в указанных позициях.|  
|[unordered\_multiset::find](../Topic/unordered_multiset::find.md)|Определяет элемент, соответствующий указанному ключу.|  
|[unordered\_multiset::get\_allocator](../Topic/unordered_multiset::get_allocator.md)|Возвращает сохраненный объект распределителя.|  
|[unordered\_multiset::hash\_function](../Topic/unordered_multiset::hash_function.md)|Получает сохраненный объект хэш\-функции.|  
|[unordered\_multiset::insert](../Topic/unordered_multiset::insert.md)|Добавляет элементы.|  
|[unordered\_multiset::key\_eq](../Topic/unordered_multiset::key_eq.md)|Получает сохраненный объект функции сравнения.|  
|[unordered\_multiset::load\_factor](../Topic/unordered_multiset::load_factor.md)|Подсчитывает среднее число элементов в блоке.|  
|[unordered\_multiset::max\_bucket\_count](../Topic/unordered_multiset::max_bucket_count.md)|Получает максимальное количество блоков.|  
|[unordered\_multiset::max\_load\_factor](../Topic/unordered_multiset::max_load_factor.md)|Возвращает или задает максимальное количество элементов в блоке.|  
|[unordered\_multiset::max\_size](../Topic/unordered_multiset::max_size.md)|Возвращает максимальный размер управляемой последовательности.|  
|[unordered\_multiset::rehash](../Topic/unordered_multiset::rehash.md)|Повторно создает хэш\-таблицу.|  
|[unordered\_multiset::size](../Topic/unordered_multiset::size.md)|Подсчитывает количество элементов.|  
|[unordered\_multiset::swap](../Topic/unordered_multiset::swap.md)|Меняет местами содержимое двух контейнеров.|  
|[unordered\_multiset::unordered\_multiset](../Topic/unordered_multiset::unordered_multiset.md)|Создает объект контейнера.|  
  
|||  
|-|-|  
|Оператор|Описание|  
|[unordered\_multiset::operator\=](../Topic/unordered_multiset::operator=.md)|Копирует хэш\-таблицу.|  
  
## Заметки  
 Объект упорядочивает управляемую им последовательность путем вызова двух сохраненных объектов, объекта функции сравнения типа [unordered\_multiset::key\_equal](../Topic/unordered_multiset::key_equal.md) и объекта хэш\-функции типа [unordered\_multiset::hasher](../Topic/unordered_multiset::hasher.md).  Доступ к первому сохраненному объекту можно получить, вызвав функцию\-член [unordered\_multiset::key\_eq](../Topic/unordered_multiset::key_eq.md)`()`; доступ ко второму сохраненному объекту выполняется путем вызова функции\-члена [unordered\_multiset::hash\_function](../Topic/unordered_multiset::hash_function.md)`()`.  В частности, для всех значений `X` и `Y` типа `Key` вызов `key_eq()(X, Y)` возвращает значение true, только если два значения аргументов имеют соответствующий порядок; вызов `hash_function()(keyval)` создает распределение значений типа `size_t`.  В отличие от шаблонного класса [Класс unordered\_set](../standard-library/unordered-set-class.md) объект шаблонного класса `unordered_multiset` не гарантирует, что `key_eq()(X, Y)` всегда имеет значение false для любых двух элементов управляемой последовательности. \(Ключи не обязательно должны быть уникальными.\)  
  
 Объект также хранит максимальный коэффициент нагрузки, который определяет максимальное желаемое среднее количество элементов в блоке.  Если вставка элемента вызывает превышение значением [unordered\_multiset::load\_factor](../Topic/unordered_multiset::load_factor.md)`()` максимального коэффициента нагрузки, контейнер увеличивает количество блоков и перестраивает хэш\-таблицу по мере необходимости.  
  
 Фактический порядок элементов в управляемой последовательности зависит от хэш\-функции, функции сравнения, порядка вставки, максимального коэффициента нагрузки и текущего числа блоков.  Обычно невозможно предсказать порядок элементов в управляемой последовательности.  Однако всегда можно сохранять уверенность, что любое подмножество элементов, имеющих соответствующий порядок, будет расположено по соседству в управляемой последовательности.  
  
 Объект выделяет и освобождает хранилище для управляемой им последовательности с помощью сохраненного объекта распределителя типа [unordered\_multiset::allocator\_type](../Topic/unordered_multiset::allocator_type.md).  Такой объект распределителя должен иметь такой же внешний интерфейс, как объект шаблонного класса `allocator`.  Обратите внимание, что сохраненный объект распределителя не копируется, когда назначается объект контейнера.  
  
## Требования  
 **Заголовок:** \<unordered\_set\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<unordered\_set\>](../standard-library/unordered-set.md)   
 [Контейнеры](../Topic/Containers%20\(Modern%20C++\).md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)