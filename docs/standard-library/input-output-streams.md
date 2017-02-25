---
title: "Потоки ввода/вывода | Microsoft Docs"
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
  - "ввод-вывод [C++], поток"
  - "потоковый ввод-вывод"
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Потоки ввода/вывода
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`basic_iostream`, который определен в файле заголовка \<istream\>, шаблон класса для объектов, которые обрабатывают оба потока ВВОДА\-ВЫВОДА ввода и вывода символьно\-ориентированных.  
  
 2 Typedef, определяющие специализации символ\- для `basic_iostream` и могут помочь сделать код более удобным для чтения. `iostream` \(не путать с файлом \<iostream\>заголовка\) поток ВВОДА\-ВЫВОДА на основе `basic_iostream<char>`; `wiostream` поток ВВОДА\-ВЫВОДА на основе `basic_iostream<wchar_t>`.  
  
 Дополнительные сведения см. в разделах [Класс basic\_iostream](../standard-library/basic-iostream-class.md), [iostream](../Topic/iostream.md) и [wiostream](../Topic/wiostream.md).  
  
 Наследование от `basic_iostream` шаблон класса `basic_fstream`, используемый к символьным данным потока и наоборот файлов.  
  
 Также typedef, предоставляющие специализации символ\- для `basic_fstream`.  Они `fstream`, поток файлового ввода\-вывода на основе `char` и `wfstream`, поток файлового ввода\-вывода на основе `wchar_t`.  Дополнительные сведения см. в разделах [Класс basic\_fstream](../standard-library/basic-fstream-class.md), [fstream](../Topic/fstream.md) и [wfstream](../Topic/wfstream.md).  С помощью этих typedef требует включения файла заголовка \<fstream\>.  
  
> [!NOTE]
>  Если объект `basic_fstream` используется для выполнения вводом\-выводом, хотя основной буфер содержит отдельные; позиции для чтения и записи, текущие позиции ввода и текущего уровня производства связаны друг с другом, поэтому при чтении перемещение некоторых данных позиция вывода.  
  
 Шаблон класса `basic_stringstream` и его общая специализация, `stringstream`, часто используются для работы с объектами потока ВВОДА\-ВЫВОДА вставки и извлечь символьные данные.  Для получения дополнительной информации см. [Класс basic\_stringstream](../standard-library/basic-stringstream-class.md).  
  
## См. также  
 [stringstream](../Topic/stringstream.md)   
 [Класс basic\_stringstream](../standard-library/basic-stringstream-class.md)   
 [\<sstream\>](../standard-library/sstream.md)   
 [Программирование iostream](../Topic/iostream%20Programming.md)   
 [Стандартная библиотека C\+\+](../standard-library/cpp-standard-library-reference.md)