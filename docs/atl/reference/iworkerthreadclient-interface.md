---
title: Интерфейс IWorkerThreadClient
ms.date: 11/04/2016
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
ms.openlocfilehash: 6a68f25f153a0ad2cf42ebfaa374ff63c5746fcd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326299"
---
# <a name="iworkerthreadclient-interface"></a>Интерфейс IWorkerThreadClient

`IWorkerThreadClient`— интерфейс, реализованный клиентами класса [CWorkerThread.](../../atl/reference/cworkerthread-class.md)

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
__interface IWorkerThreadClient
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[ЗакрытьРучку](#closehandle)|Реализация этого метода для закрытия ручки, связанной с этим объектом.|
|[Выполнить](#execute)|Реализация этого метода для выполнения кода, когда ручка, связанная с этим объектом, становится сигнальной.|

## <a name="remarks"></a>Remarks

Реализация этого интерфейса, когда у вас есть код, который должен выполняться на потоке рабочего в ответ на сигнализировать ручку.

## <a name="requirements"></a>Требования

**Заголовок:** atlutil.h

## <a name="iworkerthreadclientclosehandle"></a><a name="closehandle"></a>IWorkerThreadClient::: Близкий к работе

Реализация этого метода для закрытия ручки, связанной с этим объектом.

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>Параметры

*hHandle*<br/>
Ручка будет закрыта.

### <a name="return-value"></a>Возвращаемое значение

Возврат S_OK на успех, или ошибка HRESULT на неудачу.

### <a name="remarks"></a>Remarks

Ручка, переданная этому методу, ранее была связана с этим объектом путем вызова [cWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Пример

Следующий код показывает простую реализацию `IWorkerThreadClient::CloseHandle`.

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

## <a name="iworkerthreadclientexecute"></a><a name="execute"></a>IWorkerThreadClient:::

Реализация этого метода для выполнения кода, когда ручка, связанная с этим объектом, становится сигнальной.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>Параметры

*dwParam*<br/>
Пользовательский параметр.

*hObject*<br/>
Ручка, которая стала сигнальной.

### <a name="return-value"></a>Возвращаемое значение

Возврат S_OK на успех, или ошибка HRESULT на неудачу.

### <a name="remarks"></a>Remarks

Ручка и DWORD/pointer, переданные этому методу, ранее были связаны с этим объектом путем вызова [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

### <a name="example"></a>Пример

Следующий код показывает простую реализацию `IWorkerThreadClient::Execute`.

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>См. также раздел

[Классы](../../atl/reference/atl-classes.md)<br/>
[Класс CWorkerThread](../../atl/reference/cworkerthread-class.md)
