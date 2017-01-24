---
title: "Класс recursive_timed_mutex | Microsoft Docs"
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
  - "mutex/std::recursive_timed_mutex"
dev_langs: 
  - "C++"
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
caps.latest.revision: 9
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс recursive_timed_mutex
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет *синхронизированный тип мьютексов*.  Объекты этого типа используются для обеспечения взаимное исключение с помощью времени ограниченной блокировки внутри программы.  В отличие от объектов типа [timed\_mutex](../standard-library/timed-mutex-class.md), эффект блокирован вызывать методы для объектов `recursive_timed_mutex` чёток.  
  
## Синтаксис  
  
```  
class recursive_timed_mutex;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор recursive\_timed\_mutex::recursive\_timed\_mutex](../Topic/recursive_timed_mutex::recursive_timed_mutex%20Constructor.md)|Создает объект `recursive_timed_mutex`, не блокирован.|  
|[Деструктор recursive\_timed\_mutex::~recursive\_timed\_mutex](../Topic/recursive_timed_mutex::~recursive_timed_mutex%20Destructor.md)|Выпуски все ресурсы, используемые объектом `recursive_timed_mutex`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод recursive\_timed\_mutex::lock](../Topic/recursive_timed_mutex::lock%20Method.md)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.|  
|[Метод recursive\_timed\_mutex::try\_lock](../Topic/recursive_timed_mutex::try_lock%20Method.md)|Попытки получить права владельца объекта `mutex` без блокировки.|  
|[Метод recursive\_timed\_mutex::try\_lock\_for](../Topic/recursive_timed_mutex::try_lock_for%20Method.md)|Попытки доступа к владельца `mutex` для указанного временного интервала.|  
|[Метод recursive\_timed\_mutex::try\_lock\_until](../Topic/recursive_timed_mutex::try_lock_until%20Method.md)|Не будет пытать получения владения `mutex` до указанного времени.|  
|[Метод recursive\_timed\_mutex::unlock](../Topic/recursive_timed_mutex::unlock%20Method.md)|Освобождает права владения объектом `mutex`.|  
  
## Требования  
 **Заголовок:** mutex  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)