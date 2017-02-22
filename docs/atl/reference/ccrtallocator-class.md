---
title: "CCRTAllocator Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCRTAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCRTAllocator class"
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CCRTAllocator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для управления ими память с помощью процедуры памяти CRT.  
  
## Синтаксис  
  
```  
  
class ATL::CCRTAllocator  
  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CCRTAllocator::Allocate](../Topic/CCRTAllocator::Allocate.md)|\(Статический\) Вызовите этот метод, чтобы выделить память.|  
|[CCRTAllocator::Free](../Topic/CCRTAllocator::Free.md)|\(Статический\) Вызовите этот метод, чтобы освободить память.|  
|[CCRTAllocator::Reallocate](../Topic/CCRTAllocator::Reallocate.md)|\(Статический\) Вызовите этот метод, чтобы reallocate память.|  
  
## Заметки  
 Этот класс используется [CHeapPtr](../../atl/reference/cheapptr-class.md), чтобы предоставить подпрограммы выделения памяти CRT.  Аналогом классифицируют, [CComAllocator](../../atl/reference/ccomallocator-class.md), содержат одни и те же методы с помощью процедуры модели COM.  
  
## Требования  
 **Header:** atlcore.h  
  
## См. также  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CComAllocator Class](../../atl/reference/ccomallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)