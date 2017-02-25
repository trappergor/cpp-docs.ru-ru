---
title: "Worker Archetype | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Worker archetype"
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Worker Archetype
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Классы, соответствующие архетипу *рабочего* процесса предоставляют код в очереди элементы работы в пуле потоков.  
  
 **Реализация**  
  
 Чтобы реализовать класс, соответствующий этому архетипу, класс должен предоставлять следующие функции:  
  
|Метод|Описание|  
|-----------|--------------|  
|[Инициализация](../Topic/WorkerArchetype::Initialize.md)|Вызываемый для инициализации объекта работу перед всеми запросами передайте в [Execute](../Topic/WorkerArchetype::Execute.md).|  
|[Выполнение](../Topic/WorkerArchetype::Execute.md)|Вызываемый для обработки рабочий элемент.|  
|[Завершить](../Topic/WorkerArchetype::Terminate.md)|Вызываемый для uninitialize объект работу после того, как все запросы будут переданы [Execute](../Topic/WorkerArchetype::Execute.md).|  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|[RequestType](../Topic/WorkerArchetype::RequestType.md)|Typedef для типа рабочего элемента, который может быть обработан классом рабочего процесса.|  
  
 Типичный класс *работы* выглядит следующим образом:  
  
 [!CODE [NVC_ATL_Utilities#137](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#137)]  
  
 **Существующие реализации**  
  
 Эти классы соответствующих этому архетипу:  
  
|Класс|Описание|  
|-----------|--------------|  
|[CNonStatelessWorker](../Topic/CNonStatelessWorker%20Class.md)|Получает запросы из пула потоков и передает их в объект работы, создание и уничтожается для каждого запроса.|  
  
 **Применение**  
  
 Эти параметры шаблона ожидают класс, чтобы соответствовать этому архетипу:  
  
|Имя параметра|Использующие элементы|  
|-------------------|---------------------------|  
|*Рабочий*|[CThreadPool](../Topic/CThreadPool%20Class.md)|  
|*Рабочий*|[CNonStatelessWorker](../Topic/CNonStatelessWorker%20Class.md)|  
  
## Требования  
 **Header:** atlutil.h  
  
## См. также  
 [Archetypes](../../atl/reference/atl-archetypes.md)   
 [Основные понятия](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)