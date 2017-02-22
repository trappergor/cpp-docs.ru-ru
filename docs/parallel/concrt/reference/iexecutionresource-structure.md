---
title: "Структура IExecutionResource | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IExecutionResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IExecutionResource - структура"
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Структура IExecutionResource
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Абстракция для аппаратного потока.  
  
## Синтаксис  
  
```  
struct IExecutionResource;  
```  
  
## Члены  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод IExecutionResource::CurrentSubscriptionLevel](../Topic/IExecutionResource::CurrentSubscriptionLevel%20Method.md)|Возвращает число активированных корней виртуальных процессоров и подписанные внешние потоки, сейчас связанные с базовым аппаратным потоком, который представляет этот ресурс выполнения.|  
|[Метод IExecutionResource::GetExecutionResourceId](../Topic/IExecutionResource::GetExecutionResourceId%20Method.md)|Возвращает уникальный идентификатор для аппаратного потока, представляемого этим ресурсом выполнения.|  
|[Метод IExecutionResource::GetNodeId](../Topic/IExecutionResource::GetNodeId%20Method.md)|Возвращает уникальный идентификатор для узла процессора, к которому принадлежит этот ресурс выполнения.|  
|[Метод IExecutionResource::Remove](../Topic/IExecutionResource::Remove%20Method.md)|Возвращает этот ресурс выполнения диспетчеру ресурсов.|  
  
## Заметки  
 Ресурсы выполнения могут быть автономными или связанными с корнями виртуального процессор.  Автономный ресурс выполнения создается, когда поток в приложении создает подписку потока.  Методы [ISchedulerProxy::SubscribeThread](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md) и [ISchedulerProxy::RequestInitialVirtualProcessors](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md) создают подписки потоков и возвращают интерфейс `IExecutionResource`, представляющий подписку.  Создание подписки потока является способом информирования диспетчер ресурсов, что данный поток будет участвовать в работе, поставленной в очередь планировщика, вместе с корнями виртуальных процессоров, назначенные диспетчером ресурсов планировщику.  Диспетчер ресурсов использует сведения, чтобы избежать переподписки аппаратных потоков, где может.  
  
## Иерархия наследования  
 `IExecutionResource`  
  
## Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Структура IVirtualProcessorRoot](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [Метод ISchedulerProxy::SubscribeCurrentThread](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md)   
 [Метод ISchedulerProxy::RequestInitialVirtualProcessors](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md)