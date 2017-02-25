---
title: "Класс ISource | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::ISource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISource - класс"
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс ISource
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `ISource` является интерфейсом для всех исходных блоков.  Блоки источников распространяют сообщения блокам `ITarget`.  
  
## Синтаксис  
  
```  
template<  
   class _Type  
>  
class ISource;  
```  
  
#### Параметры  
 `_Type`  
 Тип данных полезных данных внутри сообщений, создаваемых исходным блоком.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Name|Описание|  
|----------|--------------|  
|`source_type`|Псевдоним типа для `_Type`.|  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Деструктор ISource::~ISource](../Topic/ISource::~ISource%20Destructor.md)|Уничтожает объект `ISource`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод ISource::accept](../Topic/ISource::accept%20Method.md)|При переопределении в производном классе, принимает сообщение, которое было предложено этим блоком `ISource`, передавая владение вызывающему объекту.|  
|[Метод ISource::acquire\_ref](../Topic/ISource::acquire_ref%20Method.md)|При переопределении в производном классе получает значение счетчика ссылок на этот блок `ISource`, чтобы предотвратить удаление.|  
|[Метод ISource::consume](../Topic/ISource::consume%20Method.md)|При переопределении в производном классе получает сообщение, ранее предлагаемое этим блоком `ISource` и успешно зарезервированные целевым объектом, передавая владение вызывающему объекту.|  
|[Метод ISource::link\_target](../Topic/ISource::link_target%20Method.md)|При переопределении в производном классе связывает целевой блок с этим блоком `ISource`.|  
|[Метод ISource::release](../Topic/ISource::release%20Method.md)|При переопределении в производном классе освобождает предыдущее успешное резервирование сообщения.|  
|[Метод ISource::release\_ref](../Topic/ISource::release_ref%20Method.md)|При переопределении в производном классе освобождает значение счетчика ссылок на этот блок `ISource`.|  
|[Метод ISource::reserve](../Topic/ISource::reserve%20Method.md)|При переопределении в производном классе резервирует сообщение, которое ранее было предложено данным блоком `ISource`.|  
|[Метод ISource::unlink\_target](../Topic/ISource::unlink_target%20Method.md)|При переопределении в производном классе удаляет связь целевого блока с этим блоком `ISource`, если тот был ранее связан.|  
|[Метод ISource::unlink\_targets](../Topic/ISource::unlink_targets%20Method.md)|При переопределении в производном классе удаляет связь всех целевых блоков с этим блоком `ISource`.|  
  
## Заметки  
 Для получения дополнительной информации см. [Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Иерархия наследования  
 `ISource`  
  
## Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс ITarget](../../../parallel/concrt/reference/itarget-class.md)