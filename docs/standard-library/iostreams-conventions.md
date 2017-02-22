---
title: "Соглашения iostreams | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iostream - заголовок"
  - "Стандартная библиотека C++, iostreams"
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Соглашения iostreams
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Заголовки iostreams поддерживают преобразование между текстом и кодированными формами и ввод и вывод к внешним файлам.  
  
|||  
|-|-|  
|[\<fstream\>](../standard-library/fstream.md)|[\< iomanip \>](../Topic/%3Ciomanip%3E.md)|  
|[\<ios\>](../standard-library/ios.md)|[\<iosfwd\>](../standard-library/iosfwd.md)|  
|[\<iostream\>](../standard-library/iostream.md)|[\< istream \>](../standard-library/istream.md)|  
|[\<ostream\>](../standard-library/ostream.md)|[\<sstream\>](../standard-library/sstream.md)|  
|[\< streambuf \>](../standard-library/streambuf.md)|[\<strstream\>](../standard-library/strstream.md)|  
  
 Самым простым iostreams требуется использовать только о включении заголовок [\<iostream\>](../standard-library/iostream.md).  Затем можно извлекать значения из [cin](../Topic/cin.md) или [wcin](../Topic/wcin.md) для чтения стандартный входных данных.  Правила методика описанных в описании класса [Класс basic\_istream](../Topic/basic_istream%20Class.md).  Можно также вставлять значения для [cout](../Topic/cout.md) или [wcout](../Topic/wcout.md) для записи стандартный вывод.  Правила методика описанных в описании класса [Класс basic\_ostream](../Topic/basic_ostream%20Class.md).  Элемент управления формата общие для обоих экстракторам и insertors является управляемым классом [Класс basic\_ios](../Topic/basic_ios%20Class.md).  Управление эти сведения о формате под маской извлечение и вставка нескольких объектов провинция манипуляторов.  
  
 Можно выполнять те же операции iostreams на файлах, открытии по имени с использованием классов, объявленные в [\<fstream\>](../standard-library/fstream.md).  Для преобразования iostreams и объектов класса [Класс basic\_string](../standard-library/basic-string-class.md), используйте классы, объявленные в [\<sstream\>](../standard-library/sstream.md).  Задача совпадают со строками C, использует классы, объявленные в [\<strstream\>](../standard-library/strstream.md).  
  
 Оставшиеся заголовки предоставляют стоимость, обычно непосредственно нужны только опытные пользователи классов iostreams.  
  
## См. также  
 [Обзор STL](../standard-library/cpp-standard-library-overview.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)