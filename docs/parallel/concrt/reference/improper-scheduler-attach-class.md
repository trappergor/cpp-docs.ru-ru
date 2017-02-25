---
title: "Класс improper_scheduler_attach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::improper_scheduler_attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_scheduler_attach - класс"
ms.assetid: 5a76da0a-091b-4748-8f62-b3a28f674f9e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс improper_scheduler_attach
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, которое генерируется каждый раз, когда вызывается метод `Attach` на объекте `Scheduler`, который уже присоединен к текущему контексту.  
  
## Синтаксис  
  
```  
class improper_scheduler_attach : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор improper\_scheduler\_attach::improper\_scheduler\_attach](../Topic/improper_scheduler_attach::improper_scheduler_attach%20Constructor.md)|Перегружен.  Создает объект `improper_scheduler_attach`.|  
  
## Иерархия наследования  
 `exception`  
  
 `improper_scheduler_attach`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс Scheduler](../../../parallel/concrt/reference/scheduler-class.md)   
 [Метод Scheduler::Attach](../Topic/Scheduler::Attach%20Method.md)