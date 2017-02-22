---
title: "CAutoPtrList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoPtrList"
  - "CAutoPtrList"
  - "ATL.CAutoPtrList"
  - "ATL::CAutoPtrList<E>"
  - "ATL.CAutoPtrList<E>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoPtrList class"
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CAutoPtrList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет методы полезных для построения списка умных указателей.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template<  
typename E  
>  
class CAutoPtrList : public CAtlList<  
ATL::CAutoPtr< E>,  
CAutoPtrElementTraits< E>  
>  
```  
  
#### Параметры  
 `E`  
 Тип указателя.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAutoPtrList::CAutoPtrList](../Topic/CAutoPtrList::CAutoPtrList.md)|Конструктор.|  
  
## Заметки  
 Этот класс предоставляет конструктор наследуется от [CAtlList](../Topic/CAtlList%20Class.md) и методы и [CAutoPtrElementTraits](../Topic/CAutoPtrElementTraits%20Class.md) для содействия создания объекта списка хранения интеллектуальные указатели.  Класс [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) обеспечивает аналогичную функцию для объекта массива.  
  
 Дополнительные сведения см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Иерархия наследования  
 [CAtlList](../Topic/CAtlList%20Class.md)  
  
 `CAutoPtrList`  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [CAtlList Class](../Topic/CAtlList%20Class.md)   
 [CAutoPtrElementTraits Class](../Topic/CAutoPtrElementTraits%20Class.md)   
 [Class Overview](../../atl/atl-class-overview.md)