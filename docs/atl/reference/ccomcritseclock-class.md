---
title: "CComCritSecLock Class | Microsoft Docs"
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
  - "ATL::CComCritSecLock"
  - "ATL.CComCritSecLock<TLock>"
  - "ATL::CComCritSecLock<TLock>"
  - "ATL.CComCritSecLock"
  - "CComCritSecLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCritSecLock class"
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComCritSecLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для блокирования и разблокирования объект критической секции.  
  
## Синтаксис  
  
```  
  
      template<  
   class TLock  
> class CComCritSecLock  
```  
  
#### Параметры  
 *TLock*  
 Разблокированный объект, который требуется блокировать и.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComCritSecLock::CComCritSecLock](../Topic/CComCritSecLock::CComCritSecLock.md)|Конструктор.|  
|[CComCritSecLock::~CComCritSecLock](../Topic/CComCritSecLock::~CComCritSecLock.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComCritSecLock::Lock](../Topic/CComCritSecLock::Lock.md)|Этот метод вызывается для блокирования объект критической секции.|  
|[CComCritSecLock::Unlock](../Topic/CComCritSecLock::Unlock.md)|Вызовите этот метод, чтобы Разблокировать объект критической секции.|  
  
## Заметки  
 Этот класс используется для блокирования и разблокирования объекты в более безопасным способом, чем с [класс CComCriticalSection](../Topic/CComCriticalSection%20Class.md) или [класс CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [CComCriticalSection Class](../Topic/CComCriticalSection%20Class.md)   
 [CComAutoCriticalSection Class](../../atl/reference/ccomautocriticalsection-class.md)