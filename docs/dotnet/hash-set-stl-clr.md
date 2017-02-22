---
title: "hash_set (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/hash_set> - заголовок [STL/CLR]"
  - "<hash_set> - заголовок [STL/CLR]"
  - "hash_set - класс [STL/CLR]"
ms.assetid: d110e356-ba3e-4e52-9e2d-d997bf975c96
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# hash_set (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание объекта класса шаблона, что элементы управления менять\- длины последовательность элементов являются двунаправленными, имеет доступ.  Используется контейнер `hash_set` для управления последовательность элементов в виде хэш\-таблицы, каждая запись таблицы расположении двунаправленного связанного списка узлов, каждый узел расположении один элемент.  Значение каждого элемента используется как ключ, для упорядочения последовательности.  
  
 В описании ниже, `GValue` совпадает с `GKey`, которые, в свою очередь совпадает с `Key` если здесь не будет ссылочного типа, в случае которого это `Key^`.  
  
## Синтаксис  
  
```  
template<typename Key>  
    ref class hash_set  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
    { ..... };  
```  
  
#### Параметры  
 Ключ  
 Тип ключа для элемента в управляемой последовательности.  
  
## Члены  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|[hash\_set::const\_iterator](../dotnet/hash-set-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[hash\_set::const\_reference](../dotnet/hash-set-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[hash\_set::const\_reverse\_iterator](../dotnet/hash-set-const-reverse-iterator-stl-clr.md)|Тип константы обратного итератора для контролируемой последовательности.|  
|[hash\_set::difference\_type](../dotnet/hash-set-difference-type-stl-clr.md)|Тип расстояния \(возможно, подписанного a 2\) между элементами.|  
|[hash\_set::generic\_container](../Topic/hash_set::generic_container%20\(STL-CLR\).md)|Тип универсального интерфейса для контейнера.|  
|[hash\_set::generic\_iterator](../Topic/hash_set::generic_iterator%20\(STL-CLR\).md)|Тип итератора для универсального интерфейса для контейнера.|  
|[hash\_set::generic\_reverse\_iterator](../Topic/hash_set::generic_reverse_iterator%20\(STL-CLR\).md)|Тип обратного итератора для универсального интерфейса для контейнера.|  
|[hash\_set::generic\_value](../dotnet/hash-set-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[hash\_set::hasher](../Topic/hash_set::hasher%20\(STL-CLR\).md)|Делегат хэширования для ключа.|  
|[hash\_set::iterator](../dotnet/hash-set-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[hash\_set::key\_compare](../Topic/hash_set::key_compare%20\(STL-CLR\).md)|Порядок делегат для 2 ключей.|  
|[hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md)|Тип ключа упорядочения.|  
|[hash\_set::reference](../dotnet/hash-set-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[hash\_set::reverse\_iterator](../dotnet/hash-set-reverse-iterator-stl-clr.md)|Тип обратного итератора для контролируемой последовательности.|  
|[hash\_set::size\_type](../dotnet/hash-set-size-type-stl-clr.md)|Тип расстояния a \(не отрицательного 2\) между элементами.|  
|[hash\_set::value\_compare](../dotnet/hash-set-value-compare-stl-clr.md)|Порядок делегат для 2 значений элементов.|  
|[hash\_set::value\_type](../dotnet/hash-set-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция Member|Описание|  
|--------------------|--------------|  
|[hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[hash\_set::bucket\_count](../dotnet/hash-set-bucket-count-stl-clr.md)|Подсчитывает число блоков.|  
|[hash\_set::clear](../dotnet/hash-set-clear-stl-clr.md)|Удаляет все элементы.|  
|[hash\_set::count](../dotnet/hash-set-count-stl-clr.md)|Подсчитывает число элементов, соответствующий указанному ключу.|  
|[hash\_set::empty](../dotnet/hash-set-empty-stl-clr.md)|Тесты отсутствуют ли какие\-либо элементы.|  
|[hash\_set::end](../dotnet/hash-set-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[hash\_set::equal\_range](../dotnet/hash-set-equal-range-stl-clr.md)|Находит диапазон, соответствующий указанному ключу.|  
|[hash\_set::erase](../dotnet/hash-set-erase-stl-clr.md)|Удаляет элементы в указанных положениях.|  
|[hash\_set::find](../Topic/hash_set::find%20\(STL-CLR\).md)|Определяет элемент, соответствующий указанному ключу.|  
|[hash\_set::hash\_delegate](../Topic/hash_set::hash_delegate%20\(STL-CLR\).md)|Копирует делегат хэширования для ключа.|  
|[hash\_set::hash\_set](../dotnet/hash-set-hash-set-stl-clr.md)|Создает объект контейнера.|  
|[hash\_set::insert](../dotnet/hash-set-insert-stl-clr.md)|Добавляет элементы.|  
|[hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md)|Копирует порядок делегат для 2 ключей.|  
|[hash\_set::load\_factor](../dotnet/hash-set-load-factor-stl-clr.md)|Подсчитывает число элементов " для каждого блока.|  
|[hash\_set::lower\_bound](../dotnet/hash-set-lower-bound-stl-clr.md)|Находит начало диапазона, соответствующий указанному ключу.|  
|[hash\_set::make\_value](../Topic/hash_set::make_value%20\(STL-CLR\).md)|Создает объект значение.|  
|[hash\_set::max\_load\_factor](../Topic/hash_set::max_load_factor%20\(STL-CLR\).md)|Возвращает или задает максимальное количество элементов для каждого блока.|  
|[hash\_set::rbegin](../dotnet/hash-set-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[hash\_set::rehash](../Topic/hash_set::rehash%20\(STL-CLR\).md)|Повторно создает хэш\-таблицу.|  
|[hash\_set::rend](../dotnet/hash-set-rend-stl-clr.md)|Задает конец обратной управляемой последовательности.|  
|[hash\_set::size](../dotnet/hash-set-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[hash\_set::swap](../dotnet/hash-set-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[hash\_set::to\_array](../dotnet/hash-set-to-array-stl-clr.md)|Копирует контролируемая последовательность в новый массив.|  
|[hash\_set::upper\_bound](../dotnet/hash-set-upper-bound-stl-clr.md)|Находит конечную точку диапазона, соответствующий указанному ключу.|  
|[hash\_set::value\_comp](../dotnet/hash-set-value-comp-stl-clr.md)|Копирует порядок делегат для 2 значений элементов.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|[hash\_set::operator\=](../dotnet/hash-set-operator-assign-stl-clr.md)|Заменяет контролируемая последовательность.|  
  
## Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|--------------|  
|<xref:System.ICloneable>|Дублируйте объект.|  
|<xref:System.Collections.IEnumerable>|Последовательность между элементами.|  
|<xref:System.Collections.ICollection>|Обеспечение группу в составе элементы.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Через последовательность типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Обеспечение группу в составе типизированных элементов.|  
|IHash\<Key, Value\>|Обслуживайте универсальный контейнер.|  
  
## Заметки  
 Объект выделяет и освобождает хранилище для последовательности его элементов управления в отдельные узлы в двунаправленном связанный список.  Для ускорения доступа он также поддерживает массив менять\- длины указателей в список \(хэш\-таблицу\), эффективно управляя список целиком в виде последовательности подсписков, или блоков.  Он не добавляет элементы в блок, он сохраняет упорядоченный, изменив ссылки между узлами, не скопировать содержимое одного узла на другой.  Это означает, что можно добавлять и удалять элементы свободно, не нарушая остальных элементов.  
  
 Объект является упорядоченным каждым из его элементов управления путем вызова делегата сохраненный объект типа [hash\_set::key\_compare](../Topic/hash_set::key_compare%20\(STL-CLR\).md).  Можно определить, сохраненный объект делегата при построении hash\_set; если не указан ни один объект делегата, по умолчанию используется сравнение `operator<=(key_type, key_type)`.  
  
 Чтобы открыть сохраненный объект делегата, вызвав функцию\-член [hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md)`()`.  Такой объект делегата должен определить соответствующий порядка между ключами типа [hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md).  Это означает, что для всех ключей, 2 `X` и `Y`:  
  
 `key_comp()(X, Y)` возвращает тот же логический результат при каждом вызове.  
  
 Если `key_comp()(X, Y) && key_comp()(Y, X)` выполняется, считается, что имеют `X` и `Y` соответствующий заказ.  
  
 Любое правило со заказов, ведет себя так же, как `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` или `operator==(key_type, key_type)` определяет eqivalent упорядочение.  
  
 Обратите внимание, что контейнер предоставляет только что элементы ключи которых имеют эквивалентные упорядочение \(и хэш, к тому же целочисленному значению\) смежны в блоке.  В отличие от класса шаблона [hash\_multiset](../dotnet/hash-multiset-stl-clr.md), объект класса шаблона `hash_set` гарантирует, что ключи для всех элементов уникальны. \(Отсутствует 2 ключей не имеют соответствующий заказ\).  
  
 Объект, который определяет блок должен содержать заданный порядок вызова ключ, сохраненный объект делегата типа [hash\_set::hasher](../Topic/hash_set::hasher%20\(STL-CLR\).md).  Чтобы открыть этот сохраненный объект, вызвав функцию\-член [hash\_set::hash\_delegate](../Topic/hash_set::hash_delegate%20\(STL-CLR\).md)`()` для получения целочисленное значение, которое зависит от значения ключа.  Можно определить, сохраненный объект делегата при построении hash\_set; если не указан ни один объект делегата, по умолчанию используется функция `System::Object::hash_value(key_type)`.  Это означает, что для всех ключей, `X` и `Y`:  
  
 `hash_delegate()(X)` возвращает тот же результат целые числа при каждом вызове.  
  
 Если `X` и `Y` имеет соответствующий порядок, `hash_delegate()(X)` должно возвращать один и тот же результат целого числа, как `hash_delegate()(Y)`.  
  
 Каждый элемент служит в качестве ключа, и как значение.  Последовательность представляется в виде, позволяющем поиск, вставки и удаления произвольного элемента с несколькими операций, не зависящий от числа элементов в последовательности \(постоянно время\) \-\- по крайней мере в лучше всего вариантов.  Кроме того, что вставка элемента нет итераторы, и удаление элементов только что эти итераторы, указывающих на удаленный элемент.  
  
 Если хэшированных значений не распределяются равномерно, то может выродиться хэш\-таблица.  В крайности \-\- для хэш\-функция, всегда возвращает то же значение \-\- поиск, вставки и удаления пропорциональны на число элементов в последовательности \(линейном времени\).  Контейнер стремится следует выбрать хэш\-функции, средний размер блока, и размер таблицы хэширования \(общее количество блоков\), но можно переопределить любой этих вариантов.  См., например, функции [hash\_set::max\_load\_factor](../Topic/hash_set::max_load_factor%20\(STL-CLR\).md) и [hash\_set::rehash](../Topic/hash_set::rehash%20\(STL-CLR\).md).  
  
 Hash\_set поддерживает двунаправленные итераторы\), что позволяет шаг с соседним элементам заданного итератор, обозначает элемент в контролируемой последовательности.  Специальный головной узел соответствует итератору возвращенным [hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`()`.  Можно декремент такой итератор для достижения последнего элемента в контролируемой последовательности, если в настоящий момент.  Можно увеличить итератор hash\_set для достижения головного узла, а затем сравнивает равно `end()`.  Однако нельзя разыменование итератор, `end()`.  
  
 Обратите внимание, что нельзя обращаться к элементу hash\_set непосредственно заданного свою позицию численную \-\- это требует произвольного доступа итератора.  
  
 Итератор hash\_set хранит дескриптор его связанный узел hash\_set, который, в свою очередь, сохраняет его связанный дескриптор контейнер.  Можно использовать итераторы только со связанными объектами контейнера.  Итератор hash\_set остается допустимым, пока его связанный узел hash\_set связан с определенным hash\_set.  Кроме того, допустимый итератор dereferencable \-\- его можно использовать для доступа или изменения значения элемента он обозначает \-\- пока не равно `end()`.  
  
 Стирающ или удаление элементов вызывает деструктор этого сохраненного значения.  Удалить контейнер удаляются все элементы.  Таким образом, тип которого контейнер элемента ссылочный класс гарантирует, что никаких элементов не переживают контейнер.  Однако стоит отметить, что контейнер дескрипторов делает `not` уничтожает его элементы.  
  
## Требования  
 **Заголовок:**\<cliext\/hash\_set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [набор](../dotnet/set-stl-clr.md)   
 [набор](../dotnet/set-stl-clr.md)   
 [набор](../dotnet/set-stl-clr.md)   
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)