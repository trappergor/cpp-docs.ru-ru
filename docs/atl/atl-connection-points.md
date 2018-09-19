---
title: Точки подключения ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe2cf03debbfd88f19ccc77d3922a9a5c50a50d2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091274"
---
# <a name="atl-connection-points"></a>Точки подключения ATL

Доступный для подключения объект поддерживает исходящие интерфейсы. Исходящий интерфейс позволяет объекту обмениваться данными с клиентом. Для каждого исходящего интерфейса доступный для подключения объект предоставляет точку подключения. Каждый исходящий интерфейс реализуется клиентов для объекта, который называется приемником.

![Точки подключения](../atl/media/vc2zw31.gif "vc2zw31")

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

