---
title: "Класс message_processor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::message_processor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message_processor - класс"
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Класс message_processor
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `message_processor` является абстрактным базовым классом для обработки объектов `message`.  Нет никакой гарантии на порядок сообщений.  
  
## Синтаксис  
  
```  
template<  
   class _Type  
>  
class message_processor;  
```  
  
#### Параметры  
 `_Type`  
 Тип данных полезных данных внутри сообщений, обрабатываемых этим объектом `message_processor`.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Name|Описание|  
|----------|--------------|  
|`type`|Псевдоним типа для `_Type`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод message\_processor::async\_send](../Topic/message_processor::async_send%20Method.md)|При переопределении в производном классе размещает сообщения в блок асинхронно.|  
|[Метод message\_processor::sync\_send](../Topic/message_processor::sync_send%20Method.md)|При переопределении в производном классе размещает сообщения в блок синхронно.|  
|[Метод message\_processor::wait](../Topic/message_processor::wait%20Method.md)|При переопределении в производном классе, ожидает завершения всех асинхронных операций.|  
  
### Защищенные методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод message\_processor::process\_incoming\_message](../Topic/message_processor::process_incoming_message%20Method.md)|При переопределении в производном классе выполняет прямую обработки сообщений в блок.  Вызывается один раз, каждый раз когда добавляется новое сообщение и очередь оказывается пустой.|  
  
## Иерархия наследования  
 `message_processor`  
  
## Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс ordered\_message\_processor](../Topic/ordered_message_processor%20Class.md)