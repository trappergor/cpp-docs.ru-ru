---
title: Макросы точек подключения
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
ms.openlocfilehash: cb8d6f696980ef91d7b43c960dc50289ea8500a6
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423156"
---
# <a name="connection-point-macros"></a>Макросы точек подключения

Эти макросы определяют карты и записи точек подключения.

|||
|-|-|
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|Помечает начало записей карт точек подключения.|
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|Вводит точки соединения в карту.|
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017) Аналогичен CONNECTION_POINT_ENTRY, но принимает указатель на IID.|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|Помечает конец записей карт точек подключения.|

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="begin_connection_point_map"></a>BEGIN_CONNECTION_POINT_MAP

Помечает начало записей карт точек подключения.

```
BEGIN_CONNECTION_POINT_MAP(x)
```

### <a name="parameters"></a>Параметры

*x*<br/>
окне Имя класса, содержащего точки соединения.

### <a name="remarks"></a>Remarks

Запустите карту точек подключения с помощью макроса BEGIN_CONNECTION_POINT_MAP, добавьте записи для каждой точки подключения с помощью макроса [CONNECTION_POINT_ENTRY](#connection_point_entry) и завершите карту с помощью макроса [END_CONNECTION_POINT_MAP](#end_connection_point_map) .

Дополнительные сведения о точках подключения в ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]

##  <a name="connection_point_entry"></a>CONNECTION_POINT_ENTRY и CONNECTION_POINT_ENTRY_P

Вводит точку подключения для указанного интерфейса в карту точек подключения, чтобы к ней можно было получить доступ.

```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
окне Идентификатор GUID интерфейса, добавляемого к карте точек подключения.

*пиид*<br/>
окне Указатель на идентификатор GUID Адде интерфейса.

### <a name="remarks"></a>Remarks

Записи точек подключения в карте используются [иконнектионпоинтконтаинеримпл](../../atl/reference/iconnectionpointcontainerimpl-class.md). Класс, содержащий карту точек подключения, должен наследовать от `IConnectionPointContainerImpl`.

Запустите карту точек подключения с помощью макроса [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) , добавьте записи для каждой точки подключения с помощью макроса CONNECTION_POINT_ENTRY и завершите карту с помощью макроса [END_CONNECTION_POINT_MAP](#end_connection_point_map) .

Дополнительные сведения о точках подключения в ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]

##  <a name="end_connection_point_map"></a>END_CONNECTION_POINT_MAP

Помечает конец записей карт точек подключения.

```
END_CONNECTION_POINT_MAP()
```

### <a name="remarks"></a>Remarks

Запустите карту точек подключения с помощью макроса [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) , добавьте записи для каждой точки подключения с помощью макроса [CONNECTION_POINT_ENTRY](#connection_point_entry) и завершите карту с помощью макроса END_CONNECTION_POINT_MAP.

Дополнительные сведения о точках подключения в ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)<br/>
[Глобальные функции точек подключения](../../atl/reference/connection-point-global-functions.md)
