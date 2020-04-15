---
title: Глобальные функции точки подключения
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
ms.openlocfilehash: 6474297f8b9adf04541f7d232fb88d5e52d4e88c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331534"
---
# <a name="connection-point-global-functions"></a>Глобальные функции точки подключения

Эти функции обеспечивают поддержку точек соединения и карт раковины.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, не могут использоваться в приложениях, выполняемых в Windows Runtime.

|||
|-|-|
|[AtlAdvise](#atladvise)|Создает связь между точкой подключения объекта и приемником клиента.|
|[AtlUnadvise](#atlunadvise)|Прекращает подключение, `AtlAdvise`установленное через .|
|[AtlAdviseSinkMap](#atladvisesinkmap)|Консультирует или не советует записи на карте раковины события.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="atladvise"></a><a name="atladvise"></a>AtlAdvise

Создает связь между точкой подключения объекта и приемником клиента.

> [!IMPORTANT]
> Эта функция не может быть использована в приложениях, выполняющих в Windows Runtime.

```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```

### <a name="parameters"></a>Параметры

*pUnkCP*<br/>
(в) Указатель на `IUnknown` объект, с который клиент хочет подключиться.

*Панк*<br/>
(в) Указатель на клиента `IUnknown`.

*Iid*<br/>
(в) GUID точки соединения. Как правило, это то же самое, что исходящий интерфейс, управляемый точкой соединения.

*Pdw*<br/>
(ваут) Указатель на файл cookie, который однозначно идентифицирует соединение.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Раковина реализует исходящий интерфейс, поддерживаемый точкой соединения. Клиент использует *файл-кидк pdw* для удаления соединения, передав его [AtlUnadvise.](#atlunadvise)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]

## <a name="atlunadvise"></a><a name="atlunadvise"></a>Атлетико

Прекращает подключение, установленное через [AtlAdvise](#atladvise).

> [!IMPORTANT]
> Эта функция не может быть использована в приложениях, выполняющих в Windows Runtime.

```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```

### <a name="parameters"></a>Параметры

*pUnkCP*<br/>
(в) Указатель на `IUnknown` объект, с которым связан клиент.

*Iid*<br/>
(в) GUID точки соединения. Как правило, это то же самое, что исходящий интерфейс, управляемый точкой соединения.

*dw*<br/>
(в) Файлы cookie, которые однозначно идентифицируют соединение.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]

## <a name="atladvisesinkmap"></a><a name="atladvisesinkmap"></a>AtlAdviseSinkMap

Вызывайте эту функцию для соединения или разъединения всех записей в схеме событий приемника объекта.

> [!IMPORTANT]
> Эта функция не может быть использована в приложениях, выполняющих в Windows Runtime.

```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```

### <a name="parameters"></a>Параметры

*Pt*<br/>
(в) Указатель на объект, содержащий карту раковины.

*bAdvise*<br/>
(в) ПРАВДА, если все записи раковины должны быть рекомендованы; FALSE, если все записи раковины должны быть нерекомендуетыми.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)<br/>
[Макрос точки соединения](../../atl/reference/connection-point-macros.md)
