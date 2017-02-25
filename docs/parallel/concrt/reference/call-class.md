---
title: "Класс call | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::call"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "call - класс"
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс call
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Блок обмена сообщениями `call` — многоисточниковый, упорядоченный `target_block`, который вызывает заданную функцию при приеме сообщения.  
  
## Синтаксис  
  
```  
template<  
   class _Type,  
   class _FunctorType = std::tr1::function<void(_Type const&)>  
>  
class call : public target_block<multi_link_registry<ISource<_Type>>>;  
```  
  
#### Параметры  
 `_Type`  
 Тип полезных данных распространенных этому блоку сообщений.  
  
 `_FunctorType`  
 Сигнатура функций, которые может принимать этот блок.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор call::call](../Topic/call::call%20Constructor.md)|Перегружен.  Создает блок сообщений `call`.|  
|[Деструктор call::~call](../Topic/call::~call%20Destructor.md)|Уничтожает блок сообщений `call`.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод call::process\_input\_messages](../Topic/call::process_input_messages%20Method.md)|Выполняет заданную функцию для входящих сообщениях.|  
|[Метод call::process\_message](../Topic/call::process_message%20Method.md)|Обрабатывает сообщение, которое было принято этим блоком сообщений `call`.|  
|[Метод call::propagate\_message](../Topic/call::propagate_message%20Method.md)|Асинхронно передает сообщение из блока `ISource` в этот блок сообщений `call`.  Вызывается методом `propagate` при вызове исходного блока.|  
|[Метод call::send\_message](../Topic/call::send_message%20Method.md)|Синхронно передает сообщение из блока `ISource` в этот блок сообщений `call`.  Вызывается методом `send` при вызове исходного блока.|  
|[Метод call::supports\_anonymous\_source](../Topic/call::supports_anonymous_source%20Method.md)|Переопределяет метод `supports_anonymous_source`, чтобы показать, что данный блок может принимать сообщения, предоставляемые ему несвязанным источником. \(Переопределяет метод [ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md)\).|  
  
## Заметки  
 Для получения дополнительной информации см. [Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Иерархия наследования  
 [ITarget](../../../parallel/concrt/reference/itarget-class.md)  
  
 [target\_block](../../../parallel/concrt/reference/target-block-class.md)  
  
 `call`  
  
## Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс transformer](../../../parallel/concrt/reference/transformer-class.md)