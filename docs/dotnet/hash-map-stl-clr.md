---
title: "hash_map (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/hash_map> - заголовок [STL/CLR]"
  - "<hash_map> - заголовок [STL/CLR]"
  - "hash_map - класс [STL/CLR]"
ms.assetid: c3cfc69b-04c6-42ae-a30e-0eda953fe883
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# hash_map (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание объекта класса шаблона, что элементы управления менять\- длины последовательность элементов являются двунаправленными, имеет доступ.  Используется контейнер `hash_map` для управления последовательность элементов в виде хэш\-таблицы, каждая запись таблицы расположении двунаправленного связанного списка узлов, каждый узел расположении один элемент.  Элемент состоит из ключа, для упорядочения последовательности и сопоставленного значение, которая осуществляет поиск для езды.  
  
 В описании ниже, `GValue` аналогично:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 Здесь:  
  
 `GKey` совпадает с `Key` если здесь не будет ссылочного типа, в случае которого это `Key^`  
  
 `GMapped` совпадает с `Mapped` если здесь не будет ссылочного типа, в случае которого это `Mapped^`  
  
## Синтаксис  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class hash_map  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        System::Collections::Generic::IDictionary<Gkey, GMapped>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
    { ..... };  
```  
  
#### Параметры  
 Ключ  
 Тип ключа для элемента в управляемой последовательности.  
  
 Сопоставленного  
 Тип дополнительного компонента элемента в контролируемой последовательности.  
  
## Члены  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|[hash\_map::const\_iterator](../dotnet/hash-map-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[hash\_map::const\_reference](../dotnet/hash-map-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[hash\_map::const\_reverse\_iterator](../dotnet/hash-map-const-reverse-iterator-stl-clr.md)|Тип константы обратного итератора для контролируемой последовательности.|  
|[hash\_map::difference\_type](../dotnet/hash-map-difference-type-stl-clr.md)|Тип расстояния \(возможно, подписанного a 2\) между элементами.|  
|[hash\_map::generic\_container](../dotnet/hash-map-generic-container-stl-clr.md)|Тип универсального интерфейса для контейнера.|  
|[hash\_map::generic\_iterator](../dotnet/hash-map-generic-iterator-stl-clr.md)|Тип итератора для универсального интерфейса для контейнера.|  
|[hash\_map::generic\_reverse\_iterator](../dotnet/hash-map-generic-reverse-iterator-stl-clr.md)|Тип обратного итератора для универсального интерфейса для контейнера.|  
|[hash\_map::generic\_value](../dotnet/hash-map-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[hash\_map::hasher](../dotnet/hash-map-hasher-stl-clr.md)|Делегат хэширования для ключа.|  
|[hash\_map::iterator](../dotnet/hash-map-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[hash\_map::key\_compare](../Topic/hash_map::key_compare%20\(STL-CLR\).md)|Порядок делегат для 2 ключей.|  
|[hash\_map::key\_type](../Topic/hash_map::key_type%20\(STL-CLR\).md)|Тип ключа упорядочения.|  
|[hash\_map::mapped\_type](../Topic/hash_map::mapped_type%20\(STL-CLR\).md)|Тип сопоставленного значение, связанной с каждым ключом.|  
|[hash\_map::reference](../dotnet/hash-map-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[hash\_map::reverse\_iterator](../dotnet/hash-map-reverse-iterator-stl-clr.md)|Тип обратного итератора для контролируемой последовательности.|  
|[hash\_map::size\_type](../Topic/hash_map::size_type%20\(STL-CLR\).md)|Тип расстояния a \(не отрицательного 2\) между элементами.|  
|[hash\_map::value\_compare](../dotnet/hash-map-value-compare-stl-clr.md)|Порядок делегат для 2 значений элементов.|  
|[hash\_map::value\_type](../dotnet/hash-map-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция Member|Описание|  
|--------------------|--------------|  
|[hash\_map::begin](../dotnet/hash-map-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[hash\_map::bucket\_count](../dotnet/hash-map-bucket-count-stl-clr.md)|Подсчитывает число блоков.|  
|[hash\_map::clear](../Topic/hash_map::clear%20\(STL-CLR\).md)|Удаляет все элементы.|  
|[hash\_map::count](../dotnet/hash-map-count-stl-clr.md)|Подсчитывает число элементов, соответствующий указанному ключу.|  
|[hash\_map::empty](../dotnet/hash-map-empty-stl-clr.md)|Тесты отсутствуют ли какие\-либо элементы.|  
|[hash\_map::end](../dotnet/hash-map-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[hash\_map::equal\_range](../dotnet/hash-map-equal-range-stl-clr.md)|Находит диапазон, соответствующий указанному ключу.|  
|[hash\_map::erase](../dotnet/hash-map-erase-stl-clr.md)|Удаляет элементы в указанных положениях.|  
|[hash\_map::find](../dotnet/hash-map-find-stl-clr.md)|Определяет элемент, соответствующий указанному ключу.|  
|[hash\_map::hash\_delegate](../dotnet/hash-map-hash-delegate-stl-clr.md)|Копирует делегат хэширования для ключа.|  
|[hash\_map::hash\_map](../dotnet/hash-map-hash-map-stl-clr.md)|Создает объект контейнера.|  
|[hash\_map::insert](../Topic/hash_map::insert%20\(STL-CLR\).md)|Добавляет элементы.|  
|[hash\_map::key\_comp](../dotnet/hash-map-key-comp-stl-clr.md)|Копирует порядок делегат для 2 ключей.|  
|[hash\_map::load\_factor](../dotnet/hash-map-load-factor-stl-clr.md)|Подсчитывает число элементов " для каждого блока.|  
|[hash\_map::lower\_bound](../dotnet/hash-map-lower-bound-stl-clr.md)|Находит начало диапазона, соответствующий указанному ключу.|  
|[hash\_map::make\_value](../dotnet/hash-map-make-value-stl-clr.md)|Создает объект значение.|  
|[hash\_map::max\_load\_factor](../dotnet/hash-map-max-load-factor-stl-clr.md)|Возвращает или задает максимальное количество элементов для каждого блока.|  
|[hash\_map::rbegin](../dotnet/hash-map-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[hash\_map::rehash](../dotnet/hash-map-rehash-stl-clr.md)|Повторно создает хэш\-таблицу.|  
|[hash\_map::rend](../Topic/hash_map::rend%20\(STL-CLR\).md)|Задает конец обратной управляемой последовательности.|  
|[hash\_map::size](../dotnet/hash-map-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[hash\_map::swap](../dotnet/hash-map-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[hash\_map::to\_array](../dotnet/hash-map-to-array-stl-clr.md)|Копирует контролируемая последовательность в новый массив.|  
|[hash\_map::upper\_bound](../dotnet/hash-map-upper-bound-stl-clr.md)|Находит конечную точку диапазона, соответствующий указанному ключу.|  
|[hash\_map::value\_comp](../dotnet/hash-map-value-comp-stl-clr.md)|Копирует порядок делегат для 2 значений элементов.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|[hash\_map::operator\=](../dotnet/hash-map-operator-assign-stl-clr.md)|Заменяет контролируемая последовательность.|  
|[hash\_map::operator](../dotnet/hash-map-operator-stl-clr.md)|Сопоставляет ключ, связанный с его сопоставлянному значение.|  
  
## Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|--------------|  
|<xref:System.ICloneable>|Дублируйте объект.|  
|<xref:System.Collections.IEnumerable>|Последовательность между элементами.|  
|<xref:System.Collections.ICollection>|Обеспечение группу в составе элементы.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Через последовательность типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Обеспечение группу в составе типизированных элементов.|  
|<xref:System.Collections.Generic.IDictionary%602>|Обеспечение группу в составе {ключ, значение пары.}|  
|IHash\<Key, Value\>|Обслуживайте универсальный контейнер.|  
  
## Заметки  
 Объект выделяет и освобождает хранилище для последовательности его элементов управления в отдельные узлы в двунаправленном связанный список.  Для ускорения доступа он также поддерживает массив менять\- длины указателей в список \(хэш\-таблицу\), эффективно управляя список целиком в виде последовательности подсписков, или блоков.  Он не добавляет элементы в блок, он сохраняет упорядоченный, изменив ссылки между узлами, не скопировать содержимое одного узла на другой.  Это означает, что можно добавлять и удалять элементы свободно, не нарушая остальных элементов.  
  
 Объект является упорядоченным каждым из его элементов управления путем вызова делегата сохраненный объект типа [hash\_set::key\_compare](../Topic/hash_set::key_compare%20\(STL-CLR\).md).  Можно определить, сохраненный объект делегата при построении hash\_set; если не указан ни один объект делегата, по умолчанию используется сравнение `operator<=(key_type, key_type)`.  
  
 Чтобы открыть сохраненный объект делегата, вызвав функцию\-член [hash\_set::key\_comp](../dotnet/hash-set-key-comp-stl-clr.md)`()`.  Такой объект делегата должен определить соответствующий порядка между ключами типа [hash\_set::key\_type](../dotnet/hash-set-key-type-stl-clr.md).  Это означает, что для всех ключей, 2 `X` и `Y`:  
  
 `key_comp()(X, Y)` возвращает тот же логический результат при каждом вызове.  
  
 Если `key_comp()(X, Y) && key_comp()(Y, X)` выполняется, считается, что имеют `X` и `Y` соответствующий заказ.  
  
 Любое правило со заказов, ведет себя так же, как `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` или `operator==(key_type, key_type)` определяет eqivalent упорядочение.  
  
 Обратите внимание, что контейнер предоставляет только что элементы ключи которых имеют эквивалентные упорядочение \(и хэш, к тому же целочисленному значению\) смежны в блоке.  В отличие от класса шаблона [hash\_multimap](../dotnet/hash-multimap-stl-clr.md), объект класса шаблона `hash_map` гарантирует, что ключи для всех элементов уникальны. \(Отсутствует 2 ключей не имеют соответствующий заказ\).  
  
 Объект, который определяет блок должен содержать заданный порядок вызова ключ, сохраненный объект делегата типа [hash\_set::hasher](../Topic/hash_set::hasher%20\(STL-CLR\).md).  Чтобы открыть этот сохраненный объект, вызвав функцию\-член [hash\_set::hash\_delegate](../Topic/hash_set::hash_delegate%20\(STL-CLR\).md)`()` для получения целочисленное значение, которое зависит от значения ключа.  Можно определить, сохраненный объект делегата при построении hash\_set; если не указан ни один объект делегата, по умолчанию используется функция `System::Object::hash_value(key_type)`.  Это означает, что для всех ключей, `X` и `Y`:  
  
 `hash_delegate()(X)` возвращает тот же результат целые числа при каждом вызове.  
  
 Если `X` и `Y` имеет соответствующий порядок, `hash_delegate()(X)` должно возвращать один и тот же результат целого числа, как `hash_delegate()(Y)`.  
  
 Каждый элемент содержит отдельный ключ и сопоставляются значению.  Последовательность представляется в виде, позволяющем поиск, вставки и удаления произвольного элемента с несколькими операций, не зависящий от числа элементов в последовательности \(постоянно время\) \-\- по крайней мере в лучше всего вариантов.  Кроме того, что вставка элемента нет итераторы, и удаление элементов только что эти итераторы, указывающих на удаленный элемент.  
  
 Если хэшированных значений не распределяются равномерно, то может выродиться хэш\-таблица.  В крайности \-\- для хэш\-функция, всегда возвращает то же значение \-\- поиск, вставки и удаления пропорциональны на число элементов в последовательности \(линейном времени\).  Контейнер стремится следует выбрать хэш\-функции, средний размер блока, и размер таблицы хэширования \(общее количество блоков\), но можно переопределить любой этих вариантов.  См., например, функции [hash\_set::max\_load\_factor](../Topic/hash_set::max_load_factor%20\(STL-CLR\).md) и [hash\_set::rehash](../Topic/hash_set::rehash%20\(STL-CLR\).md).  
  
 Hash\_map поддерживает двунаправленные итераторы\), что позволяет шаг с соседним элементам заданного итератор, обозначает элемент в контролируемой последовательности.  Специальный головной узел соответствует итератору возвращенным [hash\_map::end](../dotnet/hash-map-end-stl-clr.md)`()`.  Можно декремент такой итератор для достижения последнего элемента в контролируемой последовательности, если в настоящий момент.  Можно увеличить итератор hash\_map для достижения головного узла, а затем сравнивает равно `end()`.  Однако нельзя разыменование итератор, `end()`.  
  
 Обратите внимание, что нельзя обращаться к элементу hash\_map непосредственно заданного свою позицию численную \-\- это требует произвольного доступа итератора.  
  
 Итератор hash\_map хранит дескриптор его связанный узел hash\_map, который, в свою очередь, сохраняет его связанный дескриптор контейнер.  Можно использовать итераторы только со связанными объектами контейнера.  Итератор hash\_map остается допустимым, пока его связанный узел hash\_map связан с определенным hash\_map.  Кроме того, допустимый итератор dereferencable \-\- его можно использовать для доступа или изменения значения элемента он обозначает \-\- пока не равно `end()`.  
  
 Стирающ или удаление элементов вызывает деструктор этого сохраненного значения.  Удалить контейнер удаляются все элементы.  Таким образом, тип которого контейнер элемента ссылочный класс гарантирует, что никаких элементов не переживают контейнер.  Однако стоит отметить, что контейнер дескрипторов делает `not` уничтожает его элементы.  
  
## Требования  
 **Заголовок:**\<cliext\/hash\_map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [набор](../dotnet/set-stl-clr.md)   
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)