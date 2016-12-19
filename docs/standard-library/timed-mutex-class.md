---
title: "Класс timed_mutex | Microsoft Docs"
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
  - "mutex/std::timed_mutex"
dev_langs: 
  - "C++"
ms.assetid: cd198081-6f38-447a-9dba-e06dfbfafe59
caps.latest.revision: 9
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс timed_mutex
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет *синхронизированный тип мьютексов*.  Объекты этого типа используются для обеспечения взаимное исключение по времени ограниченную блокировку в течение программы.  
  
## Синтаксис  
  
```  
class timed_mutex;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор timed\_mutex::timed\_mutex](../Topic/timed_mutex::timed_mutex%20Constructor.md)|Создает объект `timed_mutex`, не блокирован.|  
|[Деструктор timed\_mutex::~timed\_mutex](../Topic/timed_mutex::~timed_mutex%20Destructor.md)|Выпуски все ресурсы, используемые объектом `timed_mutex`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод timed\_mutex::lock](../Topic/timed_mutex::lock%20Method.md)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.|  
|[Метод timed\_mutex::try\_lock](../Topic/timed_mutex::try_lock%20Method.md)|Попытки получить права владельца объекта `mutex` без блокировки.|  
|[Метод timed\_mutex::try\_lock\_for](../Topic/timed_mutex::try_lock_for%20Method.md)|Попытки доступа к владельца `mutex` для указанного временного интервала.|  
|[Метод timed\_mutex::try\_lock\_until](../Topic/timed_mutex::try_lock_until%20Method.md)|Не будет пытать получения владения `mutex` до указанного времени.|  
|[Метод timed\_mutex::unlock](../Topic/timed_mutex::unlock%20Method.md)|Освобождает права владения объектом `mutex`.|  
  
## Требования  
 **Заголовок:** mutex  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)