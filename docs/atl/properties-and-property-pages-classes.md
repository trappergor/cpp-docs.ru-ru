---
title: "Properties and Property Pages Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.properties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "свойства [ATL]"
  - "свойства [ATL], classes"
  - "страницы свойств, classes"
ms.assetid: 31616f98-69f8-48b2-8d58-b8e7d1c2b2d8
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Properties and Property Pages Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие свойства и страницы свойств поддержки классов:  
  
-   Возвращает или задает [CComDispatchDriver](../Topic/CComDispatchDriver.md) свойства объекта посредством указателя `IDispatch`.  
  
-   [CStockPropImpl](../atl/reference/cstockpropimpl-class.md) реализует стандартные свойства, поддерживаемые библиотеки ATL.  
  
-   [IPerPropertyBrowsingImpl](../Topic/IPerPropertyBrowsingImpl%20Class.md) обращается к сведениям на страницах свойств объекта.  
  
-   [IPersistPropertyBagImpl](../atl/reference/ipersistpropertybagimpl-class.md) хранит свойства объекта в клиент\- предоставляемом контейнере свойств.  
  
-   [IPropertyPageImpl](../atl/reference/ipropertypageimpl-class.md) управляет указанная страница свойств на странице свойств.  
  
-   [IPropertyPage2Impl](../atl/reference/ipropertypage2impl-class.md) аналогичное `IPropertyPageImpl`, но также позволяет клиенту выбрать конкретное свойство на странице свойств.  
  
-   [ISpecifyPropertyPagesImpl](../Topic/ISpecifyPropertyPagesImpl%20Class.md) возвращает значения clsid для страниц свойств, поддерживаемых объектом.  
  
## Связанные статьи  
 [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)  
  
 [Страницы свойств модели COM библиотеки ATL](../atl/atl-com-property-pages.md)  
  
## См. также  
 [Class Overview](../atl/atl-class-overview.md)   
 [Property Map Macros](../atl/reference/property-map-macros.md)