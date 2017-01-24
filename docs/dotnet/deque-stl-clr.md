---
title: "deque (STL/CLR) | Microsoft Docs"
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
  - "cliext::deque"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/deque> - заголовок [STL/CLR]"
  - "<deque> - заголовок [STL/CLR]"
  - "deque - класс [STL/CLR]"
ms.assetid: dd669da3-3c0e-45e9-8596-f6b483720941
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание объекта класса шаблона, что элементы управления менять\- длины последовательность элементов с прямой доступ.  Используется контейнер `deque` для управления последовательность элементов, выглядит как непрерывный блок хранилища, но с может увеличивать или уменьшать на любом конце без необходимости копировать все оставшиеся элементы.  Таким образом, он может реализовать эффективно `double-ended queue`. \(Это имя\).  
  
 В описании ниже, `GValue` совпадает с `Value` если здесь не будет ссылочного типа, в случае которого это `Value^`.  
  
## Синтаксис  
  
```  
template<typename Value>  
    ref class deque  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IDeque<GValue>  
    { ..... };  
```  
  
#### Параметры  
 GValue  
 Универсальный тип элемента в контролируемой последовательности.  
  
 Значение  
 Тип элемента в управляемой последовательности.  
  
## Члены  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|[deque::const\_iterator](../Topic/deque::const_iterator%20\(STL-CLR\).md)|Тип постоянного итератора для управляемой последовательности.|  
|[deque::const\_reference](../dotnet/deque-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[deque::const\_reverse\_iterator](../dotnet/deque-const-reverse-iterator-stl-clr.md)|Тип константы обратного итератора для контролируемой последовательности.|  
|[deque::difference\_type](../dotnet/deque-difference-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[deque::generic\_container](../Topic/deque::generic_container%20\(STL-CLR\).md)|Тип универсального интерфейса для контейнера.|  
|[deque::generic\_iterator](../dotnet/deque-generic-iterator-stl-clr.md)|Тип итератора для универсального интерфейса для контейнера.|  
|[deque::generic\_reverse\_iterator](../Topic/deque::generic_reverse_iterator%20\(STL-CLR\).md)|Тип обратного итератора для универсального интерфейса для контейнера.|  
|[deque::generic\_value](../Topic/deque::generic_value%20\(STL-CLR\).md)|Тип элемента для универсального интерфейса для контейнера.|  
|[deque::iterator](../dotnet/deque-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[deque::reference](../dotnet/deque-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[deque::reverse\_iterator](../dotnet/deque-reverse-iterator-stl-clr.md)|Тип обратного итератора для контролируемой последовательности.|  
|[deque::size\_type](../dotnet/deque-size-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[deque::value\_type](../Topic/deque::value_type%20\(STL-CLR\).md)|Тип элемента.|  
  
|Функция Member|Описание|  
|--------------------|--------------|  
|[deque::assign](../dotnet/deque-assign-stl-clr.md)|Заменяет все элементы.|  
|[deque::at](../dotnet/deque-at-stl-clr.md)|Получает элемент в указанной позиции.|  
|[deque::back](../dotnet/deque-back-stl-clr.md)|Получает последний элемент.|  
|[deque::begin](../dotnet/deque-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[deque::clear](../dotnet/deque-clear-stl-clr.md)|Удаляет все элементы.|  
|[deque::deque](../dotnet/deque-deque-stl-clr.md)|Создает объект контейнера.|  
|[deque::empty](../dotnet/deque-empty-stl-clr.md)|Тесты отсутствуют ли какие\-либо элементы.|  
|[deque::end](../Topic/deque::end%20\(STL-CLR\).md)|Задает конец управляемой последовательности.|  
|[deque::erase](../Topic/deque::erase%20\(STL-CLR\).md)|Удаляет элементы в указанных положениях.|  
|[deque::front](../Topic/deque::front%20\(STL-CLR\).md)|Получение первого элемента.|  
|[deque::insert](../dotnet/deque-insert-stl-clr.md)|Добавляет элементы в указанной позиции.|  
|[deque::pop\_back](../dotnet/deque-pop-back-stl-clr.md)|Удаляет последний элемент.|  
|[deque::pop\_front](../dotnet/deque-pop-front-stl-clr.md)|Удаляет первый элемент.|  
|[deque::push\_back](../dotnet/deque-push-back-stl-clr.md)|Добавляет новый последний элемент.|  
|[deque::push\_front](../dotnet/deque-push-front-stl-clr.md)|Добавляет новый первый элемент.|  
|[deque::rbegin](../dotnet/deque-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[deque::rend](../Topic/deque::rend%20\(STL-CLR\).md)|Задает конец обратной управляемой последовательности.|  
|[deque::resize](../dotnet/deque-resize-stl-clr.md)|Изменяет количество элементов.|  
|[deque::size](../Topic/deque::size%20\(STL-CLR\).md)|Подсчитывает количество элементов.|  
|[deque::swap](../dotnet/deque-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[deque::to\_array](../dotnet/deque-to-array-stl-clr.md)|Копирует контролируемая последовательность в новый массив.|  
  
|Свойство|Описание|  
|--------------|--------------|  
|[deque::back\_item](../Topic/deque::back_item%20\(STL-CLR\).md)|Получает последний элемент.|  
|[deque::front\_item](../dotnet/deque-front-item-stl-clr.md)|Получение первого элемента.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|[deque::operator\!\=](../dotnet/deque-operator-inequality-stl-clr.md)|Определяет, являются ли два объекта `deque` неравными.|  
|[deque::operator](../Topic/deque::operator\(STL-CLR\).md)|Получает элемент в указанной позиции.|  
|[operator\< \(deque\)](../dotnet/operator-less-than-deque-stl-clr.md)|Определяет, является ли объект `deque` меньше другой объект `deque`.|  
|[operator\<\= \(deque\)](../dotnet/operator-less-or-equal-deque-stl-clr.md)|Определяет, является ли объект `deque` меньше или равно другому объекту `deque`.|  
|[operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)|Заменяет контролируемая последовательность.|  
|[operator\=\= \(deque\)](../dotnet/operator-equality-deque-stl-clr.md)|Определяет, является ли объект `deque` равен другому объекту `deque`.|  
|[operator\> \(deque\)](../dotnet/operator-greater-than-deque-stl-clr.md)|Определяет, является ли объект `deque` больше другого объекта `deque`.|  
|[operator\>\= \(deque\)](../dotnet/operator-greater-or-equal-deque-stl-clr.md)|Определяет, является ли объект `deque` больше или равно другому объекту `deque`.|  
  
## Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|--------------|  
|<xref:System.ICloneable>|Дублируйте объект.|  
|<xref:System.Collections.IEnumerable>|Последовательность между элементами.|  
|<xref:System.Collections.ICollection>|Обеспечение группу в составе элементы.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Через последовательность типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Обеспечение группу в составе типизированных элементов.|  
|<xref:System.Collections.Generic.IList%601>|Maintain является группу в составе типизированных элементов.|  
|IDeque\<Value\>|Обслуживайте универсальный контейнер.|  
  
## Заметки  
 Объект выделяет и освобождает хранилище для последовательности его элементов управления с помощью сохраненного массив дескрипторов, которые определяют блоки элементов `Value`.  Массив увеличивается по требованию.  Рост происходит таким образом, что затраты или prepending или добавить новый элемент постоянно время, и никакие оставшиеся элементы не повреждены.  Можно также удалить элемент на одном конце при расчете времени и без нарушить остальных элементов.  Таким образом, deque хорошим кандидатом для основного контейнера для шаблона класса шаблона класса [queue](../Topic/queue%20\(STL-CLR\).md) или [стек](../dotnet/stack-stl-clr.md).  
  
 Объект `deque` поддерживает произвольного доступа являются итераторы. это означает, что можно непосредственно ссылается на элемент заданного численную свою позицию, подсчитывая с нуля первого \(переднего\) элемента, в [deque::size](../Topic/deque::size%20\(STL-CLR\).md)`() - 1` для последнего \(заднего\) элемента.  Это также означает, что deque хорошим кандидатом для основного контейнера для шаблона класса [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md).  
  
 Итератор deque хранит дескриптор его связанный объект deque вместе с смещением элемента он указывает.  Можно использовать итераторы только со связанными объектами контейнера.  Смещение элемента deque `not` обязательно совпадает с его положения.  Введенный первый элемент имеет косое ноль, добавлен следующий элемент имеет косое 1, но следующий; их имена предваряются словами элемент имеет косое \-1.  
  
 Вставка или стирать элементы на любом конце делают `not` изменяют значение элемента, хранящегося в любом допустимого смещении.  Вставка или стирающ внутренний элемент, однако изменить `can` значения элемента, хранящегося в заданном смещении, поэтому значение значение итератором также может изменить. \(Контейнер может копировать элементы вверх или вниз, чтобы создать передать перед вставкой или заполнить передать после стирания\). Однако итератор deque остается допустимым, пока его смещение задает допустимый элемент.  Кроме того, допустимый итератор остается dereferencable \-\- его можно использовать для доступа или изменения значения элемента он обозначает \-\- при его смещение не равно смещению для итератора возвращаемого `end()`.  
  
 Стирающ или удаление элементов вызывает деструктор этого сохраненного значения.  Удалить контейнер удаляются все элементы.  Таким образом, тип которого контейнер элемента ссылочный класс гарантирует, что никаких элементов не переживают контейнер.  Однако стоит отметить, что контейнер дескрипторов делает `not` уничтожает его элементы.  
  
## Требования  
 **Заголовок:**\<cliext\/deque\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)   
 [queue](../Topic/queue%20\(STL-CLR\).md)   
 [стек](../dotnet/stack-stl-clr.md)   
 [вектор](../dotnet/vector-stl-clr.md)   
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)