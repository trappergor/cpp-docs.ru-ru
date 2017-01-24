---
title: "Класс ITarget | Microsoft Docs"
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
  - "agents/concurrency::ITarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITarget - класс"
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
caps.latest.revision: 22
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс ITarget
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `ITarget` является интерфейсом для всех целевых блоков.  Целевые блоки потребляют сообщения, предлагаемые им блоками `ISource`.  
  
## Синтаксис  
  
```  
template<  
   class _Type  
>  
class ITarget;  
```  
  
#### Параметры  
 `_Type`  
 Тип данных полезных данных внутри сообщений, принимаемых целевым блоком.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`filter_method`|Сигнатура любого метода, используемого блоком, который возвращает значение `bool`, чтобы определить, следует ли принять предложенное сообщение.|  
|`type`|Псевдоним типа для `_Type`.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Деструктор ITarget::~ITarget](../Topic/ITarget::~ITarget%20Destructor.md)|Уничтожает объект `ITarget`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод ITarget::propagate](../Topic/ITarget::propagate%20Method.md)|При переопределении в производном классе асинхронно передает сообщение из исходного блока этому блоку целевому.|  
|[Метод ITarget::send](../Topic/ITarget::send%20Method.md)|При переопределении в производном классе синхронно передает сообщение целевому блоку.|  
|[Метод ITarget::supports\_anonymous\_source](../Topic/ITarget::supports_anonymous_source%20Method.md)|При переопределении в производном классе возвращает значение true или false в зависимости от того, принимает ли блок сообщений предоставляемые не связанным с ним источником сообщения.  Если переопределенный метод возвращает `true`, целевой объект не может отложить предложенное сообщение, так как использование отложенного сообщения позднее требует, чтобы источник был определен в реестре ссылок источников.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод ITarget::link\_source](../Topic/ITarget::link_source%20Method.md)|При переопределении в производном классе связывает указанный целевой блок с этим блоком `ITarget`.|  
|[Метод ITarget::unlink\_source](../Topic/ITarget::unlink_source%20Method.md)|При переопределении в производном классе удаляет связь указанного целевого блока с этим блоком `ITarget`.|  
|[Метод ITarget::unlink\_sources](../Topic/ITarget::unlink_sources%20Method.md)|При переопределении в производном классе удаляет связь всех исходных блоков с этим блоком `ITarget`.|  
  
## Заметки  
 Для получения дополнительной информации см. [Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Иерархия наследования  
 `ITarget`  
  
## Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс ISource](../../../parallel/concrt/reference/isource-class.md)