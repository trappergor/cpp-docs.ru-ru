---
title: "ATL Connection Point Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL - библиотека, точки подключения"
  - "CComDynamicUnkArray class, connection point classes"
  - "CComUnkArray class, connection point classes"
  - "CFirePropNotifyEvent class"
  - "CFirePropNotifyEvent class, connection point classes"
  - "точки подключения [C++], ATL - классы"
ms.assetid: 9582ba71-7ace-4df4-9c9b-1b0636953efc
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL Connection Point Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотеки ATL используются следующие классы для поддержки точки подключения.  
  
-   [IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md) реализует точку подключения.  Идентификатор IID исходящего интерфейса, оно представляет передается в качестве параметра шаблона.  
  
-   [IConnectionPointContainerImpl](../Topic/IConnectionPointContainerImpl%20Class.md) реализован контейнер точки подключения и управляет список объектов `IConnectionPointImpl`.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) реализует точку подключения, представляющий интерфейс [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638).  
  
-   [CComDynamicUnkArray](../Topic/CComDynamicUnkArray%20Class.md) управляет произвольное число связь между точкой подключения и его приемники.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) управляет стандартное число подключений, как указано параметром шаблона.  
  
-   [CFirePropNotifyEvent](../Topic/CFirePropNotifyEvent%20Class.md) уведомляет приемник клиента, что свойство объекта изменилось или изменением.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) обеспечивает поддержку точек подключения для com\-объекта библиотеки ATL.  Эти точки подключения сопоставлены с сопоставлением приемника событий, предоставляемого данным COM\-объект.  
  
-   Рабочие [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) совместно с сопоставлением приемника событий в классе для направления события в соответствующее обработчик функции.  
  
## См. также  
 [Точка подключения](../atl/atl-connection-points.md)