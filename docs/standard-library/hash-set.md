---
title: "&lt;hash_set&gt; | Microsoft Docs"
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
  - "<hash_set>"
  - "std.<hash_set>"
  - "std::<hash_set>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_set - заголовок"
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: 22
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;hash_set&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Этот заголовок устарел. Вместо него следует использовать [\<unordered\_set\>](../standard-library/unordered-set.md).  
  
 Определяет контейнер шаблонных классов hash\_set и hash\_multiset и их поддерживаемые шаблоны.  
  
## Синтаксис  
  
```  
  
#include <hash_set>  
  
```  
  
## Заметки  
 В Visual C\+\+ .NET 2003 члены файлов заголовков [\<hash\_map\>](../standard-library/hash-map.md) и [\<hash\_set\>](#vclrfhash_set_header_file) больше не находятся в пространстве имен std. Они перемещены в пространство имен stdext. Дополнительные сведения см. в разделе [Пространство имен stdext](../Topic/stdext%20Namespace.md).  
  
### Операторы  
  
|Версия hash\_set|Версия hash\_multiset|Описание|  
|----------------------|---------------------------|--------------|  
|[operator\!\= \(hash\_set\)](../Topic/operator!=%20\(hash_set\).md)|[operator\!\= \(hash\_multiset\)](../Topic/operator!=%20\(hash_multiset\).md)|Проверяет неравенство объекта hash\_set или hash\_multiset слева от оператора объекту hash\_set или hash\_multiset справа от оператора.|  
|[operator\=\= \(hash\_set\)](http://msdn.microsoft.com/ru-ru/791b95bd-f917-4716-aea6-add50badbfac)|[operator\=\= \(hash\_multiset\)](http://msdn.microsoft.com/ru-ru/cfa9aa0c-d5f6-403a-9441-35c2a4cee0fb)|Проверяет равенство объекта hash\_set или hash\_multiset слева от оператора объекту hash\_set или hash\_multiset справа от оператора.|  
  
### Специализированные функции шаблонов  
  
|Версия hash\_set|Версия hash\_multiset|Описание|  
|----------------------|---------------------------|--------------|  
|[swap \(hash\_set\)](../Topic/swap%20\(hash_set\).md)|[swap \(hash\_multiset\)](../Topic/swap%20\(hash_multiset\).md)|Меняет местами элементы двух объектов hash\_set или hash\_multiset.|  
  
### Классы  
  
|||  
|-|-|  
|[Класс hash\_compare](../standard-library/hash-compare-class.md)|Описывает объект, который может использоваться любыми hash\-ассоциативными контейнерами \(hash\_map, hash\_multimap, hash\_set или hash\_multiset\) как объект параметра **Traits** по умолчанию для сортировки и хэширования элементов в них.|  
|[Класс hash\_set](../standard-library/hash-set-class.md)|Используется для хранения и быстрого извлечения данных из коллекции, в которой значения элементов должны быть уникальными и в которой они служат в качестве значений ключей.|  
|[Класс hash\_multiset](../Topic/hash_multiset%20Class.md)|Используется для хранения и быстрого извлечения данных из коллекции, в которой значения элементов должны быть уникальными и в которой они служат в качестве значений ключей.|  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)