---
title: Точки подключения ATL
ms.date: 11/04/2016
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
ms.openlocfilehash: 4d94396ef8839516d9bfee15a2611cce66baa6bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252315"
---
# <a name="atl-connection-points"></a>Точки подключения ATL

Доступный для подключения объект поддерживает исходящие интерфейсы. Исходящий интерфейс позволяет объекту обмениваться данными с клиентом. Для каждого исходящего интерфейса доступный для подключения объект предоставляет точку подключения. Каждый исходящий интерфейс реализуется клиентов для объекта, который называется приемником.

![Точки подключения](../atl/media/vc2zw31.gif "точек подключения")

Каждая точка подключения поддерживает [IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint) интерфейс. Доступный для соединения объект предоставляет свои точки подключения клиенту через [IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer) интерфейс.

## <a name="in-this-section"></a>В этом разделе

[Классы точки подключения библиотеки ATL](../atl/atl-connection-point-classes.md)<br/>
Краткое описание классов ATL, поддерживающих точки подключения.

[Добавление точек подключения к объектам](../atl/adding-connection-points-to-an-object.md)<br/>
Описываются действия для добавления точек подключения к объекту.

[Пример точки подключения ATL](../atl/atl-connection-point-example.md)<br/>
Пример объявления точки подключения.

## <a name="related-sections"></a>Связанные разделы

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Ссылки на разделы о программировании с использованием библиотеки ATL.

## <a name="see-also"></a>См. также

[Основные понятия](../atl/active-template-library-atl-concepts.md)
