---
title: "list (STL/CLR) | Microsoft Docs"
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
  - "cliext::list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/list> - заголовок [STL/CLR]"
  - "<list> - заголовок [STL/CLR]"
  - "list - класс [STL/CLR]"
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание объекта класса шаблона, что элементы управления менять\- длины последовательность элементов являются двунаправленными, имеет доступ.  Используется контейнер `list` для управления последовательность элементов в качестве двунаправленного связанного списка узлов, каждый расположении один элемент.  
  
 В описании ниже, `GValue` совпадает с `Value` если здесь не будет ссылочного типа, в случае которого это `Value^`.  
  
## Синтаксис  
  
```  
template<typename Value>  
    ref class list  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        Microsoft::VisualC::StlClr::IList<GValue>  
    { ..... };  
```  
  
#### Параметры  
 Значение  
 Тип элемента в управляемой последовательности.  
  
## Члены  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|[list::const\_iterator](../dotnet/list-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[list::const\_reference](../dotnet/list-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[list::const\_reverse\_iterator](../dotnet/list-const-reverse-iterator-stl-clr.md)|Тип константы обратного итератора для контролируемой последовательности.|  
|[list::difference\_type](../dotnet/list-difference-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[list::generic\_container](../dotnet/list-generic-container-stl-clr.md)|Тип универсального интерфейса для контейнера.|  
|[list::generic\_iterator](../Topic/list::generic_iterator%20\(STL-CLR\).md)|Тип итератора для универсального интерфейса для контейнера.|  
|[list::generic\_reverse\_iterator](../dotnet/list-generic-reverse-iterator-stl-clr.md)|Тип обратного итератора для универсального интерфейса для контейнера.|  
|[list::generic\_value](../dotnet/list-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[list::iterator](../dotnet/list-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[list::reference](../dotnet/list-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[list::reverse\_iterator](../dotnet/list-reverse-iterator-stl-clr.md)|Тип обратного итератора для контролируемой последовательности.|  
|[list::size\_type](../dotnet/list-size-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[list::value\_type](../dotnet/list-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция Member|Описание|  
|--------------------|--------------|  
|[list::assign](../dotnet/list-assign-stl-clr.md)|Заменяет все элементы.|  
|[list::back](../dotnet/list-back-stl-clr.md)|Получает последний элемент.|  
|[list::begin](../Topic/list::begin%20\(STL-CLR\).md)|Задает начало управляемой последовательности.|  
|[list::clear](../dotnet/list-clear-stl-clr.md)|Удаляет все элементы.|  
|[list::empty](../dotnet/list-empty-stl-clr.md)|Тесты отсутствуют ли какие\-либо элементы.|  
|[list::end](../Topic/list::end%20\(STL-CLR\).md)|Задает конец управляемой последовательности.|  
|[list::erase](../dotnet/list-erase-stl-clr.md)|Удаляет элементы в указанных положениях.|  
|[list::front](../dotnet/list-front-stl-clr.md)|Получение первого элемента.|  
|[list::insert](../dotnet/list-insert-stl-clr.md)|Добавляет элементы в указанной позиции.|  
|[list::list](../dotnet/list-list-stl-clr.md)|Создает объект контейнера.|  
|[list::merge](../dotnet/list-merge-stl-clr.md)|Объединяет две упорядоченные управляемые последовательности.|  
|[list::pop\_back](../dotnet/list-pop-back-stl-clr.md)|Удаляет последний элемент.|  
|[list::pop\_front](../dotnet/list-pop-front-stl-clr.md)|Удаляет первый элемент.|  
|[list::push\_back](../dotnet/list-push-back-stl-clr.md)|Добавляет новый последний элемент.|  
|[list::push\_front](../Topic/list::push_front%20\(STL-CLR\).md)|Добавляет новый первый элемент.|  
|[list::rbegin](../dotnet/list-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[list::remove](../dotnet/list-remove-stl-clr.md)|Удаляет элемент с указанным значением.|  
|[list::remove\_if](../dotnet/list-remove-if-stl-clr.md)|Удаляет элементы, прошедшие определенного теста.|  
|[list::rend](../Topic/list::rend%20\(STL-CLR\).md)|Задает конец обратной управляемой последовательности.|  
|[list::resize](../dotnet/list-resize-stl-clr.md)|Изменяет количество элементов.|  
|[list::reverse](../dotnet/list-reverse-stl-clr.md)|Возвращает контролируемую последовательность.|  
|[list::size](../dotnet/list-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[list::sort](../dotnet/list-sort-stl-clr.md)|Упорядочивает управляемую последовательность.|  
|[list::splice](../Topic/list::splice%20\(STL-CLR\).md)|Ссылки Restitches между узлами.|  
|[list::swap](../Topic/list::swap%20\(STL-CLR\).md)|Меняет местами содержимое двух контейнеров.|  
|[list::to\_array](../dotnet/list-to-array-stl-clr.md)|Копирует контролируемая последовательность в новый массив.|  
|[list::unique](../dotnet/list-unique-stl-clr.md)|Удаляет смежные элементы, которые прошли заданный тест.|  
  
|Свойство|Описание|  
|--------------|--------------|  
|[list::back\_item](../Topic/list::back_item%20\(STL-CLR\).md)|Получает последний элемент.|  
|[list::front\_item](../dotnet/list-front-item-stl-clr.md)|Получение первого элемента.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|[list::operator\=](../dotnet/list-operator-assign-stl-clr.md)|Заменяет контролируемая последовательность.|  
|[operator\!\= \(list\)](../dotnet/operator-inequality-list-stl-clr.md)|Определяет, является ли объект `list` не равен другому объекту `list`.|  
|[operator\< \(list\)](../dotnet/operator-less-than-list-stl-clr.md)|Определяет, является ли объект `list` меньше другой объект `list`.|  
|[operator\<\= \(list\)](../dotnet/operator-less-or-equal-list-stl-clr.md)|Определяет, является ли объект `list` меньше или равно другому объекту `list`.|  
|[operator\=\= \(list\)](../dotnet/operator-equality-list-stl-clr.md)|Определяет, является ли объект `list` равен другому объекту `list`.|  
|[operator\> \(list\)](../Topic/operator%3E%20\(list\)%20\(STL-CLR\).md)|Определяет, является ли объект `list` больше другого объекта `list`.|  
|[operator\>\= \(list\)](../dotnet/operator-greater-or-equal-list-stl-clr.md)|Определяет, является ли объект `list` больше или равно другому объекту `list`.|  
  
## Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|--------------|  
|<xref:System.ICloneable>|Дублируйте объект.|  
|<xref:System.Collections.IEnumerable>|Последовательность между элементами.|  
|<xref:System.Collections.ICollection>|Обеспечение группу в составе элементы.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Через последовательность типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Обеспечение группу в составе типизированных элементов.|  
|IList\<Value\>|Обслуживайте универсальный контейнер.|  
  
## Заметки  
 Объект выделяет и освобождает хранилище для последовательности его элементы управления, как отдельные узлы в двунаправленной связи ".  Он выполняет переупорядочивание элементов, изменив ссылки между узлами, не скопировать содержимое одного узла на другой.  Это означает, что можно добавлять и удалять элементы свободно, не нарушая остальных элементов.  Таким образом, список хорошим кандидатом для основного контейнера для шаблона класса шаблона класса [queue](../Topic/queue%20\(STL-CLR\).md) или [стек](../dotnet/stack-stl-clr.md).  
  
 Объект `list` поддерживает двунаправленные итераторы. это означает, что можно выполнить с соседним элементам заданного итератор, обозначает элемент в контролируемой последовательности.  Специальный головной узел соответствует итератору возвращенным [list::end](../Topic/list::end%20\(STL-CLR\).md)`()`.  Можно декремент такой итератор для достижения последнего элемента в контролируемой последовательности, если в настоящий момент.  Можно увеличить итератор списка для достижения головного узла, а затем сравнивает равно `end()`.  Однако нельзя разыменование итератор, `end()`.  
  
 Обратите внимание, что нельзя ссылаться на элемент списка непосредственно заданного свою позицию численную \-\- это требует произвольного доступа итератора.  Поэтому список `not` имени. в качестве основной контейнер для шаблона класса [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md).  
  
 Итератор списка содержит дескриптор его связанный узел списка, который в свою очередь содержит дескриптор его связанный контейнер.  Можно использовать итераторы только со связанными объектами контейнера.  Итератор списка остается допустимым, пока его связанный узел списка связан с некоторым списком.  Кроме того, допустимый итератор dereferencable \-\- его можно использовать для доступа или изменения значения элемента он обозначает \-\- пока не равно `end()`.  
  
 Стирающ или удаление элементов вызывает деструктор этого сохраненного значения.  Удалить контейнер удаляются все элементы.  Таким образом, тип которого контейнер элемента ссылочный класс гарантирует, что никаких элементов не переживают контейнер.  Однако стоит отметить, что контейнер дескрипторов делает `not` уничтожает его элементы.  
  
## Требования  
 **Заголовок:**\<cliext\/list\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [deque](../dotnet/deque-stl-clr.md)   
 [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)   
 [queue](../Topic/queue%20\(STL-CLR\).md)   
 [стек](../dotnet/stack-stl-clr.md)   
 [вектор](../dotnet/vector-stl-clr.md)   
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)