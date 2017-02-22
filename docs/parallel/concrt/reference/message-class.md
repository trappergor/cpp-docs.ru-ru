---
title: "Класс message | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::message"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message - класс"
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс message
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Основной конверт сообщения, содержащий полезную нагрузку данных, передаваемую между блоками обмена сообщениями.  
  
## Синтаксис  
  
```  
template<  
   class _Type  
>  
class message : public ::Concurrency::details::_Runtime_object;  
```  
  
#### Параметры  
 `_Type`  
 Тип данных полезных данных в сообщении.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Name|Описание|  
|----------|--------------|  
|`type`|Псевдоним типа для `_Type`.|  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор message::message](../Topic/message::message%20Constructor.md)|Перегружен.  Создает объект `message`.|  
|[Деструктор message::~message](../Topic/message::~message%20Destructor.md)|Уничтожает объект `message`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод message::add\_ref](../Topic/message::add_ref%20Method.md)|Добавляет значение счетчика ссылок для объекта `message`.  Используется для блоков сообщений, которым нужен подсчет ссылок, чтобы определять времена жизни сообщений.|  
|[Метод message::msg\_id](../Topic/message::msg_id%20Method.md)|Возвращает идентификатор объекта `message`.|  
|[Метод message::remove\_ref](../Topic/message::remove_ref%20Method.md)|Вычитает из значение счетчика ссылок для объекта `message`.  Используется для блоков сообщений, которым нужен подсчет ссылок, чтобы определять времена жизни сообщений.|  
  
### Открытые члены данных  
  
|Name|Описание|  
|----------|--------------|  
|[Элемент данных message::payload](../Topic/message::payload%20Data%20Member.md)|Полезная нагрузка объекта `message`.|  
  
## Заметки  
 Для получения дополнительной информации см. [Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Иерархия наследования  
 `message`  
  
## Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)