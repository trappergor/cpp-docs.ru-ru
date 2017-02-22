---
title: "Класс condition_variable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "condition_variable/std::condition_variable"
dev_langs: 
  - "C++"
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Класс condition_variable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Используйте класс `condition_variable`, чтобы ожидать событие при наличии `mutex` типа `unique_lock<mutex>`.  Объекты этого типа могут иметь лучшую производительность, чем объекты типа [condition\_variable\_any\<unique\_lock\<мьютексы\>\>](../standard-library/condition-variable-any-class.md).  
  
## Синтаксис  
  
```  
class condition_variable;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор condition\_variable::condition\_variable](../Topic/condition_variable::condition_variable%20Constructor.md)|Создает объект `condition_variable`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод condition\_variable::native\_handle](../Topic/condition_variable::native_handle%20Method.md)|Возвращает тип для предоставления, condition\_variable дескриптора.|  
|[Метод condition\_variable::notify\_all](../Topic/condition_variable::notify_all%20Method.md)|Разблокирует все потоки, ожидающие объект `condition_variable`.|  
|[Метод condition\_variable::notify\_one](../Topic/condition_variable::notify_one%20Method.md)|Разблокирует один из потоков, ожидающие объект `condition_variable`.|  
|[Метод condition\_variable::wait](../Topic/condition_variable::wait%20Method.md)|Блокирует поток.|  
|[Метод condition\_variable::wait\_for](../Topic/condition_variable::wait_for%20Method.md)|Блокирующий поток, и задает интервал времени, после которого поток разблокирует.|  
|[Метод condition\_variable::wait\_until](../Topic/condition_variable::wait_until%20Method.md)|Блокирующий поток, и задает максимальный момент времени, в которой поток разблокирует.|  
  
## Требования  
 **Заголовок:**  condition\_variable  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<condition\_variable\>](../standard-library/condition-variable.md)