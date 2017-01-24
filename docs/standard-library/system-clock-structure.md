---
title: "Структура system_clock | Microsoft Docs"
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
  - "chrono/std::chrono::system_clock"
dev_langs: 
  - "C++"
ms.assetid: a97bd46e-267a-4836-9f7d-af1f664e99ae
caps.latest.revision: 14
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Структура system_clock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет *тип clock*, использующий данные системных часов в реальном времени.  
  
## Синтаксис  
  
```  
struct system_clock;  
```  
  
## Заметки  
 *Тип clock* используется для получения текущего времени в формате UTC.  Этот тип реализует экземпляр класса [duration](../standard-library/duration-class.md) и шаблон класса [time\_point](../standard-library/time-point-class.md), а также определяет статическую функцию\-член `now()`, которая возвращает время.  
  
 Часы считаются *монотонными*, если значение, возвращаемое при первом вызове `now()`, всегда меньше или равно значениям, возвращаемым при последующих вызовах `now()`.  
  
 Часы считаются *постоянными*, если они *монотонны* и если интервал времени между соседними тактами является постоянной величиной.  
  
 В этой реализации `system_clock` является синонимом `high_resolution_clock`.  
  
## Участники  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`system_clock::duration`|Синоним для `duration<rep, period>`.|  
|`system_clock::period`|Синоним для типа, который используется для представления тактового периода при автономном создании экземпляра `duration`.|  
|`system_clock::rep`|Синоним для типа, который используется для представления числа тактов часов при автономном создании экземпляра `duration`.|  
|`system_clock::time_point`|Синоним для `time_point<Clock, duration>`, где `Clock` является синонимом для самого типа часов или для другого типа часов, настроенного на ту же эпоху и имеющего тот же вложенный тип `duration`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод system\_clock::from\_time\_t](../Topic/system_clock::from_time_t%20Method.md)|Статический.  Возвращает объект `time_point`, наиболее точно соответствующий указанному времени.|  
|[Метод system\_clock::now](../Topic/system_clock::now%20Method.md)|Статический.  Возвращает текущее время.|  
|[Метод system\_clock::to\_time\_t](../Topic/system_clock::to_time_t%20Method.md)|Статический.  Возвращает объект `time_t`, наиболее точно соответствующий указанному объекту `time_point`.|  
  
### Открытые константы  
  
|Имя|Описание|  
|---------|--------------|  
|[Константа system\_clock::is\_monotonic](../Topic/system_clock::is_monotonic%20Constant.md)|Указывает, являются ли часы монотонными.|  
|[Константа system\_clock::is\_steady](../Topic/system_clock::is_steady%20Constant.md)|Указывает, являются ли часы постоянными.|  
  
## Требования  
 **Заголовок:** chrono  
  
 **Пространство имен:** std::chrono  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)   
 [Структура steady\_clock](../Topic/steady_clock%20struct.md)