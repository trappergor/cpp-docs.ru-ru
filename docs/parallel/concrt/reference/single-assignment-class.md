---
title: "Класс single_assignment | Microsoft Docs"
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
  - "agents/concurrency::single_assignment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "single_assignment - класс"
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс single_assignment
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Блок сообщений `single_assignment` — многоцелевой, многоисточниковый, упорядоченный `propagator_block`, способный хранить одно записываемое один раз `message`.  
  
## Синтаксис  
  
```  
template<  
   class _Type  
>  
class single_assignment : public propagator_block<multi_link_registry<ITarget<_Type>>, multi_link_registry<ISource<_Type>>>;  
```  
  
#### Параметры  
 `_Type`  
 Тип полезных данных сохраненного и распространенного буфером сообщения.  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор single\_assignment::single\_assignment](../Topic/single_assignment::single_assignment%20Constructor.md)|Перегружен.  Создает блок сообщений `single_assignment`.|  
|[Деструктор single\_assignment::~single\_assignment](../Topic/single_assignment::~single_assignment%20Destructor.md)|Уничтожает блок сообщений `single_assignment`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод single\_assignment::has\_value](../Topic/single_assignment::has_value%20Method.md)|Проверяет, инициализирован ли этот блок обмена сообщениями `single_assignment` со значением.|  
|[Метод single\_assignment::value](../Topic/single_assignment::value%20Method.md)|Возвращает ссылку на текущие полезную нагрузку сообщения, хранящуюся в блоке сообщений `single_assignment`.|  
  
### Защищенные методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод single\_assignment::accept\_message](../Topic/single_assignment::accept_message%20Method.md)|Принимает сообщение, предложенное этим блоком сообщений `single_assignment`, возвращая копию сообщения вызывающему объекту.|  
|[Метод single\_assignment::consume\_message](../Topic/single_assignment::consume_message%20Method.md)|Потребляет сообщение, ранее предложенное `single_assignment` и зарезервированное целевым объектом, возвращая копию сообщения вызывающему объекту.|  
|[Метод single\_assignment::link\_target\_notification](../Topic/single_assignment::link_target_notification%20Method.md)|Обратный вызов, который уведомляет, что новая цель связана с этим блоком сообщений `single_assignment`.|  
|[Метод single\_assignment::propagate\_message](../Topic/single_assignment::propagate_message%20Method.md)|Асинхронно передает сообщение из блока `ISource` в этот блок сообщений `single_assignment`.  Вызывается методом `propagate` при вызове исходного блока.|  
|[Метод single\_assignment::propagate\_to\_any\_targets](../Topic/single_assignment::propagate_to_any_targets%20Method.md)|Помещает `message``_PMessage` в данный блок обмена сообщениями `single_assignment` и предлагает его всем связанным целевым объектам.|  
|[Метод single\_assignment::release\_message](../Topic/single_assignment::release_message%20Method.md)|Освобождает предыдущее резервирование сообщения. \(Переопределяет конструктор [source\_block::release\_message](../Topic/source_block::release_message%20Method.md)\).|  
|[Метод single\_assignment::reserve\_message](../Topic/single_assignment::reserve_message%20Method.md)|Резервирует сообщение, которое было предложено этим блоком сообщений `single_assignment`. \(Переопределяет конструктор [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md)\).|  
|[Метод single\_assignment::resume\_propagation](../Topic/single_assignment::resume_propagation%20Method.md)|Возобновляет распространение после отмены резервирования. \(Переопределяет конструктор [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md)\).|  
|[Метод single\_assignment::send\_message](../Topic/single_assignment::send_message%20Method.md)|Синхронно передает сообщение из блока `ISource` в этот блок сообщений `single_assignment`.  Вызывается методом `send` при вызове исходного блока.|  
  
## Заметки  
 Блок сообщений `single_assignment` распространяет копии его сообщения для каждой цели.  
  
 Для получения дополнительной информации см. [Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Иерархия наследования  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../Topic/source_block%20Class.md)  
  
 [propagator\_block](../../../parallel/concrt/reference/propagator-block-class.md)  
  
 `single_assignment`  
  
## Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс overwrite\_buffer](../../../parallel/concrt/reference/overwrite-buffer-class.md)   
 [Класс unbounded\_buffer](../Topic/unbounded_buffer%20Class.md)