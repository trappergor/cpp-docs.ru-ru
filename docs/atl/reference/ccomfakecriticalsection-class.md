---
title: "CComFakeCriticalSection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComFakeCriticalSection"
  - "CComFakeCriticalSection"
  - "ATL::CComFakeCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComFakeCriticalSection class"
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComFakeCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет те же методы, что [CComCriticalSection](../Topic/CComCriticalSection%20Class.md), но не предоставляет критическую секцию.  
  
## Синтаксис  
  
```  
  
class CComFakeCriticalSection  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComFakeCriticalSection::Init](../Topic/CComFakeCriticalSection::Init.md)|Не выполняет никаких действий, так как ни одна из критической секции.|  
|[CComFakeCriticalSection::Lock](../Topic/CComFakeCriticalSection::Lock.md)|Не выполняет никаких действий, так как ни одна из критической секции.|  
|[CComFakeCriticalSection::Term](../Topic/CComFakeCriticalSection::Term.md)|Не выполняет никаких действий, так как ни одна из критической секции.|  
|[CComFakeCriticalSection::Unlock](../Topic/CComFakeCriticalSection::Unlock.md)|Не выполняет никаких действий, так как ни одна из критической секции.|  
  
## Заметки  
 `CComFakeCriticalSection` используются методы, найденные в [CComCriticalSection](../Topic/CComCriticalSection%20Class.md).  Однако `CComFakeCriticalSection` не предоставляет критическую секцию. поэтому его методы не выполняют никаких действий.  
  
 Обычно используется `CComFakeCriticalSection` через имя `typedef` или `AutoCriticalSection` или `CriticalSection`.  При использовании [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) или [CComMultiThreadModelNoCS](../Topic/CComMultiThreadModelNoCS%20Class.md), обе ссылки этих имен `CComFakeCriticalSection``typedef`.  При использовании [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), они ссылаются на [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) и `CComCriticalSection` соответственно.  
  
## Требования  
 **Header:** atlcore.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)