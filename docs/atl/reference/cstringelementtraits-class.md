---
title: "CStringElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CStringElementTraits<T>"
  - "ATL::CStringElementTraits<T>"
  - "CStringElementTraits"
  - "ATL.CStringElementTraits"
  - "ATL::CStringElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringElementTraits class"
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CStringElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет статические функции, используемые классами коллекций хранения объектов `CString`.  
  
## Синтаксис  
  
```  
  
      template<  
   typename T   
>  
class CStringElementTraits  
```  
  
#### Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[CStringElementTraits::INARGTYPE](../Topic/CStringElementTraits::INARGTYPE.md)|Тип данных, используемый для суммирующих элементов к объекту класса коллекции.|  
|[CStringElementTraits::OUTARGTYPE](../Topic/CStringElementTraits::OUTARGTYPE.md)|Тип данных, используемый для извлечения элементов из объекта класса коллекции.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CStringElementTraits::CompareElements](../Topic/CStringElementTraits::CompareElements.md)|\(Статический\) Эта функция вызывается для сравнения строк на равенство 2 элемента.|  
|[CStringElementTraits::CompareElementsOrdered](../Topic/CStringElementTraits::CompareElementsOrdered.md)|\(Статический\) Эта функция вызывается для сравнения 2 элемента строки.|  
|[CStringElementTraits::CopyElements](../Topic/CStringElementTraits::CopyElements.md)|\(Статический\) Эта функция вызывается для копирования элементов `CString`, хранящиеся в объекте класса коллекции.|  
|[CStringElementTraits::Hash](../Topic/CStringElementTraits::Hash.md)|\(Статический\) Эта функция вызывается для вычисления значения хэша для заданного элемента строки.|  
|[CStringElementTraits::RelocateElements](../Topic/CStringElementTraits::RelocateElements.md)|\(Статический\) Эта функция вызывается, чтобы переместить элементы `CString`, хранящиеся в объекте класса коллекции.|  
  
## Заметки  
 Этот класс предоставляет статические функции для копирования, перемещения и сравнения строк и для создания хэш\-значения.  Эти функции полезны при использовании класса коллекции для хранения на основе строка\- данные.  Используйте [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) при обращение\- сравнения без учета требуются.  Используйте [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), если строковый объект быть общанным с как ссылка.  
  
 Дополнительные сведения см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Требования  
 **Header:** cstringt.h  
  
## См. также  
 [CElementTraitsBase Class](../../atl/reference/celementtraitsbase-class.md)   
 [CStringElementTraitsI Class](../../atl/reference/cstringelementtraitsi-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)