---
title: Точки подключения ATL
ms.date: 11/04/2016
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
ms.openlocfilehash: df69496a6d245702a9598d684b25122ca55b1e6d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491811"
---
# <a name="atl-connection-points"></a>Точки подключения ATL

Доступный для подключения объект поддерживает исходящие интерфейсы. Исходящий интерфейс позволяет объекту обмениваться данными с клиентом. Для каждого исходящего интерфейса доступный для подключения объект предоставляет точку подключения. Каждый исходящий интерфейс реализуется клиентов для объекта, который называется приемником.

![Точки подключения](../atl/media/vc2zw31.gif "Точки подключения")

Каждая точка подключения поддерживает интерфейс [IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) . Подключаемый объект предоставляет клиенту точки подключения через интерфейс [IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer) .

## <a name="in-this-section"></a>В этом разделе

[Классы точки подключения библиотеки ATL](../atl/atl-connection-point-classes.md)<br/>
Краткое описание классов ATL, поддерживающих точки подключения.

[Добавление точек подключения к объектам](../atl/adding-connection-points-to-an-object.md)<br/>
Описываются действия для добавления точек подключения к объекту.

[Пример точки подключения ATL](../atl/atl-connection-point-example.md)<br/>
Пример объявления точки подключения.

## <a name="related-sections"></a>Связанные разделы

[ШАБЛОН](../atl/active-template-library-atl-concepts.md)<br/>
Ссылки на разделы о программировании с использованием библиотеки ATL.

## <a name="see-also"></a>См. также

[Основные понятия](../atl/active-template-library-atl-concepts.md)
