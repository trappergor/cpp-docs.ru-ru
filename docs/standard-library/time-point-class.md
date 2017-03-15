---
title: "Класс time_point | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::time_point"
dev_langs: 
  - "C++"
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Класс time_point
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`time_point` описывает тип, который представляет момент времени.  Здесь содержится объект типа [длительность](../standard-library/duration-class.md), который хранит затраченное время, поскольку эпоха, которая представлена аргументом `Clock` шаблона.  
  
## Синтаксис  
  
```  
template<  
   class Clock,  
   class Duration = typename Clock::duration  
>  
class time_point;  
```  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Name|Описание|  
|----------|--------------|  
|`time_point::clock`|Синоним для параметра `Clock` шаблона.|  
|`time_point::duration`|Синоним для параметра `Duration` шаблона.|  
|`time_point::period`|Синоним для имени `duration::period` вложенных типов.|  
|`time_point::rep`|Синоним для имени `duration::rep` вложенных типов.|  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор time\_point::time\_point](../Topic/time_point::time_point%20Constructor.md)|Создает объект `time_point`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод time\_point::max](../Topic/time_point::max%20Method.md)|Указывает верхний предел для `time_point::ref`.|  
|[Метод time\_point::min](../Topic/time_point::min%20Method.md)|Определяет нижний предел для `time_point::ref`.|  
|[Метод time\_point::time\_since\_epoch](../Topic/time_point::time_since_epoch%20Method.md)|Возвращает сохраненный `duration` значение.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор time\_point::operator\+\=](../Topic/time_point::operator+=%20Operator.md)|Добавляет указанное значение на хранимый длительности.|  
|[Оператор time\_point::operator\-\=](../Topic/time_point::operator-=%20Operator.md)|Вычитает указанное значение из сохраненного длительности.|  
  
## Требования  
 **Заголовок:**  chrono  
  
 **Пространство имен:**  std::chrono  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)