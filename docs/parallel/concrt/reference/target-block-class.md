---
title: "Класс target_block | Microsoft Docs"
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
  - "agents/concurrency::target_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "target_block - класс"
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
caps.latest.revision: 21
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс target_block
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `target_block` является абстрактным базовым классом, который предоставляет основные функции управления ссылками и проверку ошибок для блоков, являющихся только целевыми.  
  
## Синтаксис  
  
```  
template<  
   class _SourceLinkRegistry,  
   class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>  
>  
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;  
```  
  
#### Параметры  
 `_SourceLinkRegistry`  
 Реестр ссылок для использования для хранения исходных ссылок.  
  
 `_MessageProcessorType`  
 Тип процессора для обработки сообщений.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`source_iterator`|Тип итератора для `source_link_manager` данного объекта `target_block`.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор target\_block::target\_block](../Topic/target_block::target_block%20Constructor.md)|Создает объект `target_block`.|  
|[Деструктор target\_block::~target\_block](../Topic/target_block::~target_block%20Destructor.md)|Уничтожает объект `target_block`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод target\_block::propagate](../Topic/target_block::propagate%20Method.md)|Асинхронно передает сообщение из исходного блока данному целевому блоку.|  
|[Метод target\_block::send](../Topic/target_block::send%20Method.md)|Для этого целевого блока синхронно пересылает сообщение из исходного блока.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод target\_block::async\_send](../Topic/target_block::async_send%20Method.md)|Асинхронно отправляет сообщение для обработки.|  
|[Метод target\_block::decline\_incoming\_messages](../Topic/target_block::decline_incoming_messages%20Method.md)|Указывает блоку, что новые сообщения должны быть отклонены.|  
|[Метод target\_block::enable\_batched\_processing](../Topic/target_block::enable_batched_processing%20Method.md)|Активирует пакетную обработку для этого блока.|  
|[Метод target\_block::initialize\_target](../Topic/target_block::initialize_target%20Method.md)|Инициализирует базовый объект.  В частности, объект `message_processor` необходимо инициализировать.|  
|[Метод target\_block::link\_source](../Topic/target_block::link_source%20Method.md)|Связывает указанный блок источника с данным объектом `target_block`.|  
|[Метод target\_block::process\_input\_messages](../Topic/target_block::process_input_messages%20Method.md)|Обрабатывает полученные сообщения.|  
|[Метод target\_block::process\_message](../Topic/target_block::process_message%20Method.md)|При переопределении в производном классе обрабатывает сообщение, которое ранее было принято данным объектом `target_block`.|  
|[Метод target\_block::propagate\_message](../Topic/target_block::propagate_message%20Method.md)|При переопределении в производном классе этот метод асинхронно передает сообщение из блока `ISource` этому объекту `target_block`.  Вызывается методом `propagate` при вызове исходного блока.|  
|[Метод target\_block::register\_filter](../Topic/target_block::register_filter%20Method.md)|Регистрирует метод фильтра, который будет вызван на каждое полученное сообщение.|  
|[Метод target\_block::remove\_sources](../Topic/target_block::remove_sources%20Method.md)|Unlinks все источники после ожидания завершения ожидающих операций асинхронной отправки.|  
|[Метод target\_block::send\_message](../Topic/target_block::send_message%20Method.md)|При переопределении в производном классе этот метод синхронно передает сообщение из блока `ISource` этому объекту `target_block`.  Вызывается методом `send` при вызове исходного блока.|  
|[Метод target\_block::sync\_send](../Topic/target_block::sync_send%20Method.md)|Синхронно отправляет сообщение для обработки.|  
|[Метод target\_block::unlink\_source](../Topic/target_block::unlink_source%20Method.md)|Удаляет связь указанного блока источника с данным объектом `target_block`.|  
|[Метод target\_block::unlink\_sources](../Topic/target_block::unlink_sources%20Method.md)|Удаляет связи всех блоков источника с данным объектом `target_block`. \(Переопределяет [ITarget::unlink\_sources](../Topic/ITarget::unlink_sources%20Method.md).\)|  
|[Метод target\_block::wait\_for\_async\_sends](../Topic/target_block::wait_for_async_sends%20Method.md)|Ожидает завершения всех асинхронных операций распространения.|  
  
## Иерархия наследования  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 `target_block`  
  
## Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс ITarget](../../../parallel/concrt/reference/itarget-class.md)