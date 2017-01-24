---
title: "Структура IScheduler | Microsoft Docs"
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
  - "concrtrm/concurrency::IScheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IScheduler - структура"
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
caps.latest.revision: 18
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура IScheduler
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Интерфейс к абстракции планировщика работы.  Диспетчер ресурсов среды параллелизма использует этот интерфейс для связи с планировщиками работы.  
  
## Синтаксис  
  
```  
struct IScheduler;  
```  
  
## Члены  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод IScheduler::AddVirtualProcessors](../Topic/IScheduler::AddVirtualProcessors%20Method.md)|Предоставляет планировщик с набором корней виртуальный процессор для его использования.  Каждый интерфейс `IVirtualProcessorRoot` представляет право на выполнение одного потока, которые выполняют работы от имени планировщик.|  
|[Метод IScheduler::GetId](../Topic/IScheduler::GetId%20Method.md)|Возвращает уникальный идентификатор для планировщика.|  
|[Метод IScheduler::GetPolicy](../Topic/IScheduler::GetPolicy%20Method.md)|Возвращает копию политики планировщика.  Дополнительные сведения о политиках планировщиков см. в разделе [SchedulerPolicy](../../../parallel/concrt/reference/schedulerpolicy-class.md).|  
|[Метод IScheduler::NotifyResourcesExternallyBusy](../Topic/IScheduler::NotifyResourcesExternallyBusy%20Method.md)|Уведомляет этот планировщик, что аппаратные потоки, представленные набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` теперь используются другими планировщики.|  
|[Метод IScheduler::NotifyResourcesExternallyIdle](../Topic/IScheduler::NotifyResourcesExternallyIdle%20Method.md)|Уведомляет этот планировщик, что аппаратные потоки, представленные набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` не используются другими планировщики.|  
|[Метод IScheduler::RemoveVirtualProcessors](../Topic/IScheduler::RemoveVirtualProcessors%20Method.md)|Инициирует удаления корней виртуального процессора, которые ранее были распределены данным планировщиком.|  
|[Метод IScheduler::Statistics](../Topic/IScheduler::Statistics%20Method.md)|Предоставляет сведения, относящиеся к прибытию задач и уровням завершения и изменение длины очереди для планировщика.|  
  
## Заметки  
 При реализации пользовательских планировщика, который взаимодействует с диспетчер ресурсов, необходимо предоставить реализацию интерфейса `IScheduler`.  Этот интерфейс — это один конец двустороннего канала связи между планировщиком и диспетчер ресурсов.  Другой конец представляется интерфейсами `IResourceManager` и `ISchedulerProxy`, которые реализуются диспетчером ресурсов.  
  
## Иерархия наследования  
 `IScheduler`  
  
## Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Перечисление PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md)   
 [Класс SchedulerPolicy](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [Структура IExecutionContext](../Topic/IExecutionContext%20Structure.md)   
 [Структура IThreadProxy](../../../parallel/concrt/reference/ithreadproxy-structure.md)   
 [Структура IVirtualProcessorRoot](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [Структура IResourceManager](../../../parallel/concrt/reference/iresourcemanager-structure.md)