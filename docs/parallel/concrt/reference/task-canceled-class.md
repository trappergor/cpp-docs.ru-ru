---
title: "Класс task_canceled | Microsoft Docs"
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
  - "concrt/concurrency::task_canceled"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_canceled - класс"
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
caps.latest.revision: 11
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс task_canceled
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Этот класс описывает исключение, которое создается уровнем задач PPL для принудительной отмены текущей задачи.  Оно также создается методом `get()` для [задачи](../Topic/Task%20Class%20-%20Internal%20Members.md), для отмененной задачи.  
  
## Синтаксис  
  
```  
class task_canceled : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор task\_canceled::task\_canceled](../Topic/task_canceled::task_canceled%20Constructor.md)|Перегружен.  Создает объект `task_canceled`.|  
  
## Иерархия наследования  
 `exception`  
  
 `task_canceled`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Метод task::get](../Topic/task::get%20Method.md)   
 [Функция cancel\_current\_task](../Topic/cancel_current_task%20Function.md)