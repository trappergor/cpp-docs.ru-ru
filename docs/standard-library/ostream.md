---
title: "&lt;ostream&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<ostream>"
  - "<ostream>"
  - "ostream/std::<ostream>"
  - "std::<ostream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostream - заголовок"
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt;ostream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет класс шаблона [basic\_ostream](../Topic/basic_ostream%20Class.md), который является посредником при вставке для iostreams.  Заголовок также определяет несколько связанных манипуляторов.  \(Этот заголовок обычно включается автоматически при использовании других заголовков iostream.  Его редко приходится включать напрямую.\)  
  
## Синтаксис  
  
```  
  
#include <ostream>  
  
```  
  
### Typedefs  
  
|||  
|-|-|  
|[ostream](../Topic/ostream.md)|Создает тип из `basic_ostream`, который специализируется на `char`, и `char_traits`, который специализируется на `char`.|  
|[wostream](../Topic/wostream.md)|Создает тип из `basic_ostream`, который специализируется на `wchar_t`, и `char_traits`, который специализируется на `wchar_t`.|  
  
### Манипуляторы  
  
|||  
|-|-|  
|[endl](../Topic/endl.md)|Завершает строку и очищает буфер.|  
|[концы](../Topic/ends%20\(Standard%20C++%20Library\).md)|Завершает строку.|  
|[flush](../Topic/flush%20\(Standard%20C++%20Library\).md)|Очищает буфер.|  
||Меняет местами значения левого параметра объекта `basic_ostream` со значениями правого параметра объекта `basic_ostream`.|  
  
### Операторы  
  
|||  
|-|-|  
|[\<\< \- оператор](../Topic/operator%3C%3C%20\(%3Costream%3E\).md)|Записывает в поток различные типы.|  
  
### Классы  
  
|||  
|-|-|  
|[basic\_ostream](../Topic/basic_ostream%20Class.md)|Класс шаблона, который описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока.|  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)