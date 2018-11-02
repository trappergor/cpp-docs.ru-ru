---
title: Точки подключения классов (ATL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vc.atl.connection
helpviewer_keywords:
- classes [C++], connection points
- connection points classes
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
ms.openlocfilehash: 4965e5e371bd96903cad4d7f1e2b0ce3216107ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593977"
---
# <a name="connection-points-classes"></a>Классы точек подключения

Следующие классы обеспечивают поддержку точек подключения.

- [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) реализует контейнер точек соединения.

- [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) реализует точку соединения.

- [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) реализует объект точки подключения, представляющий [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) интерфейс.

- [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) управляет неограниченное количество подключений между точкой подключения и его приемников.

- [CComUnkArray](../atl/reference/ccomunkarray-class.md) управляет фиксированного числа подключений между точки подключения и его приемников.

- [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) уведомляет приемником клиента, который свойство объекта был изменен или изменением.

- [IDispEventImpl](../atl/reference/idispeventimpl-class.md) обеспечивает поддержку точек подключения для ATL COM-объекта. Эти соединения будут сопоставлены с картой приемника событий, предоставляемый COM-объект.

- [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) сопоставить работает вместе с приемником событий в классе события соответствующим функциям обработки.

## <a name="related-articles"></a>Связанные статьи

[Точки подключения](../atl/atl-connection-points.md)

[Обработка событий и ATL](../atl/event-handling-and-atl.md)

## <a name="see-also"></a>См. также

[Общие сведения о классе](../atl/atl-class-overview.md)<br/>
[Макросы для работы с точками подключения](../atl/reference/connection-point-macros.md)<br/>
[Глобальные функции точек подключения](../atl/reference/connection-point-global-functions.md)

