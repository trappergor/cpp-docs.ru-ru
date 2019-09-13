---
title: Классы точек подключения (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- classes [C++], connection points
- connection points classes
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
ms.openlocfilehash: 0dba06b072e1e9ca545ccbea196fcfe371b02157
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492442"
---
# <a name="connection-points-classes"></a>Классы точек подключения

Следующие классы обеспечивают поддержку точек подключения:

- [Иконнектионпоинтконтаинеримпл](../atl/reference/iconnectionpointcontainerimpl-class.md) Реализует контейнер точки соединения.

- [Иконнектионпоинтимпл](../atl/reference/iconnectionpointimpl-class.md) Реализует точку соединения.

- [Ипропертинотифисинккп](../atl/reference/ipropertynotifysinkcp-class.md) Реализует точку соединения, представляющую интерфейс [ипропертинотифисинк](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) .

- [Ккомдинамикункаррай](../atl/reference/ccomdynamicunkarray-class.md) Управляет неограниченными подключениями между точкой подключения и ее приемниками.

- [Ккомункаррай](../atl/reference/ccomunkarray-class.md) Управляет фиксированным числом соединений между точкой подключения и ее приемниками.

- [Кфирепропнотифевент](../atl/reference/cfirepropnotifyevent-class.md) Уведомляет приемник клиента, что свойство объекта изменилось или собирается его изменить.

- [IDispEventImpl](../atl/reference/idispeventimpl-class.md) Обеспечивает поддержку точек соединения для COM-объекта ATL. Эти точки соединения сопоставляются с картой приемника событий, которая предоставляется объектом COM.

- [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) Работает в сочетании с картой приемника событий в классе для маршрутизации событий в соответствующую функцию обработчика.

## <a name="related-articles"></a>Связанные статьи

[Точки подключения](../atl/atl-connection-points.md)

[Обработка событий и ATL](../atl/event-handling-and-atl.md)

## <a name="see-also"></a>См. также

[Обзор класса](../atl/atl-class-overview.md)<br/>
[Макросы для работы с точками подключения](../atl/reference/connection-point-macros.md)<br/>
[Глобальные функции точек подключения](../atl/reference/connection-point-global-functions.md)
