---
title: "Структура ITopologyNode | Microsoft Docs"
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
  - "concrtrm/concurrency::ITopologyNode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITopologyNode - структура"
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
caps.latest.revision: 10
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура ITopologyNode
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Интерфейс на узле топологии, определенный диспетчером ресурсов.  Узел содержит один или несколько ресурсов выполнения.  
  
## Синтаксис  
  
```  
struct ITopologyNode;  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод ITopologyNode::GetExecutionResourceCount](../Topic/ITopologyNode::GetExecutionResourceCount%20Method.md)|Возвращает количество ресурсов выполнения, сгруппированных под этим узлом.|  
|[Метод ITopologyNode::GetFirstExecutionResource](../Topic/ITopologyNode::GetFirstExecutionResource%20Method.md)|Возвращает первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.|  
|[Метод ITopologyNode::GetId](../Topic/ITopologyNode::GetId%20Method.md)|Возвращает уникальный идентификатор диспетчера ресурсов для данного узла.|  
|[Метод ITopologyNode::GetNext](../Topic/ITopologyNode::GetNext%20Method.md)|Возвращает интерфейс к следующему узлу топологии в порядке перечисления.|  
|[Метод ITopologyNode::GetNumaNode](../Topic/ITopologyNode::GetNumaNode%20Method.md)|Возвращает номер узла NUMA Windows, к которому принадлежит этот узел диспетчера ресурсов.|  
  
## Заметки  
 Этот интерфейс обычно используется для обхода топологии системы, как наблюдалось в диспетчере ресурсов.  
  
## Иерархия наследования  
 `ITopologyNode`  
  
## Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)