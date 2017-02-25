---
title: "Класс lock_guard | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mutex/std::lock_guard"
dev_langs: 
  - "C++"
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Класс lock_guard
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет шаблон, можно создать для создания объекта деструктор которого пропустить `mutex`.  
  
## Синтаксис  
  
```  
template<class Mutex>  
class lock_guard;  
```  
  
## Заметки  
 Аргумент `Mutex` шаблона должен иметь имя *тип мьютексов*.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Name|Описание|  
|----------|--------------|  
|`lock_guard::mutex_type`|Синоним для аргумента `Mutex` шаблона.|  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор lock\_guard::lock\_guard](../Topic/lock_guard::lock_guard%20Constructor.md)|Создает объект `lock_guard`.|  
|[Деструктор lock\_guard::~lock\_guard](../Topic/lock_guard::~lock_guard%20Destructor.md)|Удаление `mutex`, которое было передаватьсяо в конструктор.|  
  
## Требования  
 **Заголовок:** mutex  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)