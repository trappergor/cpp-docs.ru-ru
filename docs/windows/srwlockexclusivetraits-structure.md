---
title: "Структура SRWLockExclusiveTraits | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SRWLockExclusiveTraits - структура"
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура SRWLockExclusiveTraits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает общие характеристики класса SRWLock в режиме эксклюзивной блокировки.  
  
## Синтаксис  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`Type`|Синоним для указателя на класс [SRWLOCK](../windows/srwlock-class.md).|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод SRWLockExclusiveTraits::GetInvalidValue](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|Извлекает объект SRWLockExclusiveTraits который всегда является недопустимым.|  
|[Метод SRWLockExclusiveTraits::Unlock](../windows/srwlockexclusivetraits-unlock-method.md)|Выпускает отдельный элемент управления указанного объекта SRWLock.|  
  
## Иерархия наследования  
 `SRWLockExclusiveTraits`  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)