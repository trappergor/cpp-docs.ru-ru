---
title: "&lt; streambuf &gt; | Microsoft Docs"
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
  - "std::<streambuf>"
  - "<streambuf>"
  - "streambuf/std::<streambuf>"
  - "std.<streambuf>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "streambuf - заголовок"
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; streambuf &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Добавьте стандартный заголовок iostreams \<streambuf\>, чтобы определить класс шаблона [basic\_streambuf](../standard-library/basic-streambuf-class.md), которой является базовым для операций классов iostreams. Этот заголовок обычно включается автоматически при использовании других заголовков потоков ввода\-вывода \(iostream\). Его редко приходится включать напрямую.  
  
## Синтаксис  
  
```  
  
#include <streambuf>  
  
```  
  
### Typedefs  
  
|||  
|-|-|  
|[streambuf](../Topic/streambuf.md)|Специализация `basic_streambuf`, использующая `char` в качестве параметров шаблона.|  
|[wstreambuf](../Topic/wstreambuf.md)|Специализация `basic_streambuf`, использующая `wchar_t` в качестве параметров шаблона.|  
  
### Классы  
  
|||  
|-|-|  
|[Класс basic\_streambuf](http://msdn.microsoft.com/ru-ru/d9c706ba-ce01-43e0-b0b2-a558fc53ea8d)|Этот класс шаблона описывает абстрактный базовый класс для получения буфера потока, который управляет передачей элементов в определенное представление потока и из него.|  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)