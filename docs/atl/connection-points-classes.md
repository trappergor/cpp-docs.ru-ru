---
title: "Классы точки подключения (ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.connection
dev_langs: C++
helpviewer_keywords:
- classes [C++], connection points
- connection points classes
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ef188a5fc03a60c3481477d000662d595b7d4dd9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="connection-points-classes"></a>Классы точки подключения
Следующие классы обеспечивают поддержку точек подключения.  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) реализует контейнер точки подключения.  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) реализует точку соединения.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) реализует объект, представляющий точку подключения [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) интерфейса.  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) управляет неограниченное число подключений между точкой подключения и его журналах.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) управляет фиксированного числа подключений между точкой подключения и его приемники.  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) уведомляет приемником клиента, который свойство объекта был изменен или изменением.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) обеспечивает поддержку точек подключения для ATL COM-объекта. Эти соединения будут сопоставлены с картой приемника событий, предоставляемый COM-объект.  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) сопоставить работает вместе с приемником событий в классе направляет события соответствующим функциям обработки.  
  
## <a name="related-articles"></a>Связанные статьи  
 [Точки подключения](../atl/atl-connection-points.md)  
  
 [Обработка событий и ATL](../atl/event-handling-and-atl.md)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../atl/atl-class-overview.md)   
 [Макросы точки подключения](../atl/reference/connection-point-macros.md)   
 [Глобальные функции точек подключения](../atl/reference/connection-point-global-functions.md)

