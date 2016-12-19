---
title: "CInterfaceArray Class | Microsoft Docs"
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
  - "ATL.CInterfaceArray"
  - "CInterfaceArray"
  - "ATL::CInterfaceArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInterfaceArray class"
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CInterfaceArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет методы полезны при создании массива указателей интерфейса модели COM.  
  
## Синтаксис  
  
```  
  
      template<  
   class I,  
   const IID* piid = & __uuidof( I )  
>  
class CInterfaceArray : public CAtlArray<  
   ATL::CComQIPtr< I, piid >,  
   CComQIPtrElementTraits< I, piid >  
>  
```  
  
#### Параметры  
 `I`  
 Интерфейс модели COM, указывающие тип указателя, которую необходимо сохранить.  
  
 `piid`  
 Указатель на идентификатор IID `I`.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CInterfaceArray::CInterfaceArray](../Topic/CInterfaceArray::CInterfaceArray.md)|Конструктор массива интерфейса.|  
  
## Заметки  
 Этот класс предоставляет конструктор и производные методы для создания массива указателей интерфейса модели COM.  Используйте [CInterfaceList](../Topic/CInterfaceList%20Class.md), если список является обязательным.  
  
 Дополнительные сведения см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Иерархия наследования  
 `CAtlArray`  
  
 `CInterfaceArray`  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [CAtlArray Class](../../atl/reference/catlarray-class.md)   
 [CComQIPtr Class](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits Class](../Topic/CComQIPtrElementTraits%20Class.md)   
 [Class Overview](../../atl/atl-class-overview.md)