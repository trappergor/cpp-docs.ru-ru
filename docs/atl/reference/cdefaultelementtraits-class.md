---
title: "CDefaultElementTraits Class | Microsoft Docs"
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
  - "ATL::CDefaultElementTraits<T>"
  - "ATL.CDefaultElementTraits"
  - "ATL::CDefaultElementTraits"
  - "ATL.CDefaultElementTraits<T>"
  - "CDefaultElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultElementTraits class"
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDefaultElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет методы по умолчанию и функции для коллекции классифицируют.  
  
## Синтаксис  
  
```  
  
      template<  
   typename T  
>  
class CDefaultElementTraits : public CElementTraitsBase< T >,  
   public CDefaultHashTraits< T >,  
   public CDefaultCompareTraits< T >  
```  
  
#### Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## Заметки  
 По умолчанию этот класс предоставляет статические функции и методы для перемещения, копирования, сравнения и хэширование элементов, хранящихся в классе коллекции объект.  Этот класс является производным от [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md) его функции и методы, [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md) и [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md) и используется [CElementTraits](../../atl/reference/celementtraits-class.md), [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md) и [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md).  
  
 Дополнительные сведения см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)