---
title: "Класс EventSource | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventSource - класс"
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс EventSource
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет событие.  Функции\-члены EventSource добавляют, удаляют и вызывают обработчики событий.  
  
## Синтаксис  
  
```  
template<  
   typename TDelegateInterface  
>  
class EventSource;  
```  
  
#### Параметры  
 `TDelegateInterface`  
 Интерфейс к делегату, представляющему обработчик событий.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор EventSource::EventSource](../windows/eventsource-eventsource-constructor.md)|Инициализирует новый экземпляр класса EventSource.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод EventSource::Add](../windows/eventsource-add-method.md)|Добавляет обработчик событий, представленный указанным интерфейсом делегата, к набору обработчиков событий для текущего объекта EventSource.|  
|[Метод EventSource::GetSize](../windows/eventsource-getsize-method.md)|Извлекает число обработчиков событий, связанных с текущим объектом EventSource|  
|[Метод EventSource::InvokeAll](../windows/eventsource-invokeall-method.md)|Вызывает каждый обработчик событий, связанный с текущим объектом EventSource, использующим указанные типы аргумента и аргументы.|  
|[Метод EventSource::Remove](../Topic/EventSource::Remove%20Method.md)|Удаляет обработчик событий, представленный заданным токеном регистрации событий из набора обработчиков событий, связанных с текущим объектом EventSource.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[Элемент данных EventSource::addRemoveLock\_](../windows/eventsource-addremovelock-data-member.md)|Синхронизирует доступ к массиву [targets\_](../Topic/EventSource::targets_%20Data%20Member.md) при добавлении, удалении или вызове обработчиков событий.|  
|[Элемент данных EventSource::targets\_](../Topic/EventSource::targets_%20Data%20Member.md)|Массив из одного или нескольких обработчиков событий.|  
|[Элемент данных EventSource::targetsPointerLock\_](../windows/eventsource-targetspointerlock-data-member.md)|Синхронизирует доступ к внутренним членам данных, даже при добавлении, удалении или вызове обработчиков событий для этого EventSource.|  
  
## Иерархия наследования  
 `EventSource`  
  
## Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)