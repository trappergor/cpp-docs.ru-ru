---
title: "Класс task_continuation_context | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppltasks/concurrency::task_continuation_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_continuation_context - класс"
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Класс task_continuation_context
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `task_continuation_context` позволяет указать, где требуется выполнить продолжение.  Только полезно использовать этот класс из приложения Магазина Windows.  Для приложений не для Магазина Windows контекст выполнения продолжения задачи определяется средой выполнения, а не настраивается.  
  
## Синтаксис  
  
```  
class task_continuation_context : public details::_ContextCallback;  
```  
  
## Члены  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод task\_continuation\_context::use\_arbitrary](../Topic/task_continuation_context::use_arbitrary%20Method.md)|Создает контекст выполнения продолжения задачи, позволяющий выбирать контекст выполнения для продолжения.|  
|[Метод task\_continuation\_context::use\_current](../Topic/task_continuation_context::use_current%20Method.md)|Возвращает объект контекста продолжения задачи, представляющий текущий контекст выполнения.|  
|[Метод task\_continuation\_context::use\_default](../Topic/task_continuation_context::use_default%20Method.md)|Создает контекст продолжения задачи по умолчанию.|  
  
## Иерархия наследования  
 `_ContextCallback`  
  
 `task_continuation_context`  
  
## Требования  
 **Заголовок:** ppltasks.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task Class](http://msdn.microsoft.com/ru-ru/5389e8a5-5038-40b6-844a-55e9b58ad35f)