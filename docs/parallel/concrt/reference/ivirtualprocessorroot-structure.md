---
title: "Структура IVirtualProcessorRoot | Microsoft Docs"
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
  - "concrtrm/concurrency::IVirtualProcessorRoot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IVirtualProcessorRoot - структура"
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
caps.latest.revision: 18
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура IVirtualProcessorRoot
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Абстракция для аппаратного потока, на котором может выполняться прокси\-поток.  
  
## Синтаксис  
  
```  
struct IVirtualProcessorRoot : public IExecutionResource;  
```  
  
## Члены  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод IVirtualProcessorRoot::Activate](../Topic/IVirtualProcessorRoot::Activate%20Method.md)|Вызывает связанный с интерфейсом контекста выполнения `pContext` прокси\-поток, чтобы начать выполнение этом корне виртуального процессора.|  
|[Метод IVirtualProcessorRoot::Deactivate](../Topic/IVirtualProcessorRoot::Deactivate%20Method.md)|Приводит к тому, что прокси\-поток, выполняющийся на данном корне виртуального процессора, прекращает управлять контекстом выполнения.  Прокси\-поток продолжит выполнение при вызове метода `Activate`.|  
|[Метод IVirtualProcessorRoot::EnsureAllTasksVisible](../Topic/IVirtualProcessorRoot::EnsureAllTasksVisible%20Method.md)|Приводит к тому, что данные, хранящиеся в иерархии памяти отдельных процессоров, становятся видимыми для всех процессоров в системе.  Это гарантирует, что полная памяти граница была выполнена на всех процессорах перед возвратом метода.|  
|[Метод IVirtualProcessorRoot::GetId](../Topic/IVirtualProcessorRoot::GetId%20Method.md)|Возвращает уникальный идентификатор для корня виртуального процессора.|  
  
## Заметки  
 Каждый корень виртуального процессора имеет связанный ресурс выполнения.  Интерфейс `IVirtualProcessorRoot` наследуется от интерфейса [IExecutionResource](../../../parallel/concrt/reference/iexecutionresource-structure.md).  Несколько корней виртуальный процессор может соответствовать один и тот же базовый поток оборудования.  
  
 Диспетчер ресурсов предоставляет корни виртуального процессора планировщикам в ответ на запросы ресурсов.  Планировщик может использовать корневой виртуальный процессор для выполнения работы, активировав его с контекстом выполнения.  
  
## Иерархия наследования  
 [IExecutionResource](../../../parallel/concrt/reference/iexecutionresource-structure.md)  
  
 `IVirtualProcessorRoot`  
  
## Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)