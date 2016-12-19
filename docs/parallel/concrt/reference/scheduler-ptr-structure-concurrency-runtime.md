---
title: "Структура scheduler_ptr (среда выполнения с параллелизмом) | Microsoft Docs"
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
  - "pplinterface/concurrency::scheduler_ptr"
dev_langs: 
  - "C++"
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
caps.latest.revision: 8
caps.handback.revision: 1
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура scheduler_ptr (среда выполнения с параллелизмом)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Представляет указатель на планировщик.  Этот класс существует для того, чтобы обеспечить возможность использования спецификации общего времени жизни путем применения shared\_ptr или простой ссылки с помощью необработанного указателя.  
  
## Синтаксис  
  
```  
struct scheduler_ptr;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор scheduler\_ptr::scheduler\_ptr \(среда выполнения с параллелизмом\)](../Topic/scheduler_ptr::scheduler_ptr%20Constructor%20\(Concurrency%20Runtime\).md)|Перегружен.  Создает указатель планировщика из shared\_ptr планировщику|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод scheduler\_ptr::get \(среда выполнения с параллелизмом\)](../Topic/scheduler_ptr::get%20Method%20\(Concurrency%20Runtime\).md)|Возвращает необработанный указатель планировщику|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор scheduler\_ptr::operator bool \(среда выполнения с параллелизмом\)](../Topic/scheduler_ptr::operator%20bool%20Operator%20\(Concurrency%20Runtime\).md)|Проверьте, является ли указатель планировщика отличным от null|  
|[Оператор scheduler\_ptr::operator\-\> \(среда выполнения с параллелизмом\)](../Topic/scheduler_ptr::operator-%3E%20Operator%20\(Concurrency%20Runtime\).md)|Поведение, как у указателя|  
  
## Иерархия наследования  
 `scheduler_ptr`  
  
## Требования  
 **Заголовок:** pplinterface.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)