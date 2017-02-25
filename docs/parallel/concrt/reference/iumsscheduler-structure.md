---
title: "Структура IUMSScheduler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IUMSScheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSScheduler - структура"
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Структура IUMSScheduler
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Интерфейс к абстракции планировщика работы, который хочет, чтобы диспетчер ресурсов среда параллелизма передал ему планируемые пользовательским режимом потоки \(UMS\).  Диспетчер ресурсов использует этот интерфейс для связи с планировщиками UMS\-потоков.  Интерфейс `IUMSScheduler` наследует от интерфейса `IScheduler`.  
  
## Синтаксис  
  
```  
struct IUMSScheduler : public IScheduler;  
```  
  
## Члены  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод IUMSScheduler::SetCompletionList](../Topic/IUMSScheduler::SetCompletionList%20Method.md)|Назначает интерфейс `IUMSCompletionList` планировщику потоков UMS.|  
  
## Заметки  
 Если при реализации пользовательских планировщика, который взаимодействует с диспетчер ресурсов, требуется, чтобы потоки UMS передавались планировщику вместо обычных потоков Win32, необходимо предоставить реализацию интерфейса `IUMSScheduler`.  Кроме того следует установить значение политики для ключа политики планировщика `SchedulerKind` как `UmsThreadDefault`.  Если политика указывает UMS\-поток, интерфейс `IScheduler`, переданный в качестве параметра методу [IResourceManager::RegisterScheduler](../Topic/IResourceManager::RegisterScheduler%20Method.md) должен быть интерфейсом `IUMSScheduler`.  
  
 Диспетчер ресурсов может передать потоки UMS только в операционных системах, поддерживающих UMS. 64\-разрядные операционные системы Windows 7 и выше поддерживают потоки UMS.  Если создать политику планировщика с ключом `SchedulerKind`, которому присвоено значение `UmsThreadDefault` и базовая платформа не поддерживает UMS, значение ключа `SchedulerKind` на этой политике будет изменено на значение `ThreadScheduler`.  Следует всегда читать это значение политики обратно перед тем, как ожидать получения потоков UMS.  
  
 Интерфейс `IUMSScheduler` — это один конец двустороннего канала связи между планировщиком и диспетчер ресурсов.  Другой конец представляется интерфейсами `IResourceManager` и `ISchedulerProxy`, которые реализуются диспетчером ресурсов.  
  
## Иерархия наследования  
 [IScheduler](../../../parallel/concrt/reference/ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Перечисление PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md)   
 [Структура IScheduler](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [Структура IUMSCompletionList](../../../parallel/concrt/reference/iumscompletionlist-structure.md)   
 [Структура IResourceManager](../../../parallel/concrt/reference/iresourcemanager-structure.md)