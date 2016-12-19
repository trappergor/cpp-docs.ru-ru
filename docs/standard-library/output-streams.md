---
title: "Потоки вывода | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "потоки вывода"
ms.assetid: b49410e3-5caa-4153-9d0d-c4266408dc83
caps.latest.revision: 12
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Потоки вывода
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Объект потока вывода назначение для байтов.  3 Наиболее важных классов потока вывода `ostream`, `ofstream` и `ostringstream`.  
  
 Класс `ostream`, через производный класс `basic_ostream`, поддерживает предварительно определенные объекты потока:  
  
-   стандартный вывод `cout`  
  
-   ошибка `cerr` стандартная с ограниченной буферизацией  
  
-   `clog` аналогична `cerr`, но с полной буферизацией  
  
 Объекты редко создаются из `ostream`; предопределенные объекты обычно используются.  В некоторых случаях можно повторно назначить предопределенные объекты после запуска программы.  Класс `ostream`, который можно настроить для помещенной в буфер или небуферизованного операции, наилучшим образом подходит к последовательному вывод текст\- режима.  Всю функциональность базового класса, `ios`, включена в `ostream`.  При создании объекта класса `ostream`, необходимо указать объект `streambuf` в конструктор.  
  
 Класс `ofstream` поддерживает вывод дискового файла.  Если требуется только выходные параметры диск, создайте объект класса `ofstream`.  Можно указать принимают ли объекты `ofstream` бинарный или данных текст\- режима при построении объекта `ofstream` или при вызове функции\-члена `open` объекта.  Многие параметры форматирования и функции\-члены применяются к `ofstream` объекты, и все функциональные возможности базовых классов `ios` и `ostream` включена.  
  
 Если указано имя файла в конструкторе, этот файл автоматически открывается при построении объекта.  В противном случае можно воспользоваться функцией\-членом класса `open` после вызова конструктора по умолчанию.  
  
 Как и функция времени выполнения `sprintf_s`, класс `ostringstream` поддерживает вывод в строки в памяти.  Для создания строки в памяти с помощью форматирования потока ВВОДА\-ВЫВОДА, создайте объект класса `ostringstream`.  
  
## Содержание  
 [Построение объектов потока вывода](../Topic/Constructing%20Output%20Stream%20Objects.md)  
  
 [Использование операторов вставки и управление форматом](../standard-library/using-insertion-operators-and-controlling-format.md)  
  
 [Функции\-члены потока выходного файла](../standard-library/output-file-stream-member-functions.md)  
  
 [Эффекты буферизации](../standard-library/effects-of-buffering.md)  
  
 [Двоичные выходные файлы](../standard-library/binary-output-files.md)  
  
 [Перегрузка оператора \<\< для собственных классов](../Topic/Overloading%20the%20%3C%3C%20Operator%20for%20Your%20Own%20Classes.md)  
  
 [Создание собственных манипуляторов без аргументов](../standard-library/writing-your-own-manipulators-without-arguments.md)  
  
## См. также  
 [члены\<ostream\>](http://msdn.microsoft.com/ru-ru/a5afd034-0e3c-41ee-bbd7-468d9188da1d)   
 [ofstream](../Topic/ofstream.md)   
 [ostringstream](../Topic/ostringstream.md)   
 [члены basic\_ostream](http://msdn.microsoft.com/ru-ru/82e5cc91-7c0c-4950-a8ce-ac779cfbbd93)   
 [Программирование iostream](../Topic/iostream%20Programming.md)