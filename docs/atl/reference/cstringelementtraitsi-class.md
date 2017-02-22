---
title: "CStringElementTraitsI Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CStringElementTraitsI"
  - "CStringElementTraitsI"
  - "ATL.CStringElementTraitsI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringElementTraitsI class"
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CStringElementTraitsI Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет статические функции, связанные со строками, хранимые в объектах класса коллекции.  Он аналогичен [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), но выполняет сравнение без учета обращение\-.  
  
## Синтаксис  
  
```  
  
      template<  
   typename T,  
   class CharTraits = CDefaultCharTraits< T::XCHAR >  
>  
class CStringElementTraitsI : public CElementTraitsBase< T >  
```  
  
#### Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[CStringElementTraitsI::INARGTYPE](../Topic/CStringElementTraitsI::INARGTYPE.md)|Тип данных, используемый для суммирующих элементов к объекту класса коллекции.|  
|[CStringElementTraitsI::OUTARGTYPE](../Topic/CStringElementTraitsI::OUTARGTYPE.md)|Тип данных, используемый для извлечения элементов из объекта класса коллекции.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CStringElementTraitsI::CompareElements](../Topic/CStringElementTraitsI::CompareElements.md)|Вызовите эта статическая функция, используемая для сравнения строк на равенство 2 элемента без учета разницы в случае.|  
|[CStringElementTraitsI::CompareElementsOrdered](../Topic/CStringElementTraitsI::CompareElementsOrdered.md)|Вызовите эта статическая функция, используемая для сравнения 2 элемента строки, игнорируя различия в случае.|  
|[CStringElementTraitsI::Hash](../Topic/CStringElementTraitsI::Hash.md)|Вызовите эта статическая функция для вычисления значения хэша для заданного элемента строки.|  
  
## Заметки  
 Этот класс предоставляет статические функции для сравнения строк и для создания хэш\-значения.  Эти функции полезны при использовании класса коллекции для хранения на основе строка\- данные.  Используйте [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), когда объект строки быть с общанный с как ссылка.  
  
 Дополнительные сведения см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Иерархия наследования  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringElementTraitsI`  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [CElementTraitsBase Class](../../atl/reference/celementtraitsbase-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CStringElementTraits Class](../../atl/reference/cstringelementtraits-class.md)