---
title: Макрос точки соединения
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
ms.openlocfilehash: 361cf6ab2c7af142c1d57c002681ccf6e4a87bda
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331495"
---
# <a name="connection-point-macros"></a>Макрос точки соединения

Эти макросы определяют карты точек соединения и записи.

|||
|-|-|
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|Отмечает начало записи карты точки соединения.|
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|Вводит точки соединения на карту.|
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Визуальная студия 2017) Как и CONNECTION_POINT_ENTRY но принимает указатель на iid.|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|Отметки конца записей карты точки соединения.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="begin_connection_point_map"></a><a name="begin_connection_point_map"></a>BEGIN_CONNECTION_POINT_MAP

Отмечает начало записи карты точки соединения.

```
BEGIN_CONNECTION_POINT_MAP(x)
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Название класса, содержащее точки соединения.

### <a name="remarks"></a>Remarks

Начните карту точки соединения с BEGIN_CONNECTION_POINT_MAP макросом, добавьте записи для каждой из точек соединения с [макросом CONNECTION_POINT_ENTRY](#connection_point_entry) и завершите карту [END_CONNECTION_POINT_MAP с](#end_connection_point_map) макросом.

Для получения дополнительной информации о точках [Connection Points](../../atl/atl-connection-points.md)соединения в ATL, см.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]

## <a name="connection_point_entry-and-connection_point_entry_p"></a><a name="connection_point_entry"></a>CONNECTION_POINT_ENTRY и CONNECTION_POINT_ENTRY_P

Вводит точку соединения для указанного интерфейса в карту точки соединения, чтобы к ней можно было получить доступ.

```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) GUID интерфейса, добавляемого к карте точки соединения.

*пиид*<br/>
(в) Указатель на GUID интерфейса адди.

### <a name="remarks"></a>Remarks

Записи точек соединения на карте используются [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md). Класс, содержащий карту точки соединения, должен наследовать от `IConnectionPointContainerImpl`.

Начните карту точки соединения с [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) макросом, добавьте записи для каждой из точек соединения с CONNECTION_POINT_ENTRY макросом и завершите карту [с END_CONNECTION_POINT_MAP](#end_connection_point_map) макросом.

Для получения дополнительной информации о точках [Connection Points](../../atl/atl-connection-points.md)соединения в ATL, см.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]

## <a name="end_connection_point_map"></a><a name="end_connection_point_map"></a>END_CONNECTION_POINT_MAP

Отметки конца записей карты точки соединения.

```
END_CONNECTION_POINT_MAP()
```

### <a name="remarks"></a>Remarks

Начните карту точки соединения с [макросом BEGIN_CONNECTION_POINT_MAP,](#begin_connection_point_map) добавьте записи для каждой из точек соединения с [макросом CONNECTION_POINT_ENTRY](#connection_point_entry) и завершите карту с END_CONNECTION_POINT_MAP макросом.

Для получения дополнительной информации о точках [Connection Points](../../atl/atl-connection-points.md)соединения в ATL, см.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)<br/>
[Глобальные функции точки подключения](../../atl/reference/connection-point-global-functions.md)
