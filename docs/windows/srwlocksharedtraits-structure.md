---
title: "Структура SRWLockSharedTraits | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLockSharedTraits - структура"
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура SRWLockSharedTraits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает общие характеристики класса SRWLock в режиме совмещаемой блокировки.  
  
## Синтаксис  
  
```  
struct SRWLockSharedTraits;  
```  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Name|Описание|  
|----------|--------------|  
|`Type`|Синоним для указателя на класс [SRWLOCK](../windows/srwlock-class.md).|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод SRWLockSharedTraits::GetInvalidValue](../Topic/SRWLockSharedTraits::GetInvalidValue%20Method.md)|Извлекает объект SRWLockSharedTraits, который всегда является недопустимым.|  
|[Метод SRWLockSharedTraits::Unlock](../Topic/SRWLockSharedTraits::Unlock%20Method.md)|Выпускает отдельный элемент управления указанного объекта SRWLock.|  
  
## Иерархия наследования  
 `SRWLockSharedTraits`  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)