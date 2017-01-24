---
title: "&lt;utility&gt; | Microsoft Docs"
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
  - "<utility>"
  - "utility/std::<utility>"
  - "std.<utility>"
  - "std::<utility>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "utility - заголовок"
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет типы, функции и операторы библиотеки стандартных шаблонов \(STL\), которые помогают создавать и контролировать пары объектов, что полезно, когда два объекта должны рассматриваться как один.  
  
## Синтаксис  
  
```  
  
#include <utility>  
  
```  
  
## Заметки  
 Пары широко используются в стандартной библиотеке C\+\+.  Они необходимы как аргументы и возвращаемые значения для различных функций и как типы элементов для контейнеров, таких как [класс map](../Topic/map%20Class.md) и [класс multimap](../standard-library/multimap-class.md).  \<map\> автоматически включает заголовок \<utility\> для управления элементами типа пары «ключ — значение».  
  
### Классы  
  
|||  
|-|-|  
|[tuple\_element](../standard-library/tuple-element-class-utility.md)|Класс, который заключает в оболочку тип элемента `pair`.|  
|[tuple\_size](../standard-library/tuple-size-class-utility.md)|Класс, который заключает в оболочку счетчик элементов `pair`.|  
  
### Функции  
  
|||  
|-|-|  
|[forward](../Topic/forward.md)|Не позволяет изменить ссылочный тип \(`lvalue` или `rvalue`\) аргумента при точной пересылке.|  
|[get](../Topic/get%20Function%20%3Cutility%3E.md)|Функция, которая возвращает элемент из объекта `pair`.|  
|[make\_pair](../Topic/make_pair.md)|Вспомогательная функция шаблона, которую можно использовать для построения объектов типа `pair` на основе типов данных, переданных в качестве параметров.|  
|[переместить](../Topic/move.md)|Возвращает переданный аргумент в виде ссылки `rvalue`.|  
|[swap](../Topic/swap%20\(%3Cutility%3E\).md)|Меняет местами элементы двух объектов `pair`.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Cutility%3E\).md)|Проверяет неравенство объекта pair слева от оператора объекту pair справа от оператора.|  
|[operator\=\=](../Topic/operator==%20\(%3Cutility%3E\).md)|Проверяет равенство объекта pair слева от оператора объекту pair справа от оператора.|  
|[Оператор \<](../Topic/operator%3C%20\(%3Cutility%3E\).md)|Проверяет, меньше ли объект pair слева от оператора объекта pair справа от оператора.|  
|[Оператор \<\=](../Topic/operator%3C=%20\(%3Cutility%3E\).md)|Проверяет, что объект pair слева от оператора меньше или равен объекту pair справа от оператора.|  
|[Оператор \>](../Topic/operator%3E%20\(%3Cutility%3E\).md)|Проверяет, больше ли объект pair слева от оператора объекта pair справа от оператора.|  
|[Оператор \>\=](../Topic/operator%3E=%20\(%3Cutility%3E\).md)|Проверяет, что объект pair слева от оператора больше или равен объекту pair справа от оператора.|  
  
### Структуры  
  
|||  
|-|-|  
|[удостоверение](../Topic/identity%20Structure.md)||  
|[pair](../standard-library/pair-structure.md)|Тип, позволяющий обрабатывать два объекта как один объект.|  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)