---
title: "multiset (STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/set> заголовок [STL/CLR]"
  - "<set> - заголовок [STL/CLR]"
  - "multiset - класс [STL/CLR]"
ms.assetid: 7c46e2b4-cd88-49b7-a9e6-63ad5ae7feb5
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiset (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание объекта класса шаблона, что элементы управления менять\- длины последовательность элементов являются двунаправленными, имеет доступ.  Используется контейнер `multiset` для управления последовательность элементов как a \(почти\) сбалансировало упорядоченное дерево узлов, каждый расположении один элемент.  
  
 В описании ниже, `GValue` совпадает с `GKey`, которые, в свою очередь совпадает с `Key` если здесь не будет ссылочного типа, в случае которого это `Key^`.  
  
## Синтаксис  
  
```  
template<typename Key>  
    ref class multiset  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
    { ..... };  
```  
  
#### Параметры  
 Ключ  
 Тип ключа для элемента в управляемой последовательности.  
  
## Члены  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|[multiset::const\_iterator](../dotnet/multiset-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[multiset::const\_reference](../dotnet/multiset-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[multiset::const\_reverse\_iterator](../dotnet/multiset-const-reverse-iterator-stl-clr.md)|Тип константы обратного итератора для контролируемой последовательности.|  
|[multiset::difference\_type](../dotnet/multiset-difference-type-stl-clr.md)|Тип расстояния \(возможно, подписанного a 2\) между элементами.|  
|[multiset::generic\_container](../dotnet/multiset-generic-container-stl-clr.md)|Тип универсального интерфейса для контейнера.|  
|[multiset::generic\_iterator](../Topic/multiset::generic_iterator%20\(STL-CLR\).md)|Тип итератора для универсального интерфейса для контейнера.|  
|[multiset::generic\_reverse\_iterator](../Topic/multiset::generic_reverse_iterator%20\(STL-CLR\).md)|Тип обратного итератора для универсального интерфейса для контейнера.|  
|[multiset::generic\_value](../dotnet/multiset-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[multiset::iterator](../dotnet/multiset-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[multiset::key\_compare](../dotnet/multiset-key-compare-stl-clr.md)|Порядок делегат для 2 ключей.|  
|[multiset::key\_type](../dotnet/multiset-key-type-stl-clr.md)|Тип ключа упорядочения.|  
|[multiset::reference](../dotnet/multiset-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[multiset::reverse\_iterator](../dotnet/multiset-reverse-iterator-stl-clr.md)|Тип обратного итератора для контролируемой последовательности.|  
|[multiset::size\_type](../dotnet/multiset-size-type-stl-clr.md)|Тип расстояния a \(не отрицательного 2\) между элементами.|  
|[multiset::value\_compare](../Topic/multiset::value_compare%20\(STL-CLR\).md)|Порядок делегат для 2 значений элементов.|  
|[multiset::value\_type](../dotnet/multiset-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция Member|Описание|  
|--------------------|--------------|  
|[multiset::begin](../dotnet/multiset-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[multiset::clear](../dotnet/multiset-clear-stl-clr.md)|Удаляет все элементы.|  
|[multiset::count](../dotnet/multiset-count-stl-clr.md)|Подсчитывает число элементов, соответствующий указанному ключу.|  
|[multiset::empty](../dotnet/multiset-empty-stl-clr.md)|Тесты отсутствуют ли какие\-либо элементы.|  
|[multiset::end](../dotnet/multiset-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[multiset::equal\_range](../dotnet/multiset-equal-range-stl-clr.md)|Находит диапазон, соответствующий указанному ключу.|  
|[multiset::erase](../dotnet/multiset-erase-stl-clr.md)|Удаляет элементы в указанных положениях.|  
|[multiset::find](../Topic/multiset::find%20\(STL-CLR\).md)|Определяет элемент, соответствующий указанному ключу.|  
|[multiset::insert](../Topic/multiset::insert%20\(STL-CLR\).md)|Добавляет элементы.|  
|[multiset::key\_comp](../Topic/multiset::key_comp%20\(STL-CLR\).md)|Копирует порядок делегат для 2 ключей.|  
|[multiset::lower\_bound](../Topic/multiset::lower_bound%20\(STL-CLR\).md)|Находит начало диапазона, соответствующий указанному ключу.|  
|[multiset::make\_value](../Topic/multiset::make_value%20\(STL-CLR\).md)|Создает объект значение.|  
|[multiset::multiset](../dotnet/multiset-multiset-stl-clr.md)|Создает объект контейнера.|  
|[multiset::rbegin](../dotnet/multiset-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[multiset::rend](../Topic/multiset::rend%20\(STL-CLR\).md)|Задает конец обратной управляемой последовательности.|  
|[multiset::size](../dotnet/multiset-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[multiset::swap](../dotnet/multiset-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[multiset::to\_array](../dotnet/multiset-to-array-stl-clr.md)|Копирует контролируемая последовательность в новый массив.|  
|[multiset::upper\_bound](../dotnet/multiset-upper-bound-stl-clr.md)|Находит конечную точку диапазона, соответствующий указанному ключу.|  
|[multiset::value\_comp](../dotnet/multiset-value-comp-stl-clr.md)|Копирует порядок делегат для 2 значений элементов.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|[multiset::operator\=](../dotnet/multiset-operator-assign-stl-clr.md)|Заменяет контролируемая последовательность.|  
|[operator\!\= \(multiset\)](../dotnet/operator-inequality-multiset-stl-clr.md)|Определяет, является ли объект `multiset` не равен другому объекту `multiset`.|  
|[operator\< \(multiset\)](../dotnet/operator-less-than-multiset-stl-clr.md)|Определяет, является ли объект `multiset` меньше другой объект `multiset`.|  
|[operator\<\= \(multiset\)](../Topic/operator%3C=%20\(multiset\)%20\(STL-CLR\).md)|Определяет, является ли объект `multiset` меньше или равно другому объекту `multiset`.|  
|[operator\=\= \(multiset\)](../Topic/operator==%20\(multiset\)%20\(STL-CLR\).md)|Определяет, является ли объект `multiset` равен другому объекту `multiset`.|  
|[operator\> \(multiset\)](../dotnet/operator-greater-than-multiset-stl-clr.md)|Определяет, является ли объект `multiset` больше другого объекта `multiset`.|  
|[operator\>\= \(multiset\)](../Topic/operator%3E=%20\(multiset\)%20\(STL-CLR\).md)|Определяет, является ли объект `multiset` больше или равно другому объекту `multiset`.|  
  
## Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|--------------|  
|<xref:System.ICloneable>|Дублируйте объект.|  
|<xref:System.Collections.IEnumerable>|Последовательность между элементами.|  
|<xref:System.Collections.ICollection>|Обеспечение группу в составе элементы.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Через последовательность типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Обеспечение группу в составе типизированных элементов.|  
|ITree\<Key, Value\>|Обслуживайте универсальный контейнер.|  
  
## Заметки  
 Объект выделяет и освобождает хранилище для последовательности его элементов управления в отдельные узлы.  Он добавляет элементы в a \(почти\) не балансировал дерево, это не позволяет упорядоченный, изменив ссылки между узлами, не скопировать содержимое одного узла на другой.  Это означает, что можно добавлять и удалять элементы свободно, не нарушая остальных элементов.  
  
 Объект сортирует последовательность его элементы управления путем вызова делегата сохраненный объект типа [multiset::key\_compare](../dotnet/multiset-key-compare-stl-clr.md).  Можно определить, сохраненный объект делегата при построении multiset. если не указан ни один объект делегата, по умолчанию используется сравнение `operator<(key_type, key_type)`.  Чтобы открыть этот сохраненный объект, вызвав функцию\-член [multiset::key\_comp](../Topic/multiset::key_comp%20\(STL-CLR\).md)`()`.  
  
 Такой объект делегата должен создать строгого слабое упорядочение на ключах типа [multiset::key\_type](../dotnet/multiset-key-type-stl-clr.md).  Это означает, что для всех ключей, 2 `X` и `Y`:  
  
 `key_comp()(X, Y)` возвращает тот же логический результат при каждом вызове.  
  
 Если `key_comp()(X, Y)` выполняется, `key_comp()(Y, X)` должно быть значение.  
  
 Если `key_comp()(X, Y)` выполняется, считается, что приказано `X` перед `Y`.  
  
 Если `!key_comp()(X, Y) && !key_comp()(Y, X)` выполняется, считается, что имеют `X` и `Y` соответствующий заказ.  
  
 Для любого элемента `X`, предшествующего `Y` в контролируемой последовательности, `key_comp()(Y, X)` ложно. \(Для объекта делегата, по умолчанию ключи никогда не уменьшает значение\). В отличие от класса шаблона [набор](../dotnet/set-stl-clr.md), объект класса шаблона `multiset` не требует ключи для всех элементов уникальны. \(Два или более ключи могут иметь соответствующий заказ\).  
  
 Каждый элемент служит в качестве ey, и как значение.  Последовательность представляется в виде, позволяющем поиск, вставки и удаления произвольного элемента с несколькими операций пропорциональных в логарифму числа элементов в последовательности \(логарифмическом времени\).  Кроме того, что вставка элемента нет итераторы, и удаление элементов только что эти итераторы, указывающих на удаленный элемент.  
  
 Multiset поддерживает двунаправленные итераторы. это означает, что можно выполнить с соседним элементам заданного итератор, обозначает элемент в контролируемой последовательности.  Специальный головной узел соответствует итератору возвращенным [multiset::end](../dotnet/multiset-end-stl-clr.md)`()`.  Можно декремент такой итератор для достижения последнего элемента в контролируемой последовательности, если в настоящий момент.  Можно увеличить итератор multiset для достижения головного узла, а затем сравнивает равно `end()`.  Однако нельзя разыменование итератор, `end()`.  
  
 Обратите внимание, что нельзя обращаться к элементу multiset непосредственно заданного свою позицию численную \-\- это требует произвольного доступа итератора.  
  
 Итератор multiset хранит дескриптор его связанный узел multiset, который, в свою очередь, сохраняет его связанный дескриптор контейнер.  Можно использовать итераторы только со связанными объектами контейнера.  Итератор multiset остается допустимым, пока его связанный узел multiset связан с некоторым multiset.  Кроме того, допустимый итератор dereferencable \-\- его можно использовать для доступа или изменения значения элемента он обозначает \-\- пока не равно `end()`.  
  
 Стирающ или удаление элементов вызывает деструктор этого сохраненного значения.  Удалить контейнер удаляются все элементы.  Таким образом, тип которого контейнер элемента ссылочный класс гарантирует, что никаких элементов не переживают контейнер.  Однако стоит отметить, что контейнер дескрипторов делает `not` уничтожает его элементы.  
  
## Требования  
 **Заголовок:**\<cliext\/set\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [набор](../dotnet/set-stl-clr.md)   
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)