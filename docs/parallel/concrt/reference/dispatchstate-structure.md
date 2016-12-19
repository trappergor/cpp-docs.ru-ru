---
title: "Структура DispatchState | Microsoft Docs"
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
  - "concrtrm/concurrency::DispatchState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DispatchState - структура"
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
caps.latest.revision: 17
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура DispatchState
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Структура `DispatchState` используется для передачи состояния методу `IExecutionContext::Dispatch`.  Он описывает обстоятельства, под которыми вызывается метод `Dispatch` на интерфейсе `IExecutionContext`.  
  
## Синтаксис  
  
```  
struct DispatchState;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор DispatchState::DispatchState](../Topic/DispatchState::DispatchState%20Constructor.md)|Создает новый объект `DispatchState`.|  
  
### Открытые члены данных  
  
|Name|Описание|  
|----------|--------------|  
|[Член данных DispatchState::m\_dispatchStateSize](../Topic/DispatchState::m_dispatchStateSize%20Data%20Member.md)|Размер этой структуры, который используется для управления версиями.|  
|[Член данных DispatchState::m\_fIsPreviousContextAsynchronouslyBlocked](../Topic/DispatchState::m_fIsPreviousContextAsynchronouslyBlocked%20Data%20Member.md)|Сообщает, этот контекст вошел ли в метод `Dispatch`, так как предыдущий контекст асинхронно блокирован.  Это используется только в контексте планирования UMS и ему присвоено значение `0` для всех других контекстов выполнения.|  
|[Член данных DispatchState::m\_reserved](../Topic/DispatchState::m_reserved%20Data%20Member.md)|Биты, зарезервированы для будущих передач информации.|  
  
## Иерархия наследования  
 `DispatchState`  
  
## Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Метод IExecutionContext::Dispatch](../Topic/IExecutionContext::Dispatch%20Method.md)