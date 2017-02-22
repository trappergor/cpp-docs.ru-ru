---
title: "CComSimpleThreadAllocator Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComSimpleThreadAllocator"
  - "ATL::CComSimpleThreadAllocator"
  - "ATL.CComSimpleThreadAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL threads"
  - "ATL threads, выделение"
  - "CComSimpleThreadAllocator class"
  - "работа с потоками [ATL], selecting threads"
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComSimpleThreadAllocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс управляет выделение потоков для класса `CComAutoThreadModule`.  
  
## Синтаксис  
  
```  
  
class CComSimpleThreadAllocator  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComSimpleThreadAllocator::GetThread](../Topic/CComSimpleThreadAllocator::GetThread.md)|Выбирает поток.|  
  
## Заметки  
 `CComSimpleThreadAllocator` управляет выделение потоков для [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  `CComSimpleThreadAllocator::GetThread` просто задействует через каждый поток и возвращает следующее в последовательности.  
  
## Требования  
 **Header:**  atlbase.h  
  
## См. также  
 [CComApartment Class](../../atl/reference/ccomapartment-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)