---
title: "Класс transformer | Microsoft Docs"
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
  - "agents/concurrency::transformer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "transformer - класс"
ms.assetid: eea71925-7043-4a92-bfd4-dbc0ece5d081
caps.latest.revision: 22
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс transformer
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Блок сообщений `transformer` — одноцелевой многоисточниковый упорядоченный `propagator_block`, который может принимать сообщения одного типа и способен хранить неограниченное число сообщений другого типа.  
  
## Синтаксис  
  
```  
template<  
   class _Input,  
   class _Output  
>  
class transformer : public propagator_block<single_link_registry<ITarget<_Output>>, multi_link_registry<ISource<_Input>>>;  
```  
  
#### Параметры  
 `_Input`  
 Тип полезных данных сообщений, принятых буфером.  
  
 `_Output`  
 Тип полезных данных сохраненных и распространенных из буфера сообщений.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор transformer::transformer](../Topic/transformer::transformer%20Constructor.md)|Перегружен.  Создает блок сообщений `transformer`.|  
|[Деструктор transformer::~transformer](../Topic/transformer::~transformer%20Destructor.md)|Уничтожает блок сообщений `transformer`.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод transformer::accept\_message](../Topic/transformer::accept_message%20Method.md)|Принимает сообщение, предложенное этим блоком сообщений `transformer`, передавая владение вызывающему объекту.|  
|[Метод transformer::consume\_message](../Topic/transformer::consume_message%20Method.md)|Потребляет сообщение, ранее предложенное `transformer` зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[Метод transformer::link\_target\_notification](../Topic/transformer::link_target_notification%20Method.md)|Обратный вызов, который уведомляет, что новая цель связана с этим блоком сообщений `transformer`.|  
|[Метод transformer::propagate\_message](../Topic/transformer::propagate_message%20Method.md)|Асинхронно передает сообщение из блока `ISource` в этот блок сообщений `transformer`.  Вызывается методом `propagate` при вызове исходного блока.|  
|[Метод transformer::propagate\_to\_any\_targets](../Topic/transformer::propagate_to_any_targets%20Method.md)|Выполняет функцию преобразователя для входящих сообщений.|  
|[Метод transformer::release\_message](../Topic/transformer::release_message%20Method.md)|Освобождает предыдущее резервирование сообщения. \(Переопределяет конструктор [source\_block::release\_message](../Topic/source_block::release_message%20Method.md)\).|  
|[Метод transformer::reserve\_message](../Topic/transformer::reserve_message%20Method.md)|Резервирует сообщение, которое было предложено этим блоком сообщений `transformer`. \(Переопределяет конструктор [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md)\).|  
|[Метод transformer::resume\_propagation](../Topic/transformer::resume_propagation%20Method.md)|Возобновляет распространение после отмены резервирования. \(Переопределяет конструктор [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md)\).|  
|[Метод transformer::send\_message](../Topic/transformer::send_message%20Method.md)|Синхронно передает сообщение из блока `ISource` в этот блок сообщений `transformer`.  Вызывается методом `send` при вызове исходного блока.|  
|[Метод transformer::supports\_anonymous\_source](../Topic/transformer::supports_anonymous_source%20Method.md)|Переопределяет метод `supports_anonymous_source`, чтобы показать, что данный блок может принимать сообщения, предоставляемые ему несвязанным источником. \(Переопределяет метод [ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md)\).|  
  
## Заметки  
 Для получения дополнительной информации см. [Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Иерархия наследования  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../Topic/source_block%20Class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `transformer`  
  
## Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс call](../../../parallel/concrt/reference/call-class.md)