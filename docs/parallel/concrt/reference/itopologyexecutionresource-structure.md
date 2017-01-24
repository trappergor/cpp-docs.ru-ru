---
title: "Структура ITopologyExecutionResource | Microsoft Docs"
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
  - "concrtrm/concurrency::ITopologyExecutionResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITopologyExecutionResource - структура"
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: 10
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура ITopologyExecutionResource
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Интерфейс к ресурсу выполнения, как определено диспетчером ресурсов.  
  
## Синтаксис  
  
```  
struct ITopologyExecutionResource;  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод ITopologyExecutionResource::GetId](../Topic/ITopologyExecutionResource::GetId%20Method.md)|Возвращает уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.|  
|[Метод ITopologyExecutionResource::GetNext](../Topic/ITopologyExecutionResource::GetNext%20Method.md)|Возвращает интерфейс к другому ресурсу выполнения в порядке перечисления.|  
  
## Заметки  
 Этот интерфейс обычно используется для обхода топологии системы, как наблюдалось в диспетчере ресурсов.  
  
## Иерархия наследования  
 `ITopologyExecutionResource`  
  
## Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)