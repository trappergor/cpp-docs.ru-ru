---
title: "Класс array (STL) | Microsoft Docs"
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
  - "array/std::tr1::array"
  - "std.tr1.array"
  - "array"
  - "std::tr1::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array - класс [TR1]"
ms.assetid: fdfd43a5-b2b5-4b9e-991f-93bf10fb4293
caps.latest.revision: 22
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс array (STL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает объект, управляющий последовательностью из элементов `N` типа `Ty`.  Последовательность хранится как массив `Ty` в объекте `array<Ty, N>`.  
  
## Синтаксис  
  
```  
template<class Ty, std::size_t N>  
    class array;  
```  
  
#### Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`Ty`|Тип элемента.|  
|`N`|Количество элементов|  
  
## Члены  
  
|||  
|-|-|  
|Определение типа|Описание|  
|[array::const\_iterator](../Topic/array::const_iterator.md)|Тип постоянного итератора для управляемой последовательности.|  
|[array::const\_pointer](../Topic/array::const_pointer.md)|Тип постоянного указателя на элемент.|  
|[array::const\_reference](../Topic/array::const_reference.md)|Тип постоянной ссылки на элемент.|  
|[array::const\_reverse\_iterator](../Topic/array::const_reverse_iterator.md)|Тип постоянного обратного итератора для управляемой последовательности.|  
|[array::difference\_type](../Topic/array::difference_type.md)|Тип расстояния со знаком между двумя элементами.|  
|[array::iterator](../Topic/array::iterator.md)|Тип итератора для управляемой последовательности.|  
|[array::pointer](../Topic/array::pointer.md)|Тип указателя на элемент.|  
|[array::reference](../Topic/array::reference.md)|Тип ссылки на элемент.|  
|[array::reverse\_iterator](../Topic/array::reverse_iterator.md)|Тип обратного итератора для управляемой последовательности.|  
|[array::size\_type](../Topic/array::size_type.md)|Тип беззнакового расстояния между двумя элементами.|  
|[array::value\_type](../Topic/array::value_type.md)|Тип элемента.|  
  
|||  
|-|-|  
|Функция\-член|Описание|  
|[array::array](../Topic/array::array.md)|Создает объект массива.|  
|[array::assign](../Topic/array::assign.md)|Заменяет все элементы.|  
|[array::at](../Topic/array::at.md)|Обращается к элементу в указанной позиции.|  
|[array::back](../Topic/array::back.md)|Обращается к последнему элементу.|  
|[array::begin](../Topic/array::begin.md)|Задает начало управляемой последовательности.|  
|[array::cbegin](../Topic/array::cbegin.md)|Возвращает постоянный итератор произвольного доступа, указывающий на первый элемент в массиве.|  
|[array::cend](../Topic/array::cend.md)|Возвращает постоянный итератор произвольного доступа, указывающий на предпоследнюю позицию массива.|  
|[array::crbegin](../Topic/array::crbegin.md)|Возвращает константный итератор, который указывает на первый элемент в обращенном массиве.|  
|[array::crend](../Topic/array::crend.md)|Возвращает постоянный итератор, который указывает на последний элемент в обратном массиве.|  
|[array::data](../Topic/array::data.md)|Получает адрес первого элемента.|  
|[array::empty](../Topic/array::empty.md)|Проверяет наличие элементов.|  
|[array::end](../Topic/array::end.md)|Задает конец управляемой последовательности.|  
|[array::fill](../Topic/array::fill.md)|Заменяет все элементы указанным значением.|  
|[array::front](../Topic/array::front.md)|Обращается к первому элементу.|  
|[array::max\_size](../Topic/array::max_size.md)|Подсчитывает количество элементов.|  
|[array::rbegin](../Topic/array::rbegin.md)|Задает начало обратной управляемой последовательности.|  
|[array::rend](../Topic/array::rend.md)|Задает конец обратной управляемой последовательности.|  
|[array::size](../Topic/array::size.md)|Подсчитывает количество элементов.|  
|[array::swap](../Topic/array::swap.md)|Меняет местами содержимое двух контейнеров.|  
  
|||  
|-|-|  
|Оператор|Описание|  
|[array::operator\=](../Topic/array::operator=.md)|Заменяет управляемую последовательность.|  
|[array::operator](../Topic/array::operator.md)|Обращается к элементу в указанной позиции.|  
  
## Заметки  
 У этого типа есть конструктор по умолчанию `array()` и оператор присваивания по умолчанию `operator=`. Тип удовлетворяет требованиям для `aggregate`.  Поэтому объекты типа `array<Ty, N>` можно инициализировать с помощью агрегатного инициализатора.  Например:  
  
```  
array<int, 4> ai = { 1, 2, 3 };  
```  
  
 создает объект `ai`, содержащий четыре целочисленных значения, инициализирует первые три элемента как 1, 2 и 3 соответственно и инициализирует четвертый элемент как 0.  
  
## Требования  
 **Заголовок:** \<array\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<array\>](../standard-library/array.md)