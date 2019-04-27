---
title: Точки подключения классов (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- classes [C++], connection points
- connection points classes
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
ms.openlocfilehash: 8e1ee67f75af1fa38693f7ddb487580ab733cc58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250818"
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
