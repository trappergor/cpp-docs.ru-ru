---
title: "Connection Points Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.connection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы [C++], точки подключения"
  - "connection points classes"
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Connection Points Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие классы предоставляют поддержку для точки подключения.  
  
-   [IConnectionPointContainerImpl](../Topic/IConnectionPointContainerImpl%20Class.md) реализован контейнер точки подключения.  
  
-   [IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md) реализует точку подключения.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) реализует точку подключения, представляющий интерфейс [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638).  
  
-   [CComDynamicUnkArray](../Topic/CComDynamicUnkArray%20Class.md) управляет неограниченные связь между точкой подключения и его приемники.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) управляет фиксированное число связь между точкой подключения и его приемники.  
  
-   [CFirePropNotifyEvent](../Topic/CFirePropNotifyEvent%20Class.md) уведомляет приемник клиента, что свойство объекта изменилось или изменением.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) обеспечивает поддержку точек подключения для com\-объекта библиотеки ATL.  Эти точки подключения сопоставлены с сопоставлением приемника событий, предоставляемого данным COM\-объект.  
  
-   Рабочие [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) совместно с сопоставлением приемника событий в классе для направления события в соответствующее обработчик функции.  
  
## Связанные статьи  
 [Точки соединения](../atl/atl-connection-points.md)  
  
 [Обработка событий и библиотеки ATL](../Topic/Event%20Handling%20and%20ATL.md)  
  
## См. также  
 [Class Overview](../atl/atl-class-overview.md)   
 [Connection Point Macros](../atl/reference/connection-point-macros.md)   
 [Connection Point Global Functions](../Topic/Connection%20Point%20Global%20Functions.md)