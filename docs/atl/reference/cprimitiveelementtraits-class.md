---
title: "CPrimitiveElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CPrimitiveElementTraits<T>"
  - "CPrimitiveElementTraits"
  - "ATL.CPrimitiveElementTraits"
  - "ATL::CPrimitiveElementTraits<T>"
  - "ATL::CPrimitiveElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrimitiveElementTraits class"
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CPrimitiveElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет методы по умолчанию и функции для класса коллекции структурированного типов\-примитивов.  
  
## Синтаксис  
  
```  
  
      template<  
   typename T  
> class CPrimitiveElementTraits :   
   public CDefaultElementTraits< T >  
```  
  
#### Параметры  
 `T`  
 Тип данных, хранимых в объекте класса коллекции.  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[CPrimitiveElementTraits::INARGTYPE](../Topic/CPrimitiveElementTraits::INARGTYPE.md)|Тип данных, используемый для суммирующих элементов к объекту класса коллекции.|  
|[CPrimitiveElementTraits::OUTARGTYPE](../Topic/CPrimitiveElementTraits::OUTARGTYPE.md)|Тип данных, используемый для извлечения элементов из объекта класса коллекции.|  
  
## Заметки  
 По умолчанию этот класс предоставляет статические функции и методы для перемещения, копирования, сравнения и хэширование элементов простого типа данных, хранящихся в классе коллекции объект.  
  
 Дополнительные сведения см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Иерархия наследования  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CPrimitiveElementTraits`  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)