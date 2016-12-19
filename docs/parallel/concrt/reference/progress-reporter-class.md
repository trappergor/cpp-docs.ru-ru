---
title: "Класс progress_reporter | Microsoft Docs"
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
  - "ppltasks/concurrency::progress_reporter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "progress_reporter - класс"
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
caps.latest.revision: 11
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс progress_reporter
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс progress\_reporter позволяет создавать уведомления определенного типа о ходе выполнения.  Каждый объект progress\_reporter привязан к конкретному асинхронному действию или операции.  
  
## Синтаксис  
  
```  
template<  
   typename _ProgressType  
>  
class progress_reporter;  
```  
  
#### Параметры  
 `_ProgressType`  
 Тип полезной нагрузки каждого уведомления о ходе выполнения, сообщаемой через progress\_reporter.  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор progress\_reporter::progress\_reporter](../Topic/progress_reporter::progress_reporter%20Constructor.md)||  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод progress\_reporter::report](../Topic/progress_reporter::report%20Method.md)|Отправляет отчет о ходе выполнения асинхронному действию или операции, к которым привязан этот progress\_reporter.|  
  
## Заметки  
 Этот тип доступен только в приложениях Магазина Windows.  
  
## Иерархия наследования  
 `progress_reporter`  
  
## Требования  
 **Заголовок:** ppltasks.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Функция create\_async](../Topic/create_async%20Function.md)