---
title: "hash_multimap (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/hash_map> - заголовок [STL/CLR]"
  - "<hash_map> - заголовок [STL/CLR]"
  - "hash_multimap - класс [STL/CLR]"
ms.assetid: cd78687b-8a05-48e0-9d22-8b8194ae3b0b
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multimap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание объекта класса шаблона, что элементы управления менять\- длины последовательность элементов являются двунаправленными, имеет доступ.  Используется контейнер `hash_multimap` для управления последовательность элементов в виде хэш\-таблицы, каждая запись таблицы расположении двунаправленного связанного списка узлов, каждый узел расположении один элемент.  Элемент состоит из ключа, для упорядочения последовательности и сопоставленного значение, которая осуществляет поиск для езды.  
  
 В описании ниже, `GValue` аналогично:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 Здесь:  
  
 `GKey` совпадает с `Key` если здесь не будет ссылочного типа, в случае которого это `Key^`  
  
 `GMapped` совпадает с `Mapped` если здесь не будет ссылочного типа, в случае которого это `Mapped^`  
  
## Синтаксис  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class hash_multimap  
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
  
 Сопоставленного  
 Тип дополнительного компонента элемента в контролируемой последовательности.  
  
## Члены  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|[hash\_multimap::const\_iterator](../dotnet/hash-multimap-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[hash\_multimap::const\_reference](../dotnet/hash-multimap-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[hash\_multimap::const\_reverse\_iterator](../Topic/hash_multimap::const_reverse_iterator%20\(STL-CLR\).md)|Тип константы обратного итератора для контролируемой последовательности.|  
|[hash\_multimap::difference\_type](../dotnet/hash-multimap-difference-type-stl-clr.md)|Тип расстояния \(возможно, подписанного a 2\) между элементами.|  
|[hash\_multimap::generic\_container](../dotnet/hash-multimap-generic-container-stl-clr.md)|Тип универсального интерфейса для контейнера.|  
|[hash\_multimap::generic\_iterator](../dotnet/hash-multimap-generic-iterator-stl-clr.md)|Тип итератора для универсального интерфейса для контейнера.|  
|[hash\_multimap::generic\_reverse\_iterator](../dotnet/hash-multimap-generic-reverse-iterator-stl-clr.md)|Тип обратного итератора для универсального интерфейса для контейнера.|  
|[hash\_multimap::generic\_value](../dotnet/hash-multimap-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[hash\_multimap::hasher](../dotnet/hash-multimap-hasher-stl-clr.md)|Делегат хэширования для ключа.|  
|[hash\_multimap::iterator](../dotnet/hash-multimap-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[hash\_multimap::key\_compare](../dotnet/hash-multimap-key-compare-stl-clr.md)|Порядок делегат для 2 ключей.|  
|[hash\_multimap::key\_type](../dotnet/hash-multimap-key-type-stl-clr.md)|Тип ключа упорядочения.|  
|[hash\_multimap::mapped\_type](../Topic/hash_multimap::mapped_type%20\(STL-CLR\).md)|Тип сопоставленного значение, связанной с каждым ключом.|  
|[hash\_multimap::reference](../dotnet/hash-multimap-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[hash\_multimap::reverse\_iterator](../dotnet/hash-multimap-reverse-iterator-stl-clr.md)|Тип обратного итератора для контролируемой последовательности.|  
|[hash\_multimap::size\_type](../dotnet/hash-multimap-size-type-stl-clr.md)|Тип расстояния a \(не отрицательного 2\) между элементами.|  
|[hash\_multimap::value\_compare](../dotnet/hash-multimap-value-compare-stl-clr.md)|Порядок делегат для 2 значений элементов.|  
|[hash\_multimap::value\_type](../dotnet/hash-multimap-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция Member|Описание|  
|--------------------|--------------|  
|[hash\_multimap::begin](../dotnet/hash-multimap-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[hash\_multimap::bucket\_count](../dotnet/hash-multimap-bucket-count-stl-clr.md)|Подсчитывает число блоков.|  
|[hash\_multimap::clear](../dotnet/hash-multimap-clear-stl-clr.md)|Удаляет все элементы.|  
|[hash\_multimap::count](../dotnet/hash-multimap-count-stl-clr.md)|Подсчитывает число элементов, соответствующий указанному ключу.|  
|[hash\_multimap::empty](../dotnet/hash-multimap-empty-stl-clr.md)|Тесты отсутствуют ли какие\-либо элементы.|  
|[hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[hash\_multimap::equal\_range](../dotnet/hash-multimap-equal-range-stl-clr.md)|Находит диапазон, соответствующий указанному ключу.|  
|[hash\_multimap::erase](../dotnet/hash-multimap-erase-stl-clr.md)|Удаляет элементы в указанных положениях.|  
|[hash\_multimap::find](../dotnet/hash-multimap-find-stl-clr.md)|Определяет элемент, соответствующий указанному ключу.|  
|[hash\_multimap::hash\_delegate](../dotnet/hash-multimap-hash-delegate-stl-clr.md)|Копирует делегат хэширования для ключа.|  
|[hash\_multimap::hash\_multimap](../dotnet/hash-multimap-hash-multimap-stl-clr.md)|Создает объект контейнера.|  
|[hash\_multimap::insert](../dotnet/hash-multimap-insert-stl-clr.md)|Добавляет элементы.|  
|[hash\_multimap::key\_comp](../dotnet/hash-multimap-key-comp-stl-clr.md)|Копирует порядок делегат для 2 ключей.|  
|[hash\_multimap::load\_factor](../dotnet/hash-multimap-load-factor-stl-clr.md)|Подсчитывает число элементов " для каждого блока.|  
|[hash\_multimap::lower\_bound](../Topic/hash_multimap::lower_bound%20\(STL-CLR\).md)|Находит начало диапазона, соответствующий указанному ключу.|  
|[hash\_multimap::make\_value](../dotnet/hash-multimap-make-value-stl-clr.md)|Создает объект значение.|  
|[hash\_multimap::max\_load\_factor](../Topic/hash_multimap::max_load_factor%20\(STL-CLR\).md)|Возвращает или задает максимальное количество элементов для каждого блока.|  
|[hash\_multimap::rbegin](../dotnet/hash-multimap-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[hash\_multimap::rehash](../dotnet/hash-multimap-rehash-stl-clr.md)|Повторно создает хэш\-таблицу.|  
|[hash\_multimap::rend](../dotnet/hash-multimap-rend-stl-clr.md)|Задает конец обратной управляемой последовательности.|  
|[hash\_multimap::size](../dotnet/hash-multimap-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[hash\_multimap::swap](../dotnet/hash-multimap-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[hash\_multimap::to\_array](../dotnet/hash-multimap-to-array-stl-clr.md)|Копирует контролируемая последовательность в новый массив.|  
|[hash\_multimap::upper\_bound](../Topic/hash_multimap::upper_bound%20\(STL-CLR\).md)|Находит конечную точку диапазона, соответствующий указанному ключу.|  
|[hash\_multimap::value\_comp](../dotnet/hash-multimap-value-comp-stl-clr.md)|Копирует порядок делегат для 2 значений элементов.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|[hash\_multimap::operator\=](../dotnet/hash-multimap-operator-assign-stl-clr.md)|Заменяет контролируемая последовательность.|  
  
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
  
 Обратите внимание, что контейнер предоставляет только что элементы ключи которых имеют эквивалентные упорядочение \(и хэш, к тому же целочисленному значению\) смежны в блоке.  В отличие от класса шаблона [hash\_map](../dotnet/hash-map-stl-clr.md), объект класса шаблона `hash_multimap` не требует ключи для всех элементов уникальны. \(Два или более ключи могут иметь соответствующий заказ\).  
  
 Объект, который определяет блок должен содержать заданный порядок вызова ключ, сохраненный объект делегата типа [hash\_set::hasher](../Topic/hash_set::hasher%20\(STL-CLR\).md).  Чтобы открыть этот сохраненный объект, вызвав функцию\-член [hash\_set::hash\_delegate](../Topic/hash_set::hash_delegate%20\(STL-CLR\).md)`()` для получения целочисленное значение, которое зависит от значения ключа.  Можно определить, сохраненный объект делегата при построении hash\_set; если не указан ни один объект делегата, по умолчанию используется функция `System::Object::hash_value(key_type)`.  Это означает, что для всех ключей, `X` и `Y`:  
  
 `hash_delegate()(X)` возвращает тот же результат целые числа при каждом вызове.  
  
 Если `X` и `Y` имеет соответствующий порядок, `hash_delegate()(X)` должно возвращать один и тот же результат целого числа, как `hash_delegate()(Y)`.  
  
 Каждый элемент содержит отдельный ключ и сопоставляются значению.  Последовательность представляется в виде, позволяющем поиск, вставки и удаления произвольного элемента с несколькими операций, не зависящий от числа элементов в последовательности \(постоянно время\) \-\- по крайней мере в лучше всего вариантов.  Кроме того, что вставка элемента нет итераторы, и удаление элементов только что эти итераторы, указывающих на удаленный элемент.  
  
 Если хэшированных значений не распределяются равномерно, то может выродиться хэш\-таблица.  В крайности \-\- для хэш\-функция, всегда возвращает то же значение \-\- поиск, вставки и удаления пропорциональны на число элементов в последовательности \(линейном времени\).  Контейнер стремится следует выбрать хэш\-функции, средний размер блока, и размер таблицы хэширования \(общее количество блоков\), но можно переопределить любой этих вариантов.  См., например, функции [hash\_set::max\_load\_factor](../Topic/hash_set::max_load_factor%20\(STL-CLR\).md) и [hash\_set::rehash](../Topic/hash_set::rehash%20\(STL-CLR\).md).  
  
 Hash\_multimap поддерживает двунаправленные итераторы\), что позволяет шаг с соседним элементам заданного итератор, обозначает элемент в контролируемой последовательности.  Специальный головной узел соответствует итератору возвращенным [hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)`()`.  Можно декремент такой итератор для достижения последнего элемента в контролируемой последовательности, если в настоящий момент.  Можно увеличить итератор hash\_multimap для достижения головного узла, а затем сравнивает равно `end()`.  Однако нельзя разыменование итератор, `end()`.  
  
 Обратите внимание, что нельзя обращаться к элементу hash\_multimap непосредственно заданного свою позицию численную \-\- это требует произвольного доступа итератора.  
  
 Итератор hash\_multimap хранит дескриптор его связанный узел hash\_multimap, который, в свою очередь, сохраняет его связанный дескриптор контейнер.  Можно использовать итераторы только со связанными объектами контейнера.  Итератор hash\_multimap остается допустимым, пока его связанный узел hash\_multimap связан с определенным hash\_multimap.  Кроме того, допустимый итератор dereferencable \-\- его можно использовать для доступа или изменения значения элемента он обозначает \-\- пока не равно `end()`.  
  
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