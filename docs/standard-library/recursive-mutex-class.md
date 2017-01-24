---
title: "Класс recursive_mutex | Microsoft Docs"
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
  - "mutex/std::recursive_mutex"
dev_langs: 
  - "C++"
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
caps.latest.revision: 9
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс recursive_mutex
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет *тип мьютексов*.  В отличие от [мьютексы](../standard-library/mutex-class-stl.md), расширения функциональности вызовов блокировать методы для объектов, которые уже блокированы четко.  
  
## Синтаксис  
  
```  
class recursive_mutex;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор recursive\_mutex::recursive\_mutex](../Topic/recursive_mutex::recursive_mutex%20Constructor.md)|Создает объект `recursive_mutex`.|  
|[Деструктор recursive\_mutex::~recursive\_mutex](../Topic/recursive_mutex::~recursive_mutex%20Destructor.md)|Выпуски все ресурсы, используемые объектом `recursive_mutex`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод recursive\_mutex::lock](../Topic/recursive_mutex::lock%20Method.md)|Блокирует вызывающий поток до тех пор, пока поток не получит владение мьютекса.|  
|[Метод recursive\_mutex::try\_lock](../Topic/recursive_mutex::try_lock%20Method.md)|Пытается получить мьютекс владения без блокировки.|  
|[Метод recursive\_mutex::unlock](../Topic/recursive_mutex::unlock%20Method.md)|Владение выпусков мьютекса.|  
  
## Требования  
 **Заголовок:** mutex  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)