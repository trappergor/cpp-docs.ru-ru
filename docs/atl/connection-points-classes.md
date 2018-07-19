---
title: Классы точки подключения (ATL) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.connection
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], connection points
- connection points classes
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d458fb5805b99c8dcc5cc25abc9f85f88f08e92
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957661"
---
# <a name="connection-points-classes"></a>Классы точек подключения
Следующие классы обеспечивают поддержку точек подключения.  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) реализует контейнер точек соединения.  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) реализует точку соединения.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) реализует объект точки подключения, представляющий [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) интерфейс.  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) управляет неограниченное количество подключений между точкой подключения и его приемников.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) управляет фиксированного числа подключений между точки подключения и его приемников.  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) уведомляет приемником клиента, который свойство объекта был изменен или изменением.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) обеспечивает поддержку точек подключения для ATL COM-объекта. Эти соединения будут сопоставлены с картой приемника событий, предоставляемый COM-объект.  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) сопоставить работает вместе с приемником событий в классе события соответствующим функциям обработки.  
  
## <a name="related-articles"></a>Связанные статьи  
 [Точки подключения](../atl/atl-connection-points.md)  
  
 [Обработка событий и ATL](../atl/event-handling-and-atl.md)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../atl/atl-class-overview.md)   
 [Макросы точки подключения](../atl/reference/connection-point-macros.md)   
 [Глобальные функции точек подключения](../atl/reference/connection-point-global-functions.md)

