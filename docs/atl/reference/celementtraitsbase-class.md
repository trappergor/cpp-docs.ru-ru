---
title: "CElementTraitsBase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CElementTraitsBase"
  - "ATL::CElementTraitsBase"
  - "ATL.CElementTraitsBase<T>"
  - "ATL::CElementTraitsBase<T>"
  - "ATL.CElementTraitsBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CElementTraitsBase class"
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CElementTraitsBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет копию и методы перемещения по умолчанию для коллекции классифицируют.  
  
## Синтаксис  
  
```  
  
      template<  
   typename T  
>  
class CElementTraitsBase  
```  
  
#### Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[CElementTraitsBase::INARGTYPE](../Topic/CElementTraitsBase::INARGTYPE.md)|Тип данных, используемый для суммирующих элементов к объекту класса коллекции.|  
|[CElementTraitsBase::OUTARGTYPE](../Topic/CElementTraitsBase::OUTARGTYPE.md)|Тип данных, используемый для извлечения элементов из объекта класса коллекции.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CElementTraitsBase::CopyElements](../Topic/CElementTraitsBase::CopyElements.md)|Вызывайте этот метод для копирования элементов, хранящихся в объекте класса коллекции.|  
|[CElementTraitsBase::RelocateElements](../Topic/CElementTraitsBase::RelocateElements.md)|Вызовите этот метод, чтобы переместить элементы, хранящиеся в объекте класса коллекции.|  
  
## Заметки  
 Этот базовый класс определяет методы для копирования и передислоцируя классифицируют элементов в коллекции.  Оно используется классами [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) и [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
 Дополнительные сведения см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)