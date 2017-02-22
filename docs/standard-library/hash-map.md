---
title: "&lt;hash_map&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<hash_map>"
  - "<hash_map>"
  - "std::<hash_map>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_map - заголовок"
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# &lt;hash_map&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Этот заголовок устарел. Вместо него следует использовать [\<unordered\_map\>](../standard-library/unordered-map.md).  
  
 Определяет контейнер шаблонных классов hash\_map и hash\_multimap и их поддерживаемые шаблоны.  
  
 В Visual C\+\+ .NET 2003 члены файлов заголовков [\<hash\_map\>](#vclrfhash_map_header_file) и [\<hash\_set\>](../standard-library/hash-set.md) больше не находятся в пространстве имен std. Они перемещены в пространство имен stdext. Дополнительные сведения см. в разделе [Пространство имен stdext](../Topic/stdext%20Namespace.md).  
  
## Синтаксис  
  
```  
  
#include <hash_map>  
  
```  
  
### Операторы  
  
|Версия hash\_map|Версия hash\_multimap|Описание|  
|----------------------|---------------------------|--------------|  
|[operator\!\= \(hash\_map\)](../Topic/operator!=%20\(hash_map\).md)|[operator\!\= \(hash\_multimap\)](../Topic/operator!=%20\(hash_multimap\).md)|Проверяет неравенство объекта hash\_map или hash\_multimap слева от оператора объекту hash\_map или hash\_multimap справа от оператора.|  
|[operator\=\= \(hash\_map\)](http://msdn.microsoft.com/ru-ru/f933cb1c-934d-43f5-aa9e-0b325eb95b85)|[operator\=\= \(hash\_multimap\)](http://msdn.microsoft.com/ru-ru/3fa378b1-0250-4e3f-a130-dc14103fc5e9)|Проверяет равенство объекта hash\_map или hash\_multimap слева от оператора объекту hash\_map или hash\_multimap справа от оператора.|  
  
### Специализированные функции шаблонов  
  
|Версия hash\_map|Версия hash\_multimap|Описание|  
|----------------------|---------------------------|--------------|  
|[swap \(hash\_map\)](../Topic/hash_map::swap.md)|[swap \(hash\_multimap\)](../Topic/hash_multimap::swap.md)|Меняет местами элементы двух объектов hash\_map или hash\_multimap.|  
  
### Классы  
  
|||  
|-|-|  
|[Класс hash\_compare](../standard-library/hash-compare-class.md)|Описывает объект, который может использоваться любыми hash\-ассоциативными контейнерами \(hash\_map, hash\_multimap, hash\_set или hash\_multiset\) как объект параметра **Traits** по умолчанию для сортировки и хэширования элементов в них.|  
|[Класс value\_compare](../Topic/value_compare%20Class.md)|Предоставляет объект функции, который может сравнивать элементы hash\_map путем сравнения значения ключей для определения относительного порядка в hash\_map.|  
|[Класс hash\_map](../standard-library/hash-map-class.md)|Используется для хранения и быстрого считывания данных из коллекции, в которой каждый элемент — это пара, которая имеет отсортированный уникальный ключ и связанное с ним значение.|  
|[Класс hash\_multimap](../standard-library/hash-multimap-class.md)|Используется для хранения и быстрого считывания данных из коллекции, в которой каждый элемент — это пара, которая имеет ключ, значение которого не должно быть уникальным, и связанное с ним значение.|  
  
## Требования  
 **Заголовок:** \<hash\_map\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)