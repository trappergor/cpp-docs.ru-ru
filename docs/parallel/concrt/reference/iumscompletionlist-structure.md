---
title: "Структура IUMSCompletionList | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IUMSCompletionList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSCompletionList - структура"
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Структура IUMSCompletionList
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Представляет список завершения UMS.  Когда UMS поток блокируется, назначенный контекст планирования планировщика запускается для принятия решения, что запланировать на базовый корень виртуального процессора, пока исходный поток заблокирован.  Когда разблокируется исходный поток, операционная система ставит его в очередь списка завершения, которое доступен через этот интерфейс.  Планировщик может запросить список завершения на назначенный планирования контекст или любое другое место, в котором он ищет работу.  
  
## Синтаксис  
  
```  
struct IUMSCompletionList;  
```  
  
## Члены  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод IUMSCompletionList::GetUnblockNotifications](../Topic/IUMSCompletionList::GetUnblockNotifications%20Method.md)|Получает цепочку интерфейсов `IUMSUnblockNotification`, представляющих контексты выполнения, чьи связанные потоки прокси разблокированы со времени последнего вызова этого метода.|  
  
## Заметки  
 Планировщик должен быть чрезвычайно осторожным, какие действия выполняются после использования этого интерфейса для извлечения элементов из очереди списка завершения.  Элементы должны быть помещены в список работоспособных контекстов планировщика и быть общедоступными как можно скорее.  Это вполне возможно, что один из элементов, удаленных из очереди, получил владение произвольной блокировки.  Планировщик не может выполнять произвольные вызовы функции, которые могут блокировать между вызовами для извлечения элементов из очереди и размещение этих элементов в список, который обычно доступен из планировщика.  
  
## Иерархия наследования  
 `IUMSCompletionList`  
  
## Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Структура IUMSScheduler](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [Структура IUMSUnblockNotification](../../../parallel/concrt/reference/iumsunblocknotification-structure.md)