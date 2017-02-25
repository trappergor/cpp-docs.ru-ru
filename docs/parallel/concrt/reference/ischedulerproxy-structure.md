---
title: "Структура ISchedulerProxy | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::ISchedulerProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISchedulerProxy - структура"
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Структура ISchedulerProxy
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Интерфейс, по которому планировщики взаимодействуют со средой параллелизма диспетчера ресурсов для согласования выделения ресурсов.  
  
## Синтаксис  
  
```  
struct ISchedulerProxy;  
```  
  
## Члены  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод ISchedulerProxy::BindContext](../Topic/ISchedulerProxy::BindContext%20Method.md)|Связывает с прокси потоком контекст выполнения, если он еще не связан с одним.|  
|[Метод ISchedulerProxy::CreateOversubscriber](../Topic/ISchedulerProxy::CreateOversubscriber%20Method.md)|Создает новый корень виртуального процессора на аппаратном потоке, связанном с существующим ресурса выполнения.|  
|[Метод ISchedulerProxy::RequestInitialVirtualProcessors](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md)|Запрашивает начальное распределения корней виртуальный процессор.  Каждый корень виртуального процессор представляет возможность выполнения одного потока, который может выполнять работу для планировщика.|  
|[Метод ISchedulerProxy::Shutdown](../Topic/ISchedulerProxy::Shutdown%20Method.md)|Уведомляет диспетчер ресурсов, что выключается планировщик.  Это приведет к тому, что диспетчер ресурсов немедленно освободит все ресурсы, предоставленные планировщику.|  
|[Метод ISchedulerProxy::SubscribeCurrentThread](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md)|Регистрирует текущий поток на диспетчере ресурсов, связывая его с данным планировщиком.|  
|[Метод ISchedulerProxy::UnbindContext](../Topic/ISchedulerProxy::UnbindContext%20Method.md)|Отсоединяет прокси\-поток от контекста выполнения заданного параметром `pContext` и возвращает его в свободный пул прокси потоков фабрики.  Этот метод может быть вызвана только на контекст выполнения, который был привязан через метод [ISchedulerProxy::BindContext](../Topic/ISchedulerProxy::BindContext%20Method.md) и еще не начата, будучи параметром `pContext` вызова метода [IThreadProxy::SwitchTo](../Topic/IThreadProxy::SwitchTo%20Method.md).|  
  
## Заметки  
 Диспетчер ресурсов передает интерфейс `ISchedulerProxy` всем планировщикам, которые регистрируют его, используя метод [IResourceManager::RegisterScheduler](../Topic/IResourceManager::RegisterScheduler%20Method.md).  
  
## Иерархия наследования  
 `ISchedulerProxy`  
  
## Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Структура IScheduler](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [Структура IThreadProxy](../../../parallel/concrt/reference/ithreadproxy-structure.md)   
 [Структура IVirtualProcessorRoot](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [Структура IResourceManager](../../../parallel/concrt/reference/iresourcemanager-structure.md)