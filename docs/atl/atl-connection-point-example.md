---
title: Пример точки подключения ATL
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
ms.openlocfilehash: 3113637a3f777a56bc0b0994203ce709fbc189d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223346"
---
# <a name="atl-connection-point-example"></a>Пример точки подключения ATL

В этом примере показан объект, который поддерживает [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) как исходящий интерфейс:

[!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]

При указании `IPropertyNotifySink` как исходящий интерфейс, можно использовать класс [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) вместо `IConnectionPointImpl`. Пример:

[!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]

## <a name="see-also"></a>См. также

[Точка подключения](../atl/atl-connection-points.md)
