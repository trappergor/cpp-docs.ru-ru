---
title: Глобальные функции точек подключения
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
ms.openlocfilehash: 0313e93ee82bb96f3bfe08e45f70ccfee30dbee6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278272"
---
# <a name="connection-point-global-functions"></a>Глобальные функции точек подключения

Эти функции обеспечивают поддержку для точки подключения и к приемнику maps.

> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.

|||
|-|-|
|[AtlAdvise](#atladvise)|Создает связь между точкой подключения объекта и приемником клиента.|
|[AtlUnadvise](#atlunadvise)|Завершает подключение, установленное через `AtlAdvise`.|
|[AtlAdviseSinkMap](#atladvisesinkmap)|Будет указано, или не рекомендуйте записей в картой приемника событий.|

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="atladvise"></a>  AtlAdvise

Создает связь между точкой подключения объекта и приемником клиента.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.

```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```

### <a name="parameters"></a>Параметры

*pUnkCP*<br/>
[in] Указатель на `IUnknown` объекта клиент хочет подключиться с помощью.

*pUnk*<br/>
[in] Указатель на клиент `IUnknown`.

*IID*<br/>
[in] Идентификатор GUID точки подключения. Как правило это так же, как выходящего интерфейса, управляемого с использованием точки подключения.

*pdw*<br/>
[out] Указатель на файл cookie, который однозначно идентифицирует соединение.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Примечания

Приемник реализует исходящего интерфейса, поддерживаемого точкой подключения. Клиент использует *pdw* куки-файл, чтобы удалить соединение, передав его в [AtlUnadvise](#atlunadvise).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]

##  <a name="atlunadvise"></a>  AtlUnadvise

Завершает подключение, установленное через [AtlAdvise](#atladvise).

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.

```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```

### <a name="parameters"></a>Параметры

*pUnkCP*<br/>
[in] Указатель на `IUnknown` объекта, который клиент подключен с.

*IID*<br/>
[in] Идентификатор GUID точки подключения. Как правило это так же, как выходящего интерфейса, управляемого с использованием точки подключения.

*dw*<br/>
[in] Файл cookie, однозначно определяющее соединение.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]

##  <a name="atladvisesinkmap"></a>  AtlAdviseSinkMap

Вызывайте эту функцию для соединения или разъединения всех записей в схеме событий приемника объекта.

> [!IMPORTANT]
>  Эта функция не может использоваться в приложениях, выполняемых в среде выполнения Windows.

```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```

### <a name="parameters"></a>Параметры

*pT*<br/>
[in] Указатель на объект, содержащий карту в качестве приемника.

*bAdvise*<br/>
[in] Значение TRUE, если все записи в качестве приемника, которому необходимо предоставить рекомендацию; Значение FALSE, если все записи в качестве приемника должны быть негативной рекомендации.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)<br/>
[Макросы для работы с точками подключения](../../atl/reference/connection-point-macros.md)
