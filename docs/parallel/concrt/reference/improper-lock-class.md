---
title: "Класс improper_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::improper_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_lock - класс"
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс improper_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, которое выдается, когда блокировка получена неправильно.  
  
## Синтаксис  
  
```  
class improper_lock : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор improper\_lock::improper\_lock](../Topic/improper_lock::improper_lock%20Constructor.md)|Перегружен.  Создает `improper_lock exception`.|  
  
## Заметки  
 Как правило это исключение возникает при попытке получить не реентрантную блокировку рекурсивно на том же контексте.  
  
## Иерархия наследования  
 `exception`  
  
 `improper_lock`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс critical\_section](../../../parallel/concrt/reference/critical-section-class.md)   
 [Класс reader\_writer\_lock](../Topic/reader_writer_lock%20Class.md)