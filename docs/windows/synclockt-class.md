---
title: "Класс SyncLockT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockT - класс"
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Класс SyncLockT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockT;  
```  
  
#### Параметры  
 `SyncTraits`  
 Тип, который может принимать ресурс во владение.  
  
## Примечания  
 Представляет собой тип, который может получать ресурс в монопольное или совместное владение.  
  
 Класс SyncLockT используется, например, чтобы помочь реализовать класс [SRWLock](../windows/srwlock-class.md).  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор SyncLockT::SyncLockT](../Topic/SyncLockT::SyncLockT%20Constructor.md)|Инициализирует новый экземпляр класса SyncLockT.|  
|[Деструктор SyncLockT::~SyncLockT](../windows/synclockt-tilde-synclockt-destructor.md)|Деинициализирует экземпляр класса SyncLockT.|  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор SyncLockT::SyncLockT](../Topic/SyncLockT::SyncLockT%20Constructor.md)|Инициализирует новый экземпляр класса SyncLockT.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод SyncLockT::IsLocked](../windows/synclockt-islocked-method.md)|Указывает, владеет ли текущий объект SyncLockT ресурсом; иными словами, объект SyncLockT *блокирован*.|  
|[Метод SyncLockT::Unlock](../windows/synclockt-unlock-method.md)|Освобождает управление ресурсом, удерживаемого текущим объектом SyncLockT, если таковые имеются.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[Элемент данных SyncLockT::sync\_](../Topic/SyncLockT::sync_%20Data%20Member.md)|Удерживает основной ресурс, представленный классом SyncLockT.|  
  
## Иерархия наследования  
 `SyncLockT`  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers::Details](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [Класс SRWLock](../windows/srwlock-class.md)