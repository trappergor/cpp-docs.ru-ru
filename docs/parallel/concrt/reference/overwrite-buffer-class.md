---
title: "Класс overwrite_buffer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::overwrite_buffer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "overwrite_buffer - класс"
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# Класс overwrite_buffer
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Блок сообщений `overwrite_buffer` — многоцелевой, многоисточниковый, упорядоченный `propagator_block`, способный хранить одно сообщение за раз.  Новые сообщения перезаписывают предыдущие.  
  
## Синтаксис  
  
```  
template<  
   class _Type  
>  
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<_Type>>, multi_link_registry<ISource<_Type>>>;  
```  
  
#### Параметры  
 `_Type`  
 Тип полезных данных сохраненных и распространенных буфером сообщений.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор overwrite\_buffer::overwrite\_buffer](../Topic/overwrite_buffer::overwrite_buffer%20Constructor.md)|Перегружен.  Создает блок сообщений `overwrite_buffer`.|  
|[Деструктор overwrite\_buffer:: ~ overwrite\_buffer](../Topic/overwrite_buffer::~overwrite_buffer%20Destructor.md)|Уничтожает блок сообщений `overwrite_buffer`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод overwrite\_buffer::has\_value](../Topic/overwrite_buffer::has_value%20Method.md)|Проверяет, имеет ли этот блок обмена сообщениями `overwrite_buffer` значение.|  
|[Метод overwrite\_buffer::value](../Topic/overwrite_buffer::value%20Method.md)|Возвращает ссылку на текущие полезную нагрузку сообщения, хранящуюся в блоке сообщений `overwrite_buffer`.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод overwrite\_buffer::accept\_message](../Topic/overwrite_buffer::accept_message%20Method.md)|Принимает сообщение, предложенное этим блоком сообщений `overwrite_buffer`, возвращая копию сообщения вызывающему объекту.|  
|[Метод overwrite\_buffer::consume\_message](../Topic/overwrite_buffer::consume_message%20Method.md)|Потребляет сообщение, ранее предложенное блоком сообщений `overwrite_buffer` и зарезервированное целевым объектом, возвращая копию сообщения вызывающему объекту.|  
|[Метод overwrite\_buffer::link\_target\_notification](../Topic/overwrite_buffer::link_target_notification%20Method.md)|Обратный вызов, который уведомляет, что новая цель связана с этим блоком сообщений `overwrite_buffer`.|  
|[Метод overwrite\_buffer::propagate\_message](../Topic/overwrite_buffer::propagate_message%20Method.md)|Асинхронно передает сообщение из блока `ISource` в этот блок сообщений `overwrite_buffer`.  Вызывается методом `propagate` при вызове исходного блока.|  
|[Метод overwrite\_buffer::propagate\_to\_any\_targets](../Topic/overwrite_buffer::propagate_to_any_targets%20Method.md)|Помещает `message``_PMessage` в данный блок обмена сообщениями `overwrite_buffer` и предлагает его всем связанным целевым объектам.|  
|[Метод overwrite\_buffer::release\_message](../Topic/overwrite_buffer::release_message%20Method.md)|Освобождает предыдущее резервирование сообщения. \(Переопределяет конструктор [source\_block::release\_message](../Topic/source_block::release_message%20Method.md)\).|  
|[Метод overwrite\_buffer::reserve\_message](../Topic/overwrite_buffer::reserve_message%20Method.md)|Резервирует сообщение, которое было предложено этим блоком сообщений `overwrite_buffer`. \(Переопределяет конструктор [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md)\).|  
|[Метод overwrite\_buffer::resume\_propagation](../Topic/overwrite_buffer::resume_propagation%20Method.md)|Возобновляет распространение после отмены резервирования. \(Переопределяет конструктор [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md)\).|  
|[Метод overwrite\_buffer::send\_message](../Topic/overwrite_buffer::send_message%20Method.md)|Синхронно передает сообщение из блока `ISource` в этот блок сообщений `overwrite_buffer`.  Вызывается методом `send` при вызове исходного блока.|  
|[Метод overwrite\_buffer::supports\_anonymous\_source](../Topic/overwrite_buffer::supports_anonymous_source%20Method.md)|Переопределяет метод `supports_anonymous_source`, чтобы показать, что данный блок может принимать сообщения, предоставляемые ему несвязанным источником. \(Переопределяет метод [ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md)\).|  
  
## Заметки  
 Блок сообщений `overwrite_buffer` распространяет копии своего сохраненного сообщения для каждого целевого объекта.  
  
 Для получения дополнительной информации см. [Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Иерархия наследования  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../Topic/source_block%20Class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `overwrite_buffer`  
  
## Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс unbounded\_buffer](../Topic/unbounded_buffer%20Class.md)   
 [Класс single\_assignment](../../../parallel/concrt/reference/single-assignment-class.md)