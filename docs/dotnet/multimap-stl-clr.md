---
title: "multimap (STL/CLR) | Microsoft Docs"
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
  - "cliext::multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/map> - заголовок [STL/CLR]"
  - "<map> - заголовок [STL/CLR]"
  - "multimap - класс [STL/CLR]"
ms.assetid: 3dfe329d-a078-462a-b050-7999ce6110ad
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multimap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание объекта класса шаблона, что элементы управления менять\- длины последовательность элементов являются двунаправленными, имеет доступ.  Используется контейнер `multimap` для управления последовательность элементов как a \(почти\) сбалансировало упорядоченное дерево узлов, каждый расположении один элемент.  Элемент состоит из ключа, для упорядочения последовательности и сопоставленного значение, которая осуществляет поиск для езды.  
  
 В описании ниже, `GValue` аналогично:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 Здесь:  
  
 `GKey` совпадает с `Key` если здесь не будет ссылочного типа, в случае которого это `Key^`  
  
 `GMapped` совпадает с `Mapped` если здесь не будет ссылочного типа, в случае которого это `Mapped^`  
  
## Синтаксис  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class multimap  
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
  
 Сопоставленного  
 Тип дополнительного компонента элемента в контролируемой последовательности.  
  
## Члены  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|[multimap::const\_iterator](../dotnet/multimap-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[multimap::const\_reference](../dotnet/multimap-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[multimap::const\_reverse\_iterator](../Topic/multimap::const_reverse_iterator%20\(STL-CLR\).md)|Тип константы обратного итератора для контролируемой последовательности.|  
|[multimap::difference\_type](../dotnet/multimap-difference-type-stl-clr.md)|Тип расстояния \(возможно, подписанного a 2\) между элементами.|  
|[multimap::generic\_container](../dotnet/multimap-generic-container-stl-clr.md)|Тип универсального интерфейса для контейнера.|  
|[multimap::generic\_iterator](../dotnet/multimap-generic-iterator-stl-clr.md)|Тип итератора для универсального интерфейса для контейнера.|  
|[multimap::generic\_reverse\_iterator](../dotnet/multimap-generic-reverse-iterator-stl-clr.md)|Тип обратного итератора для универсального интерфейса для контейнера.|  
|[multimap::generic\_value](../dotnet/multimap-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[multimap::iterator](../dotnet/multimap-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[multimap::key\_compare](../dotnet/multimap-key-compare-stl-clr.md)|Порядок делегат для 2 ключей.|  
|[multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md)|Тип ключа упорядочения.|  
|[multimap::mapped\_type](../dotnet/multimap-mapped-type-stl-clr.md)|Тип сопоставленного значение, связанной с каждым ключом.|  
|[multimap::reference](../dotnet/multimap-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[multimap::reverse\_iterator](../Topic/multimap::reverse_iterator%20\(STL-CLR\).md)|Тип обратного итератора для контролируемой последовательности.|  
|[multimap::size\_type](../Topic/multimap::size_type%20\(STL-CLR\).md)|Тип расстояния a \(не отрицательного 2\) между элементами.|  
|[multimap::value\_compare](../Topic/multimap::value_compare%20\(STL-CLR\).md)|Порядок делегат для 2 значений элементов.|  
|[multimap::value\_type](../dotnet/multimap-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция Member|Описание|  
|--------------------|--------------|  
|[multimap::begin](../dotnet/multimap-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[multimap::clear](../Topic/multimap::clear%20\(STL-CLR\).md)|Удаляет все элементы.|  
|[multimap::count](../dotnet/multimap-count-stl-clr.md)|Подсчитывает число элементов, соответствующий указанному ключу.|  
|[multimap::empty](../dotnet/multimap-empty-stl-clr.md)|Тесты отсутствуют ли какие\-либо элементы.|  
|[multimap::end](../dotnet/multimap-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[multimap::equal\_range](../dotnet/multimap-equal-range-stl-clr.md)|Находит диапазон, соответствующий указанному ключу.|  
|[multimap::erase](../dotnet/multimap-erase-stl-clr.md)|Удаляет элементы в указанных положениях.|  
|[multimap::find](../dotnet/multimap-find-stl-clr.md)|Определяет элемент, соответствующий указанному ключу.|  
|[multimap::insert](../dotnet/multimap-insert-stl-clr.md)|Добавляет элементы.|  
|[multimap::key\_comp](../dotnet/multimap-key-comp-stl-clr.md)|Копирует порядок делегат для 2 ключей.|  
|[multimap::lower\_bound](../dotnet/multimap-lower-bound-stl-clr.md)|Находит начало диапазона, соответствующий указанному ключу.|  
|[multimap::make\_value](../dotnet/multimap-make-value-stl-clr.md)|Создает объект значение.|  
|[multimap::multimap](../dotnet/multimap-multimap-stl-clr.md)|Создает объект контейнера.|  
|[multimap::rbegin](../dotnet/multimap-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[multimap::rend](../dotnet/multimap-rend-stl-clr.md)|Задает конец обратной управляемой последовательности.|  
|[multimap::size](../Topic/multimap::size%20\(STL-CLR\).md)|Подсчитывает количество элементов.|  
|[multimap::swap](../dotnet/multimap-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[multimap::to\_array](../dotnet/multimap-to-array-stl-clr.md)|Копирует контролируемая последовательность в новый массив.|  
|[multimap::upper\_bound](../dotnet/multimap-upper-bound-stl-clr.md)|Находит конечную точку диапазона, соответствующий указанному ключу.|  
|[multimap::value\_comp](../Topic/multimap::value_comp%20\(STL-CLR\).md)|Копирует порядок делегат для 2 значений элементов.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|[multimap::operator\=](../dotnet/multimap-operator-assign-stl-clr.md)|Заменяет контролируемая последовательность.|  
|[operator\!\= \(multimap\)](../Topic/operator!=%20\(multimap\)%20\(STL-CLR\).md)|Определяет, является ли объект `multimap` не равен другому объекту `multimap`.|  
|[operator\< \(multimap\)](../dotnet/operator-less-than-multimap-stl-clr.md)|Определяет, является ли объект `multimap` меньше другой объект `multimap`.|  
|[operator\<\= \(multimap\)](../dotnet/operator-less-or-equal-multimap-stl-clr.md)|Определяет, является ли объект `multimap` меньше или равно другому объекту `multimap`.|  
|[operator\=\= \(multimap\)](../dotnet/operator-equality-multimap-stl-lr.md)|Определяет, является ли объект `multimap` равен другому объекту `multimap`.|  
|[operator\> \(multimap\)](../dotnet/operator-greater-than-multimap-stl-clr.md)|Определяет, является ли объект `multimap` больше другого объекта `multimap`.|  
|[operator\>\= \(multimap\)](../Topic/operator%3E=%20\(multimap\)%20\(STL-CLR\).md)|Определяет, является ли объект `multimap` больше или равно другому объекту `multimap`.|  
  
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
  
 Объект сортирует последовательность его элементы управления путем вызова делегата сохраненный объект типа [multimap::key\_compare](../dotnet/multimap-key-compare-stl-clr.md).  Можно определить, сохраненный объект делегата при построении multimap; если не указан ни один объект делегата, по умолчанию используется сравнение `operator<(key_type, key_type)`.  Чтобы открыть этот сохраненный объект, вызвав функцию\-член [multimap::key\_comp](../dotnet/multimap-key-comp-stl-clr.md)`()`.  
  
 Такой объект делегата должен создать строгого слабое упорядочение на ключах типа [multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md).  Это означает, что для всех ключей, 2 `X` и `Y`:  
  
 `key_comp()(X, Y)` возвращает тот же логический результат при каждом вызове.  
  
 Если `key_comp()(X, Y)` выполняется, `key_comp()(Y, X)` должно быть значение.  
  
 Если `key_comp()(X, Y)` выполняется, считается, что приказано `X` перед `Y`.  
  
 Если `!key_comp()(X, Y) && !key_comp()(Y, X)` выполняется, считается, что имеют `X` и `Y` соответствующий заказ.  
  
 Для любого элемента `X`, предшествующего `Y` в контролируемой последовательности, `key_comp()(Y, X)` ложно. \(Для объекта делегата, по умолчанию ключи никогда не уменьшает значение\). В отличие от класса шаблона [map](../dotnet/map-stl-clr.md), объект класса шаблона `multimap` не требует ключи для всех элементов уникальны. \(Два или более ключи могут иметь соответствующий заказ\).  
  
 Каждый элемент содержит отдельный ключ и сопоставляются значению.  Последовательность представляется в виде, позволяющем поиск, вставки и удаления произвольного элемента с несколькими операций пропорциональных в логарифму числа элементов в последовательности \(логарифмическом времени\).  Кроме того, что вставка элемента нет итераторы, и удаление элементов только что эти итераторы, указывающих на удаленный элемент.  
  
 Multimap поддерживает двунаправленные итераторы\), что позволяет шаг с соседним элементам заданного итератор, обозначает элемент в контролируемой последовательности.  Специальный головной узел соответствует итератору возвращенным [multimap::end](../dotnet/multimap-end-stl-clr.md)`()`.  Можно декремент такой итератор для достижения последнего элемента в контролируемой последовательности, если в настоящий момент.  Можно увеличить итератор multimap для достижения головного узла, а затем сравнивает равно `end()`.  Однако нельзя разыменование итератор, `end()`.  
  
 Обратите внимание, что нельзя обращаться к элементу multimap непосредственно заданного свою позицию численную \-\- это требует произвольного доступа итератора.  
  
 Итератор multimap хранит дескриптор его связанный узел multimap, который, в свою очередь, сохраняет его связанный дескриптор контейнер.  Можно использовать итераторы только со связанными объектами контейнера.  Итератор multimap остается допустимым, пока его связанный узел multimap связан с определенным multimap.  Кроме того, допустимый итератор dereferencable \-\- его можно использовать для доступа или изменения значения элемента он обозначает \-\- пока не равно `end()`.  
  
 Стирающ или удаление элементов вызывает деструктор этого сохраненного значения.  Удалить контейнер удаляются все элементы.  Таким образом, тип которого контейнер элемента ссылочный класс гарантирует, что никаких элементов не переживают контейнер.  Однако стоит отметить, что контейнер дескрипторов делает `not` уничтожает его элементы.  
  
## Требования  
 **Заголовок:**\<cliext\/map\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [map](../dotnet/map-stl-clr.md)   
 [multiset](../dotnet/multiset-stl-clr.md)   
 [набор](../dotnet/set-stl-clr.md)   
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)