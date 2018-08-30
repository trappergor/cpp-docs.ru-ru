---
title: Классы точки подключения ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CFirePropNotifyEvent class, connection point classes
- connection points [C++], ATL classes
- ATL, connection points
- CComDynamicUnkArray class, connection point classes
- CFirePropNotifyEvent class
- CComUnkArray class, connection point classes
ms.assetid: 9582ba71-7ace-4df4-9c9b-1b0636953efc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 289ff7ae7db1abd6a0a19577a2c567b462a2910e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201404"
---
# <a name="atl-connection-point-classes"></a>Классы точки подключения библиотеки ATL
ATL используются следующие классы для поддержки точек подключения:  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) реализует точку соединения. Идентификатор IID исходящего интерфейса, который он представляет передается в качестве параметра шаблона.  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) реализует контейнер точек соединения и управляет списком `IConnectionPointImpl` объектов.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) реализует объект точки подключения, представляющий [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) интерфейс.  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) управляет произвольное число подключений между точкой подключения и его приемников.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) управляет определенного количества подключений, как указано в параметре шаблона.  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) уведомляет приемником клиента, который свойство объекта был изменен или изменением.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) обеспечивает поддержку точек подключения для ATL COM-объекта. Эти соединения будут сопоставлены с картой приемника событий, предоставляемый COM-объект.  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) работает совместно с картой приемника событий в классе события соответствующим функциям обработки.  
  
## <a name="see-also"></a>См. также  
 [Точка подключения](../atl/atl-connection-points.md)

