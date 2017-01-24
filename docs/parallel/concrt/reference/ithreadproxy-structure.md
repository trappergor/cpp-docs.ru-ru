---
title: "Структура IThreadProxy | Microsoft Docs"
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
  - "concrtrm/concurrency::IThreadProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IThreadProxy - структура"
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
caps.latest.revision: 21
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура IThreadProxy
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Абстракция для потока выполнения.  В зависимости от создаваемого ключа политики `SchedulerType` планировщика, диспетчер ресурсов будет предоставить прокси\-поток, который основывается на регулярном потоке Win32 или потоком, планируемым в режиме пользователя \(UMS\).  UMS потоки являются поддерживаемыми в 64\-разрядных операционных системах, начиная с Windows 7 и выше.  
  
## Синтаксис  
  
```  
struct IThreadProxy;  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод IThreadProxy::GetId](../Topic/IThreadProxy::GetId%20Method.md)|Возвращает уникальный идентификатор для прокси потока.|  
|[Метод IThreadProxy::SwitchOut](../Topic/IThreadProxy::SwitchOut%20Method.md)|Отсоединяет контекст от базового корневого виртуального процессора.|  
|[Метод IThreadProxy::SwitchTo](../Topic/IThreadProxy::SwitchTo%20Method.md)|Выполняет совместное переключение контекста из текущего выполняемого контекста в другой.|  
|[Метод IThreadProxy::YieldToSystem](../Topic/IThreadProxy::YieldToSystem%20Method.md)|Заставляет вызвавший поток передать выполнение другому потоку, готовому к использованию на текущем процессоре.  Операционная система выбирает следующий поток для выполнения.|  
  
## Заметки  
 Прокси\-потоки привязаны к контекстам выполнения, представленными интерфейсом `IExecutionContext` как способ управления работой.  
  
## Иерархия наследования  
 `IThreadProxy`  
  
## Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Структура IExecutionContext](../Topic/IExecutionContext%20Structure.md)   
 [Структура IScheduler](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [Структура IVirtualProcessorRoot](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)