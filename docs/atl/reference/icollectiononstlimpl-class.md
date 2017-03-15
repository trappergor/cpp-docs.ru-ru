---
title: "ICollectionOnSTLImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.ICollectionOnSTLImpl"
  - "ATL::ICollectionOnSTLImpl"
  - "ICollectionOnSTLImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICollectionOnSTLImpl class"
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# ICollectionOnSTLImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет методы, используемые классом коллекции.  
  
## Синтаксис  
  
```  
  
      template <  
   class T,  
   class CollType,  
   class ItemType,  
   class CopyItem,  
   class EnumType  
>  
class ICollectionOnSTLImpl :  
   public T  
```  
  
#### Параметры  
 `T`  
 Интерфейс коллекции модели COM.  
  
 `CollType`  
 Класс контейнеров STL.  
  
 *ItemType*  
 Тип элемента, предоставляемый интерфейсом контейнера.  
  
 *CopyItem*  
 [класс политики копирования](../Topic/ATL%20Copy%20Policy%20Classes.md).  
  
 *EnumType*  
 [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) совместимы класс перечислителя.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[ICollectionOnSTLImpl::get\_\_NewEnum](../Topic/ICollectionOnSTLImpl::get__NewEnum.md)|Возвращает объект перечислителя для коллекции.|  
|[ICollectionOnSTLImpl::get\_Count](../Topic/ICollectionOnSTLImpl::get_Count.md)|Возвращает количество элементов в коллекции.|  
|[ICollectionOnSTLImpl::get\_Item](../Topic/ICollectionOnSTLImpl::get_Item.md)|Возвращает запрошенный элемент из коллекции.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[ICollectionOnSTLImpl::m\_coll](../Topic/ICollectionOnSTLImpl::m_coll.md)|Коллекция.|  
  
## Заметки  
 Этот класс обеспечивает реализацию методов интерфейса коллекции: 3 [get\_Count](../Topic/ICollectionOnSTLImpl::get_Count.md), [get\_Item](../Topic/ICollectionOnSTLImpl::get_Item.md) и [get\_\_NewEnum](../Topic/ICollectionOnSTLImpl::get__NewEnum.md).  
  
 Использовать этот класс.  
  
-   Определите \(или borrow\) интерфейс коллекции, который необходимо реализовать.  
  
-   Создайте производный класс от `ICollectionOnSTLImpl` специализации на основе этом интерфейсе коллекции.  
  
-   Используйте производный класс для реализации все методы интерфейса не обращанного `ICollectionOnSTLImpl` из коллекции.  
  
> [!NOTE]
>  Если интерфейс коллекции сдвоенный интерфейс, наследуйте класс от [IDispatchImpl](../../atl/reference/idispatchimpl-class.md), указав в качестве первого параметра `ICollectionOnSTLImpl` специализацию шаблона, если необходимо предоставить реализацию методов `IDispatch` библиотеки ATL.  
  
-   Добавление элементов в элемент [m\_coll](../Topic/ICollectionOnSTLImpl::m_coll.md) для заполнения коллекции.  
  
 Дополнительные сведения и примеры см. в разделе [Коллекции и перечислители библиотеки ATL](../../atl/atl-collections-and-enumerators.md).  
  
## Иерархия наследования  
 `T`  
  
 `ICollectionOnSTLImpl`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [Образец ATLCollections](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)