---
title: "Класс agent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::agent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "agent - класс"
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс agent
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс предназначен для использования как базовый класс для всех независимых агентов.  Используется для скрытия состояния от других агентов и взаимодействия с помощью передачи сообщений.  
  
## Синтаксис  
  
```  
class agent;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор agent::agent](../Topic/agent::agent%20Constructor.md)|Перегружен.  Создает агент.|  
|[Деструктор agent::~agent](../Topic/agent::~agent%20Destructor.md)|Уничтожает агент.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод agent::cancel](../Topic/agent::cancel%20Method.md)|Переводит агента из состояния `agent_created` или `agent_runnable` в состояние `agent_canceled`.|  
|[Метод agent::start](../Topic/agent::start%20Method.md)|Перемещает агента из состояния `agent_created` в состояние `agent_runnable` и назначает его для выполнения.|  
|[Метод agent::status](../Topic/agent::status%20Method.md)|Синхронный источник сведений о состоянии от агента.|  
|[Метод agent::status\_port](../Topic/agent::status_port%20Method.md)|Асинхронный источник сведений о состоянии от агента.|  
|[Метод agent::wait](../Topic/agent::wait%20Method.md)|Ожидает выполнения задач агента.|  
|[Метод agent::wait\_for\_all](../Topic/agent::wait_for_all%20Method.md)|Ожидает, когда все указанные агенты выполнят своих задач.|  
|[Метод agent::wait\_for\_one](../Topic/agent::wait_for_one%20Method.md)|Ожидает, когда любой из указанных агентов выполнят своих задач.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод agent::done](../Topic/agent::done%20Method.md)|Перемещает агент в состояние `agent_done`, указывающее, что агент завершился.|  
|[Метод agent::run](../Topic/agent::run%20Method.md)|Представляет основную задача агента.  `run` должен быть переопределен в производном классе и указывает, что агент должен делать после его запуска.|  
  
## Заметки  
 Для получения дополнительной информации см. [Асинхронные агенты](../../../parallel/concrt/asynchronous-agents.md).  
  
## Иерархия наследования  
 `agent`  
  
## Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)