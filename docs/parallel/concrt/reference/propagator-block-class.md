---
title: "Класс propagator_block | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::propagator_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "propagator_block - класс"
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс propagator_block
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `propagator_block` является абстрактным базовым классом для блоков сообщений, которые одновременно исходные и целевые.  Объединяет функциональные возможности обоих классов `source_block` и `target_block`.  
  
## Синтаксис  
  
```  
template<  
   class _TargetLinkRegistry,  
   class _SourceLinkRegistry,  
   class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>  
>  
class propagator_block : public source_block<_TargetLinkRegistry, _MessageProcessorType>, public ITarget<typename _SourceLinkRegistry::type::source_type>;  
```  
  
#### Параметры  
 `_TargetLinkRegistry`  
 Реестр ссылок для использования для хранения целевых ссылок.  
  
 `_SourceLinkRegistry`  
 Реестр ссылок для использования для хранения исходных ссылок.  
  
 `_MessageProcessorType`  
 Тип процессора для обработки сообщений.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`source_iterator`|Тип итератора для `source_link_manager` для данного `propagator_block`.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор propagator\_block::propagator\_block](../Topic/propagator_block::propagator_block%20Constructor.md)|Создает объект `propagator_block`.|  
|[Деструктор propagator\_block::~propagator\_block](../Topic/propagator_block::~propagator_block%20Destructor.md)|Удаляет объект `propagator_block`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод propagator\_block::propagate](../Topic/propagator_block::propagate%20Method.md)|Асинхронно передает сообщение из исходного блока данному целевому блоку.|  
|[Метод propagator\_block::send](../Topic/propagator_block::send%20Method.md)|Синхронно вызывает сообщение на этот блок.  Вызывается блоком `ISource`.  По завершении этой функции сообщение уже будет распространено в блок.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод propagator\_block::decline\_incoming\_messages](../Topic/propagator_block::decline_incoming_messages%20Method.md)|Указывает блоку, что новые сообщения должны быть отклонены.|  
|[Метод propagator\_block::initialize\_source\_and\_target](../Topic/propagator_block::initialize_source_and_target%20Method.md)|Инициализирует базовый объект.  В частности, объект `message_processor` необходимо инициализировать.|  
|[Метод propagator\_block::link\_source](../Topic/propagator_block::link_source%20Method.md)|Связывает указанный блок источника с данным объектом `propagator_block`.|  
|[Метод propagator\_block::process\_input\_messages](../Topic/propagator_block::process_input_messages%20Method.md)|Обработка входного сообщения.  Это полезно только для блоков распространения, которые являются производными от source\_block \(Переопределяет [source\_block::process\_input\_messages](../Topic/source_block::process_input_messages%20Method.md)\).|  
|[Метод propagator\_block::propagate\_message](../Topic/propagator_block::propagate_message%20Method.md)|При переопределении в производном классе этот метод асинхронно передает сообщение из блока `ISource` этому объекту `propagator_block`.  Вызывается методом `propagate` при вызове исходного блока.|  
|[Метод propagator\_block::register\_filter](../Topic/propagator_block::register_filter%20Method.md)|Регистрирует метод фильтра, который будет вызван на каждое полученное сообщение.|  
|[Метод propagator\_block::remove\_network\_links](../Topic/propagator_block::remove_network_links%20Method.md)|Удаляет все исходные и целевые сетевые ссылки из этого объекта `propagator_block`.|  
|[Метод propagator\_block::send\_message](../Topic/propagator_block::send_message%20Method.md)|При переопределении в производном классе этот метод синхронно передает сообщение из блока `ISource` этому объекту `propagator_block`.  Вызывается методом `send` при вызове исходного блока.|  
|[Метод propagator\_block::unlink\_source](../Topic/propagator_block::unlink_source%20Method.md)|Удаляет связь указанного блока источника с данным объектом `propagator_block`.|  
|[Метод propagator\_block::unlink\_sources](../Topic/propagator_block::unlink_sources%20Method.md)|Удаляет связи всех блоков источника с данным объектом `propagator_block`. \(Переопределяет [ITarget::unlink\_sources](../Topic/ITarget::unlink_sources%20Method.md).\)|  
  
## Заметки  
 Чтобы избежать множественное наследование, класс `propagator_block` класс наследуется от класса `source_block` и абстрактного класса `ITarget`.  Большинство функциональных возможностей в классе `target_block` реплицируется здесь.  
  
## Иерархия наследования  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [source\_block](../Topic/source_block%20Class.md)  
  
 `propagator_block`  
  
## Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс source\_block](../Topic/source_block%20Class.md)   
 [Класс ITarget](../../../parallel/concrt/reference/itarget-class.md)