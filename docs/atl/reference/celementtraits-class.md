---
title: "CElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CElementTraits<T>"
  - "ATL::CElementTraits"
  - "ATL.CElementTraits"
  - "ATL::CElementTraits<T>"
  - "CElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CElementTraits class"
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс используется классами коллекций, чтобы обеспечить методы и функции для перемещения, копирования, сравнения и хэширование операций.  
  
## Синтаксис  
  
```  
  
      template<  
   typename T  
>  
class CElementTraits : public CDefaultElementTraits< T >  
```  
  
#### Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## Заметки  
 По умолчанию этот класс предоставляет статические функции и методы для перемещения, копирования, сравнения и хэширование элементов, хранящихся в классе коллекции объект.  `CElementTraits` указан в качестве поставщика по умолчанию этих операций классами [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../Topic/CAtlList%20Class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md) и [CRBTree](../../atl/reference/crbtree-class.md) коллекции.  
  
 Реализации по умолчанию будут достаточным для простых типов данных, но если классы коллекций используются для хранения более сложных объектов, функции и методы должны быть переопределитьы пользователь\- предоставленными реализациями.  
  
 Дополнительные сведения см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)