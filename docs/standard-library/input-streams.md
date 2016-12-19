---
title: "Потоки ввода | Microsoft Docs"
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
  - "данные [C++], чтение из входящего потока"
  - "объекты потока ввода"
  - "потоки ввода"
  - "чтение данных [C++], из входящих потоков"
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
caps.latest.revision: 11
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Потоки ввода
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Объект входного потока байтов источника.  3 Наиболее важных классах входного потока [istream](http://msdn.microsoft.com/ru-ru/6801779e-260e-416d-b4ec-fef5ff1b2371), [ifstream](../Topic/ifstream.md) и [istringstream](../Topic/istringstream.md).  
  
 Класс `istream` наилучшим образом используется для последовательного ввода текст\- режима.  Можно настроить объекты класса `istream` для помещенной в буфер или небуферизованного операции.  Всю функциональность базового класса, `ios`, включена в `istream`.  Иногда необходимо будет строить объекты из класса `istream`.  Вместо этого обычно используются предопределенный объект `cin`, фактически объект класса [ostream](../standard-library/ostream.md).  В некоторых случаях можно присвоить `cin` на другие объекты потока после запуска программы.  
  
 Класс `ifstream` поддерживает ввод дискового файла.  Если требуется только для ввода дисковый файл, создайте объект класса `ifstream`.  Можно указать бинарный или данных текст\- режима.  Если указано имя файла в конструкторе, файл автоматически открывается при построении объекта.  В противном случае можно использовать функцию `open` после вызова конструктора по умолчанию.  Многие параметры форматирования и функции\-члены применяются к `ifstream` объекты.  Все функциональные возможности базовых классов `ios` и `istream` включена в `ifstream`.  
  
 Подобно функции библиотеки `sscanf_s`, класс `istringstream` поддерживает входные данные от строк в памяти.  Для извлечения данных из массива символов имеет значение NULL терминатор выделите и инициализация строки, а затем создайте объект класса `istringstream`.  
  
## Содержание  
 [Построение объектов потока ввода](../Topic/Constructing%20Input%20Stream%20Objects.md)  
  
 [Использование операторов извлечения](../Topic/Using%20Extraction%20Operators.md)  
  
 [Проверка на наличие ошибок извлечения](../standard-library/testing-for-extraction-errors.md)  
  
 [Манипуляторы входных потоков](../standard-library/input-stream-manipulators.md)  
  
 [Функции\-члены потока ввода](../standard-library/input-stream-member-functions.md)  
  
 [Перегрузка оператора \>\> для собственных классов](../standard-library/overloading-the-input-operator-for-your-own-classes.md)  
  
## См. также  
 [Программирование iostream](../Topic/iostream%20Programming.md)