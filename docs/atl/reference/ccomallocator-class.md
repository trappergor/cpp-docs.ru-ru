---
title: "CComAllocator Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComAllocator"
  - "ATL::CComAllocator"
  - "CComAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAllocator class"
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComAllocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для управления ими память с помощью процедуры памяти модели COM.  
  
## Синтаксис  
  
```  
  
class CComAllocator  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComAllocator::Allocate](../Topic/CComAllocator::Allocate.md)|Вызовите статический метод, чтобы выделить память.|  
|[CComAllocator::Free](../Topic/CComAllocator::Free.md)|Вызовите статический метод, чтобы освободить выделенную память.|  
|[CComAllocator::Reallocate](../Topic/CComAllocator::Reallocate.md)|Вызовите статический метод для reallocate память.|  
  
## Заметки  
 Этот класс используется [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), чтобы предоставить подпрограммы для выделения памяти модели COM.  Аналогом классифицируют, [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), содержат одни и те же методы с помощью процедуры CRT.  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [CComHeapPtr Class](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator Class](../../atl/reference/ccrtallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)