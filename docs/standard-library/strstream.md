---
title: "&lt;strstream&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<strstream>"
  - "std::<strstream>"
  - "<strstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstream - заголовок"
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt;strstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет несколько классов, поддерживающих операции iostreams для  последовательностей, хранящихся в выделенном массиве объекта `char`.  Такие последовательности легко преобразуются в строки C и обратно.  
  
## Синтаксис  
  
```  
  
#include <strstream>  
  
```  
  
## Заметки  
 Объекты типа `strstream` работают с `char` \*, которые являются строками C.  Используйте [\< sstream \>](../standard-library/sstream.md) для работы с объектами типа [basic\_string](../standard-library/basic-string-class.md).  
  
> [!NOTE]
>  Классы в `<strstream>` считаются устаревшими.  Рекомендуется использовать вместо них классы в `<sstream>`.  
  
### Классы  
  
|||  
|-|-|  
|[Класс strstreambuf](../standard-library/strstreambuf-class.md)|Этот класс описывает буфер потока, который управляет передачей элементов из последовательности элементов, содержащейся в объекте массива `char`, и в эту последовательность.|  
|[Класс istrstream](../standard-library/istrstream-class.md)|Этот класс описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).|  
|[Класс ostrstream](../Topic/ostrstream%20Class.md)|Этот класс описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [strstreambuf](../standard-library/strstreambuf-class.md).|  
|[Класс strstream](../standard-library/strstream-class.md)|Этот класс описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).|  
  
## См. также  
 [\<strstream\>](../standard-library/strstream.md)   
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)