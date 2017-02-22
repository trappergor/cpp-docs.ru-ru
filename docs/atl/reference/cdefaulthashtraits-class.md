---
title: "CDefaultHashTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDefaultHashTraits"
  - "ATL.CDefaultHashTraits<T>"
  - "ATL::CDefaultHashTraits<T>"
  - "ATL.CDefaultHashTraits"
  - "ATL::CDefaultHashTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultHashTraits class"
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CDefaultHashTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит статическую функцию для расчета значений хэша.  
  
## Синтаксис  
  
```  
  
      template<  
   typename T  
>  
class CDefaultHashTraits  
```  
  
#### Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDefaultHashTraits::Hash](../Topic/CDefaultHashTraits::Hash.md)|\(Статический\) Эта функция вызывается для вычисления значения хэша для заданного элемента.|  
  
## Заметки  
 Этот класс содержит единственную статическую функцию, которая возвращает хэш\-значение для заданного элемента.  Этот класс используется [класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Дополнительные сведения см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)