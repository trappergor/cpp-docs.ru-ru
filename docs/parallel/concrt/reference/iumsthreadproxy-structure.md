---
title: "Структура IUMSThreadProxy | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IUMSThreadProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSThreadProxy - структура"
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Структура IUMSThreadProxy
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Абстракция для потока выполнения.  Если требуется, чтобы планировщик предоставлять запланированные пользовательского режимом потоков \(UMS\), задайте значение для элемента политики планировщика `SchedulerKind` как `UmsThreadDefault` и реализуйте интерфейс `IUMSScheduler`.  UMS потоки являются только поддерживаемыми в 64\-разрядных операционных системах, начиная с Windows 7 и выше.  
  
## Синтаксис  
  
```  
struct IUMSThreadProxy : public IThreadProxy;  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод IUMSThreadProxy::EnterCriticalRegion](../Topic/IUMSThreadProxy::EnterCriticalRegion%20Method.md)|Вызывается для ввода критической области.  Внутри критической области планировщик не будет наблюдать асинхронные операции блокирования, происходящие во время области.  Это означает, что не будет повторных входов в планировщик для ошибок страниц, приостановок потока, вызовов асинхронных процедур ядра \(APCs\) и т. д. для потока UMS.|  
|[Метод IUMSThreadProxy::EnterHyperCriticalRegion](../Topic/IUMSThreadProxy::EnterHyperCriticalRegion%20Method.md)|Вызывается для ввода гиперкритической области.  Внутри гиперкритической области планировщик не будет наблюдать любые операции блокирования, происходящие во время области.  Это означает, что в планировщик не будет повторных входов для блокирующих вызовов функции, блокирующих попыток получения блокировки, сбоев страниц, приостановках потока, вызовов асинхронных процедур ядра \(APCs\) и т. д. для потока UMS.|  
|[Метод IUMSThreadProxy::ExitCriticalRegion](../Topic/IUMSThreadProxy::ExitCriticalRegion%20Method.md)|Вызывается для выхода из критической области.|  
|[Метод IUMSThreadProxy::ExitHyperCriticalRegion](../Topic/IUMSThreadProxy::ExitHyperCriticalRegion%20Method.md)|Вызывается для выхода из гиперкритической области.|  
|[Метод IUMSThreadProxy::GetCriticalRegionType](../Topic/IUMSThreadProxy::GetCriticalRegionType%20Method.md)|Возвращает в какого рода критической области находится прокси поток.  Поскольку гиперкритические области являются надмножеством критических областей, если код вошел в критическую область, а затем в гиперкритическую, будет возвращено `InsideHyperCriticalRegion`.|  
  
## Иерархия наследования  
 [IThreadProxy](../../../parallel/concrt/reference/ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Структура IUMSScheduler](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [Перечисление SchedulerType](../Topic/SchedulerType%20Enumeration.md)