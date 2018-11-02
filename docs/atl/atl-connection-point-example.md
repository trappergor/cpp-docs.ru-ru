---
title: Пример точки подключения ATL
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
ms.openlocfilehash: 9312db740171672e6b0f231855408e0d0a9e060d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495996"
---
# <a name="atl-connection-point-example"></a>Пример точки подключения ATL

В этом примере показан объект, который поддерживает [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) как исходящий интерфейс:

[!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]

При указании `IPropertyNotifySink` как исходящий интерфейс, можно использовать класс [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) вместо `IConnectionPointImpl`. Пример:

[!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]

## <a name="see-also"></a>См. также

[Точка подключения](../atl/atl-connection-points.md)

