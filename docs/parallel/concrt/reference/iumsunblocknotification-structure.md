---
title: "Структура IUMSUnblockNotification | Microsoft Docs"
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
  - "concrtrm/concurrency::IUMSUnblockNotification"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSUnblockNotification - структура"
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура IUMSUnblockNotification
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Представляет уведомление от диспетчера ресурсов, что прокси поток, который заблокирован и запустил возврат к назначенному планирования контексту планировщика, разблокирован и готов для планирования.  Этот интерфейс является недопустимым после перепланирования связанного контекста выполнения прокси\-потока, возвращенного из метода `GetContext`.  
  
## Синтаксис  
  
```  
struct IUMSUnblockNotification;  
```  
  
## Члены  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод IUMSUnblockNotification::GetContext](../Topic/IUMSUnblockNotification::GetContext%20Method.md)|Возвращает интерфейс `IExecutionContext` для контекста выполнения, связанного с прокси потоком, который разблокирован.  После того, как этот метод возвращает и базовый контекст выполнения запланирован заново через вызов метода `IThreadProxy::SwitchTo`, этот интерфейс не является допустимым.|  
|[Метод IUMSUnblockNotification::GetNextUnblockNotification](../Topic/IUMSUnblockNotification::GetNextUnblockNotification%20Method.md)|Возвращает следующий интерфейс `IUMSUnblockNotification` в цепочку, возвращенную из метода `IUMSCompletionList::GetUnblockNotifications`.|  
  
## Иерархия наследования  
 `IUMSUnblockNotification`  
  
## Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Структура IUMSScheduler](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [Структура IUMSCompletionList](../../../parallel/concrt/reference/iumscompletionlist-structure.md)