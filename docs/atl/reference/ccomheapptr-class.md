---
title: "CComHeapPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComHeapPtr"
  - "ATL.CComHeapPtr<T>"
  - "ATL::CComHeapPtr<T>"
  - "CComHeapPtr"
  - "ATL.CComHeapPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComHeapPtr class"
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComHeapPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Интеллектуальное класс указателя для управления указатели кучи.  
  
## Синтаксис  
  
```  
  
      template<  
   typename T  
> class CComHeapPtr :  
   public CHeapPtr< T, CComAllocator >  
```  
  
#### Параметры  
 `T`  
 Тип объекта, который будет храниться в куче.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComHeapPtr::CComHeapPtr](../Topic/CComHeapPtr::CComHeapPtr.md)|Конструктор.|  
  
## Заметки  
 `CComHeapPtr` является производным от `CHeapPtr`, но польз [CComAllocator](../../atl/reference/ccomallocator-class.md) выделить память с помощью процедуры модели COM.  См. раздел [CHeapPtr](../../atl/reference/cheapptr-class.md) и [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) для методов, доступных.  
  
## Иерархия наследования  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md)  
  
 `CComHeapPtr`  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrBase Class](../../atl/reference/cheapptrbase-class.md)   
 [CComAllocator Class](../../atl/reference/ccomallocator-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)