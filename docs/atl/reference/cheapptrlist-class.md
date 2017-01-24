---
title: "CHeapPtrList Class | Microsoft Docs"
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
  - "ATL::CHeapPtrList"
  - "CHeapPtrList"
  - "ATL.CHeapPtrList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtrList class"
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHeapPtrList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет методы полезных для построения списка указателей кучи.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template<  
typename E,  
class Allocator = ATL::CCRTAllocator  
>  
class CHeapPtrList : public CAtlList<  
ATL::CHeapPtr< E, Allocator>,  
CHeapPtrElementTraits< E, Allocator>  
>  
```  
  
#### Параметры  
 `E`  
 Тип объекта, который необходимо сохранить в классе коллекции.  
  
 `Allocator`  
 Класс выделения памяти для использования.  Значение по умолчанию [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHeapPtrList::CHeapPtrList](../Topic/CHeapPtrList::CHeapPtrList.md)|Конструктор.|  
  
## Заметки  
 Этот класс предоставляет конструктор наследуется от [CAtlList](../Topic/CAtlList%20Class.md) и методы и [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) для содействия создания объекта класса коллекции хранения указателей кучи.  
  
## Иерархия наследования  
 [CAtlList](../Topic/CAtlList%20Class.md)  
  
 `CHeapPtrList`  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [CAtlList Class](../Topic/CAtlList%20Class.md)   
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrElementTraits Class](../../atl/reference/cheapptrelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)