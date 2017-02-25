---
title: "&lt;set&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<set>"
  - "std::<set>"
  - "<set>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "set - заголовок"
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt;set&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет классы шаблонов контейнеров set и multiset и их вспомогательные шаблоны.  
  
## Синтаксис  
  
```  
  
#include <set>  
  
```  
  
## Участники  
  
### Операторы  
  
|Версия Set|Версия Multiset|Описание|  
|----------------|---------------------|--------------|  
|[operator\!\= \(set\)](../Topic/operator!=%20\(set\).md)|[operator\!\= \(multiset\)](../Topic/operator!=%20\(multiset\).md)|Проверяет неравенство объекта set или multiset слева от оператора объекту set или multiset справа от оператора.|  
|[operator\< \(set\)](../Topic/operator%3C%20\(set\).md)|[operator\< \(multiset\)](../Topic/operator%3C%20\(multiset\).md)|Проверяет, меньше ли объект set или multiset слева от оператора объекта set или multiset справа от оператора.|  
|[operator\<\= \(set\)](../Topic/operator%3C=%20\(set\).md)|[operator\<\= \(multiset\)](../Topic/operator%3C=%20\(multiset\).md)|Проверяет, меньше или равен ли объект set или multiset слева от оператора объекту set или multiset справа от оператора.|  
|[operator\=\= \(set\)](../Topic/operator==%20\(set\).md)|[operator\=\= \(multiset\)](../Topic/operator==%20\(multiset\).md)|Проверяет равенство объекта set или multiset слева от оператора объекту set или multiset справа от оператора.|  
|[operator\> \(set\)](../Topic/operator%3E%20\(set\).md)|[operator\> \(multiset\)](../Topic/operator%3E%20\(multiset\).md)|Проверяет, больше ли объект set или multiset слева от оператора объекта set или multiset справа от оператора.|  
|[operator\>\= \(set\)](../Topic/operator%3E=%20\(set\).md)|[operator\>\= \(multiset\)](../Topic/operator%3E=%20\(multiset\).md)|Проверяет, больше или равен ли объект set или multiset слева от оператора объекту set или multiset справа от оператора.|  
  
### Специализированные функции шаблонов  
  
|Версия Set|Версия Multiset|Описание|  
|----------------|---------------------|--------------|  
|[swap \(set\)](../Topic/swap%20\(set\).md)|[swap \(multiset\)](../Topic/swap%20\(multiset\).md)|Меняет местами элементы двух объектов set или multiset.|  
  
### Классы  
  
|||  
|-|-|  
|[Класс set](../standard-library/set-class.md)|Используется для хранения и извлечения данных из коллекции, в которой значения элементов должны быть уникальными и в которой они служат в качестве значений ключей, согласно которым данные автоматически упорядочиваются.|  
|[Класс multiset](../Topic/multiset%20Class.md)|Используется для хранения и извлечения данных из коллекции, в которой значения элементов не должны быть уникальными и в которой они служат в качестве значений ключей, согласно которым данные автоматически упорядочиваются.|  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)