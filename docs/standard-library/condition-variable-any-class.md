---
title: "Класс condition_variable_any | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "condition_variable/std::condition_variable_any"
dev_langs: 
  - "C++"
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Класс condition_variable_any
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Используйте класс `condition_variable_any`, чтобы ожидать событие с любой тип `mutex`.  
  
## Синтаксис  
  
```  
class condition_variable_any;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор condition\_variable\_any::condition\_variable\_any](../Topic/condition_variable_any::condition_variable_any%20Constructor.md)|Создает объект `condition_variable_any`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод condition\_variable\_any::notify\_all](../Topic/condition_variable_any::notify_all%20Method.md)|Разблокирует все потоки, ожидающие объект `condition_variable_any`.|  
|[Метод condition\_variable\_any::notify\_one](../Topic/condition_variable_any::notify_one%20Method.md)|Разблокирует один из потоков, ожидающие объект `condition_variable_any`.|  
|[Метод condition\_variable\_any::wait](../Topic/condition_variable_any::wait%20Method.md)|Блокирует поток.|  
|[Метод condition\_variable\_any::wait\_for](../Topic/condition_variable_any::wait_for%20Method.md)|Блокирующий поток, и задает интервал времени, после которого поток разблокирует.|  
|[Метод condition\_variable\_any::wait\_until](../Topic/condition_variable_any::wait_until%20Method.md)|Блокирующий поток, и задает максимальный момент времени, в которой поток разблокирует.|  
  
## Требования  
 **Заголовок:**  condition\_variable  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<condition\_variable\>](../standard-library/condition-variable.md)