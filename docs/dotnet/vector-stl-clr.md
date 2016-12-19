---
title: "vector (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/vector> - заголовок [STL/CLR]"
  - "<vector> - заголовок [STL/CLR]"
  - "vector - класс [STL/CLR]"
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vector (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание объекта класса шаблона, что элементы управления менять\- длины последовательность элементов с прямой доступ.  Используется контейнер `vector` для управления последовательность элементов в непрерывном блоке хранилища.  Блок реализуется как массив, который увеличивается по требованию.  
  
 В описании ниже, `GValue` совпадает с `Value` если здесь не будет ссылочного типа, в случае которого это `Value^`.  
  
## Синтаксис  
  
```  
template<typename Value>  
    ref class vector  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IVector<GValue>  
    { ..... };  
```  
  
#### Параметры  
 Значение  
 Тип элемента в управляемой последовательности.  
  
## Члены  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|[vector::const\_iterator](../dotnet/vector-const-iterator-stl-clr.md)|Тип постоянного итератора для управляемой последовательности.|  
|[vector::const\_reference](../dotnet/vector-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[vector::const\_reverse\_iterator](../dotnet/vector-const-reverse-iterator-stl-clr.md)|Тип константы обратного итератора для контролируемой последовательности.|  
|[vector::difference\_type](../dotnet/vector-difference-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[vector::generic\_container](../dotnet/vector-generic-container-stl-clr.md)|Тип универсального интерфейса для контейнера.|  
|[vector::generic\_iterator](../dotnet/vector-generic-iterator-stl-clr.md)|Тип итератора для универсального интерфейса для контейнера.|  
|[vector::generic\_reverse\_iterator](../Topic/vector::generic_reverse_iterator%20\(STL-CLR\).md)|Тип обратного итератора для универсального интерфейса для контейнера.|  
|[vector::generic\_value](../dotnet/vector-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для контейнера.|  
|[vector::iterator](../dotnet/vector-iterator-stl-clr.md)|Тип итератора для управляемой последовательности.|  
|[vector::reference](../dotnet/vector-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[vector::reverse\_iterator](../dotnet/vector-reverse-iterator-stl-clr.md)|Тип обратного итератора для контролируемой последовательности.|  
|[vector::size\_type](../dotnet/vector-size-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[vector::value\_type](../Topic/vector::value_type%20\(STL-CLR\).md)|Тип элемента.|  
  
|Функция Member|Описание|  
|--------------------|--------------|  
|[vector::assign](../Topic/vector::assign%20\(STL-CLR\).md)|Заменяет все элементы.|  
|[vector::at](../dotnet/vector-at-stl-clr.md)|Получает элемент в указанной позиции.|  
|[vector::back](../dotnet/vector-back-stl-clr.md)|Получает последний элемент.|  
|[vector::begin](../dotnet/vector-begin-stl-clr.md)|Задает начало управляемой последовательности.|  
|[vector::capacity](../dotnet/vector-capacity-stl-clr.md)|Возвращает объем пространства, выделенного для хранения контейнера.|  
|[vector::clear](../dotnet/vector-clear-stl-clr.md)|Удаляет все элементы.|  
|[vector::empty](../Topic/vector::empty%20\(STL-CLR\).md)|Тесты отсутствуют ли какие\-либо элементы.|  
|[vector::end](../dotnet/vector-end-stl-clr.md)|Задает конец управляемой последовательности.|  
|[vector::erase](../dotnet/vector-erase-stl-clr.md)|Удаляет элементы в указанных положениях.|  
|[vector::front](../dotnet/vector-front-stl-clr.md)|Получение первого элемента.|  
|[vector::insert](../Topic/vector::insert%20\(STL-CLR\).md)|Добавляет элементы в указанной позиции.|  
|[vector::pop\_back](../Topic/vector::pop_back%20\(STL-CLR\).md)|Удаляет последний элемент.|  
|[vector::push\_back](../dotnet/vector-push-back-stl-clr.md)|Добавляет новый последний элемент.|  
|[vector::rbegin](../dotnet/vector-rbegin-stl-clr.md)|Задает начало обратной управляемой последовательности.|  
|[vector::rend](../dotnet/vector-rend-stl-clr.md)|Задает конец обратной управляемой последовательности.|  
|[vector::reserve](../Topic/vector::reserve%20\(STL-CLR\).md)|Предоставляет минимальные ресурсы роста для контейнера.|  
|[vector::resize](../Topic/vector::resize%20\(STL-CLR\).md)|Изменяет количество элементов.|  
|[vector::size](../dotnet/vector-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[vector::swap](../dotnet/vector-swap-stl-clr.md)|Меняет местами содержимое двух контейнеров.|  
|[vector::to\_array](../dotnet/vector-to-array-stl-clr.md)|Копирует контролируемая последовательность в новый массив.|  
|[vector::vector](../dotnet/vector-vector-stl-clr.md)|Создает объект контейнера.|  
  
|Свойство|Описание|  
|--------------|--------------|  
|[vector::back\_item](../dotnet/vector-back-item-stl-clr.md)|Получает последний элемент.|  
|[vector::front\_item](../dotnet/vector-front-item-stl-clr.md)|Получение первого элемента.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|[vector::operator\=](../dotnet/vector-operator-assign-stl-clr.md)|Заменяет контролируемая последовательность.|  
|[vector::operator](../dotnet/vector-operator-stl-clr.md)|Получает элемент в указанной позиции.|  
|[operator\!\= \(vector\)](../Topic/operator!=%20\(vector\)%20\(STL-CLR\).md)|Определяет, является ли объект `vector` не равен другому объекту `vector`.|  
|[operator\< \(vector\)](../dotnet/operator-less-than-vector-stl-clr.md)|Определяет, является ли объект `vector` меньше другой объект `vector`.|  
|[operator\<\= \(vector\)](../dotnet/operator-less-or-equal-vector-stl-clr.md)|Определяет, является ли объект `vector` меньше или равно другому объекту `vector`.|  
|[operator\=\= \(vector\)](../Topic/operator==%20\(vector\)%20\(STL-CLR\).md)|Определяет, является ли объект `vector` равен другому объекту `vector`.|  
|[operator\> \(vector\)](../dotnet/operator-greater-than-vector-stl-clr.md)|Определяет, является ли объект `vector` больше другого объекта `vector`.|  
|[operator\>\= \(vector\)](../Topic/operator%3E=%20\(vector\)%20\(STL-CLR\).md)|Определяет, является ли объект `vector` больше или равно другому объекту `vector`.|  
  
## Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|--------------|  
|<xref:System.ICloneable>|Дублируйте объект.|  
|<xref:System.Collections.IEnumerable>|Последовательность между элементами.|  
|<xref:System.Collections.ICollection>|Обеспечение группу в составе элементы.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Через последовательность типизированных элементов.|  
|<xref:System.Collections.Generic.ICollection%601>|Обеспечение группу в составе типизированных элементов.|  
|<xref:System.Collections.Generic.IList%601>|Maintain является группу в составе типизированных элементов.|  
|IVector\<Value\>|Обслуживайте универсальный контейнер.|  
  
## Заметки  
 Объект выделяет и освобождает хранилище для последовательности его элементов управления с помощью сохраненного массив элементов `Value`, который увеличивается по требованию.  Рост происходит таким образом, что затраты добавить новый элемент амортизирована постоянно время.  Другими словами, стоимость добавлений элементов в конце не растет, в среднем, как длина контролируемой последовательности получает крупнее.  Таким образом, вектор хорошим кандидатом для основного контейнера для шаблона класса [стек](../dotnet/stack-stl-clr.md).  
  
 `vector` поддерживает произвольного доступа являются итераторы. это означает, что можно непосредственно ссылается на элемент заданного численную свою позицию, подсчитывая с нуля первого \(переднего\) элемента, в [vector::size](../dotnet/vector-size-stl-clr.md)`() - 1` для последнего \(заднего\) элемента.  Это также означает, что вектор хорошим кандидатом для основного контейнера для шаблона класса [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md).  
  
 Итератор вектора содержит дескриптор его связанный объект вектора вместе с смещением элемента он указывает.  Можно использовать итераторы только со связанными объектами контейнера.  Смещение элементов вектора совпадает с его положение.  
  
 Вставка или стирать элементы могут изменять значения элемента, хранящегося в заданном положении, поэтому значение значение итератором также может изменить. \(Контейнер может копировать элементы вверх или вниз, чтобы создать передать перед вставкой или заполнить передать после стирания\). Однако итератор вектора остается допустимым, пока его смещение в диапазоне `[0,` [vector::size](../dotnet/vector-size-stl-clr.md)`()]`.  Кроме того, допустимый итератор остается dereferencable \-\- его можно использовать для доступа или изменения значения элемента он обозначает \-\- при его смещение не равно `size()`.  
  
 Стирающ или удаление элементов вызывает деструктор этого сохраненного значения.  Удалить контейнер удаляются все элементы.  Таким образом, тип которого контейнер элемента ссылочный класс гарантирует, что никаких элементов не переживают контейнер.  Однако стоит отметить, что контейнер дескрипторов делает `not` уничтожает его элементы.  
  
## Требования  
 **Заголовок:**\<cliext\/vector\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [deque](../dotnet/deque-stl-clr.md)   
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)   
 [queue](../Topic/queue%20\(STL-CLR\).md)   
 [стек](../dotnet/stack-stl-clr.md)   
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)