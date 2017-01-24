---
title: "stack (STL/CLR) | Microsoft Docs"
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
  - "cliext::stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<cliext/stack> - заголовок [STL/CLR]"
  - "<stack> - заголовок [STL/CLR]"
  - "stack - класс [STL/CLR]"
ms.assetid: 6ee96b9f-8a33-4cf7-b7e0-6535c24bdefb
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# stack (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описание объекта класса шаблона, что элементы управления менять\- длины последовательность элементов с " последним пришел — первым в доступе.  Используется адаптер `stack` контейнера для управления основной контейнер как стека внедрения — вниз.  
  
 В описании ниже, `GValue` совпадает с `Value` если здесь не будет ссылочного типа, в случае которого это `Value^`.  Аналогично, `GContainer` совпадает с `Container` если здесь не будет ссылочного типа, в случае которого это `Container^`.  
  
## Синтаксис  
  
```  
template<typename Value,  
    typename Container>  
    ref class stack  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IStack<GValue, GContainer>  
    { ..... };  
```  
  
#### Параметры  
 Значение  
 Тип элемента в управляемой последовательности.  
  
 Контейнер  
 Тип базового контейнера.  
  
## Члены  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|[stack::const\_reference](../dotnet/stack-const-reference-stl-clr.md)|Тип постоянной ссылки на элемент.|  
|[stack::container\_type](../dotnet/stack-container-type-stl-clr.md)|Тип базового контейнера.|  
|[stack::difference\_type](../dotnet/stack-difference-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[stack::generic\_container](../Topic/stack::generic_container%20\(STL-CLR\).md)|Тип универсального интерфейса для адаптера контейнера.|  
|[stack::generic\_value](../dotnet/stack-generic-value-stl-clr.md)|Тип элемента для универсального интерфейса для адаптера контейнера.|  
|[stack::reference](../dotnet/stack-reference-stl-clr.md)|Тип ссылки на элемент.|  
|[stack::size\_type](../dotnet/stack-size-type-stl-clr.md)|Тип расстояния со знаком между двумя элементами.|  
|[stack::value\_type](../dotnet/stack-value-type-stl-clr.md)|Тип элемента.|  
  
|Функция Member|Описание|  
|--------------------|--------------|  
|[stack::assign](../Topic/stack::assign%20\(STL-CLR\).md)|Заменяет все элементы.|  
|[stack::empty](../dotnet/stack-empty-stl-clr.md)|Тесты отсутствуют ли какие\-либо элементы.|  
|[stack::get\_container](../Topic/stack::get_container%20\(STL-CLR\).md)|Осуществляет доступ к базовому контейнеру.|  
|[stack::pop](../Topic/stack::pop%20\(STL-CLR\).md)|Удаляет последний элемент.|  
|[stack::push](../dotnet/stack-push-stl-clr.md)|Добавляет новый последний элемент.|  
|[stack::size](../dotnet/stack-size-stl-clr.md)|Подсчитывает количество элементов.|  
|[stack::stack](../dotnet/stack-stack-stl-clr.md)|Создает объект контейнера.|  
|[stack::top](../dotnet/stack-top-stl-clr.md)|Получает последний элемент.|  
|[stack::to\_array](../dotnet/stack-to-array-stl-clr.md)|Копирует контролируемая последовательность в новый массив.|  
  
|Свойство|Описание|  
|--------------|--------------|  
|[stack::top\_item](../dotnet/stack-top-item-stl-clr.md)|Получает последний элемент.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|[stack::operator\=](../dotnet/stack-operator-assign-stl-clr.md)|Заменяет контролируемая последовательность.|  
|[operator\!\= \(stack\)](../dotnet/operator-inequality-stack-stl-clr.md)|Определяет, является ли объект `stack` не равен другому объекту `stack`.|  
|[operator\< \(stack\)](../dotnet/operator-less-than-stack-stl-clr.md)|Определяет, является ли объект `stack` меньше другой объект `stack`.|  
|[operator\<\= \(stack\)](../dotnet/operator-less-or-equal-stack-stl-clr.md)|Определяет, является ли объект `stack` меньше или равно другому объекту `stack`.|  
|[operator\=\= \(stack\)](../dotnet/operator-equality-stack-stl-clr.md)|Определяет, является ли объект `stack` равен другому объекту `stack`.|  
|[operator\> \(stack\)](../dotnet/operator-greater-than-stack-stl-clr.md)|Определяет, является ли объект `stack` больше другого объекта `stack`.|  
|[operator\>\= \(stack\)](../Topic/operator%3E=%20\(stack\)%20\(STL-CLR\).md)|Определяет, является ли объект `stack` больше или равно другому объекту `stack`.|  
  
## Интерфейсы  
  
|Интерфейс|Описание|  
|---------------|--------------|  
|<xref:System.ICloneable>|Дублируйте объект.|  
|IStack\<Value, Container\>|Обслуживайте универсальный адаптер контейнера.|  
  
## Заметки  
 Объект выделяет и освобождает хранилище для последовательности его элементы управления через основной контейнер, типа `Container`, который хранит элементы `Value` и увеличивается по требованию.  Объект ограничивает доступ к отправлять и извлечь только последний элемент, реализующий a " последним пришел — первым обслужен out очереди \(также известной как очередь, или стек LIFO\).  
  
## Требования  
 **Заголовок:**\<cliext\/stack\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [deque](../dotnet/deque-stl-clr.md)   
 [list](../dotnet/list-stl-clr.md)   
 [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)   
 [queue](../Topic/queue%20\(STL-CLR\).md)   
 [вектор](../dotnet/vector-stl-clr.md)   
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)