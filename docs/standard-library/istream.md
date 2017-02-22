---
title: "&lt; istream &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "istream/std::<istream>"
  - "std.<istream>"
  - "<istream>"
  - "std::<istream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istream - заголовок"
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt; istream &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет класс шаблона basic\_istream, отвечающий за извлечение для iostreams, и класс шаблона basic\_iostream, отвечающий за вставку и извлечение. Заголовок также определяет связанный манипулятор. Этот файл заголовок обычно автоматически включается другим заголовком iostreams, его редко приходится включать напрямую.  
  
## Синтаксис  
  
```  
  
#include <istream>  
  
```  
  
### Typedefs  
  
|||  
|-|-|  
|[iostream](../Topic/iostream.md)|Тип `basic_iostream`, специализированный для `char`.|  
|[istream](../Topic/istream.md)|Тип `basic_istream`, специализированный для `char`.|  
|[wiostream](../Topic/wiostream.md)|Тип `basic_iostream`, специализированный для **wchar**.|  
|[wistream](../Topic/wistream.md)|Тип `basic_istream`, специализированный для **wchar**.|  
  
### Манипуляторы  
  
|||  
|-|-|  
|[ws](../Topic/ws.md)|Пропускает пробелы в потоке.|  
|[swap](../Topic/%3Cistream%3E%20swap.md)|Меняет местами два объекта потоков.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\>\>](../Topic/operator%3E%3E%20\(%3Cistream%3E\).md)|Извлекает символы и строки из потока.|  
  
### Классы  
  
|||  
|-|-|  
|[basic\_iostream](../standard-library/basic-iostream-class.md)|Класс потока, поддерживающий ввод и вывод.|  
|[basic\_istream](../Topic/basic_istream%20Class.md)|Класс шаблона описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока с элементами типа **Elem**, также известных как [char\_type](../Topic/basic_ios::char_type.md). Их признаки символов определяются классом **Tr** \([traits\_type](../Topic/basic_ios::traits_type.md)\).|  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)