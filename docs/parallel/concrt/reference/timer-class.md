---
title: "Класс timer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::timer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "timer - класс"
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс timer
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Блок сообщений `timer` — это одноцелевой `source_block`, способный отправлять сообщение цели по истечении указанного периода времени или через определенные интервалы.  
  
## Синтаксис  
  
```  
template<  
   class _Type  
>  
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<_Type>>>;  
```  
  
#### Параметры  
 `_Type`  
 Тип полезных данных выводных сообщений этого блока.  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор timer::timer](../Topic/timer::timer%20Constructor.md)|Перегружен.  Создает блок сообщений `timer` который, будет отправлять заданное сообщение после указанного интервала.|  
|[Деструктор timer::~timer](../Topic/timer::~timer%20Destructor.md)|Уничтожает блок сообщений `timer`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод timer::pause](../Topic/timer::pause%20Method.md)|Останавливает блок обмена сообщениями `timer`.  Если это повторяющаяся блока обмена сообщениями `timer`, можно перезапустить его с последующим вызовом `start()`.  Для неповторяющихся таймеров, это имеет тот же эффект, как вызов `stop`.|  
|[Метод timer::start](../Topic/timer::start%20Method.md)|Начинает блок сообщений `timer`.  Через заданное количество миллисекунд после этого вызова, указанное значение распространяется дальше по ходу процесса как `message`.|  
|[Метод timer::stop](../Topic/timer::stop%20Method.md)|Останавливает блок обмена сообщениями `timer`.|  
  
### Защищенные методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод timer::accept\_message](../Topic/timer::accept_message%20Method.md)|Принимает сообщение, предложенное этим блоком сообщений `timer`, передавая владение вызывающему объекту.|  
|[Метод timer::consume\_message](../Topic/timer::consume_message%20Method.md)|Потребляет сообщение, ранее предложенное `timer` зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[Метод timer::link\_target\_notification](../Topic/timer::link_target_notification%20Method.md)|Обратный вызов, который уведомляет, что новая цель связана с этим блоком сообщений `timer`.|  
|[Метод timer::propagate\_to\_any\_targets](../Topic/timer::propagate_to_any_targets%20Method.md)|Пытается предложить сообщение, созданное блоком `timer`, на все связанные целевые объекты.|  
|[Метод timer::release\_message](../Topic/timer::release_message%20Method.md)|Освобождает предыдущее резервирование сообщения. \(Переопределяет конструктор [source\_block::release\_message](../Topic/source_block::release_message%20Method.md)\).|  
|[Метод timer::reserve\_message](../Topic/timer::reserve_message%20Method.md)|Резервирует сообщение, которое было предложено этим блоком сообщений `timer`. \(Переопределяет конструктор [source\_block::reserve\_message](../Topic/source_block::reserve_message%20Method.md)\).|  
|[Метод timer::resume\_propagation](../Topic/timer::resume_propagation%20Method.md)|Возобновляет распространение после отмены резервирования. \(Переопределяет конструктор [source\_block::resume\_propagation](../Topic/source_block::resume_propagation%20Method.md)\).|  
  
## Заметки  
 Для получения дополнительной информации см. [Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Иерархия наследования  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [source\_block](../Topic/source_block%20Class.md)  
  
 `timer`  
  
## Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)