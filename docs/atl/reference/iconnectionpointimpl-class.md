---
title: Класс IConnectionPointImpl
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
ms.openlocfilehash: b850d9cfa9b2e2ea2a8b5e7f10e29e5cf26bc63e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655238"
---
# <a name="iconnectionpointimpl-class"></a>Класс IConnectionPointImpl

Этот класс реализует точку соединения.

## <a name="syntax"></a>Синтаксис

```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IConnectionPointImpl`.

*piid*<br/>
Указатель на IID интерфейса, представленный объектом точки подключения.

*CDV*<br/>
Класс, который управляет подключениями. Значение по умолчанию — [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), что позволяет неограниченное количество подключений. Можно также использовать [CComUnkArray](../../atl/reference/ccomunkarray-class.md), который задает фиксированное количество подключений.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IConnectionPointImpl::Advise](#advise)|Устанавливает соединение между точкой подключения и приемника.|
|[IConnectionPointImpl::EnumConnections](#enumconnections)|Создает перечислитель для итерации по соединениям для точки подключения.|
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|Получает IID интерфейса, представленный точкой подключения.|
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|Извлекает указатель интерфейса на доступный для соединения объект.|
|[IConnectionPointImpl::Unadvise](#unadvise)|Завершает соединение, установленное ранее при помощи `Advise`.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[IConnectionPointImpl::m_vec](#m_vec)|Управляет подключениями для точки подключения.|

## <a name="remarks"></a>Примечания

`IConnectionPointImpl` реализует точку соединения, который позволяет объекту предоставлять исходящий интерфейс для клиента. Клиент реализует этот интерфейс для объекта, который называется приемником.

Использует ATL [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) для реализации доступный для соединения объект. Каждая точка подключения в доступный для соединения объект представляет исходящего интерфейса, идентифицируемый *piid*. Класс *CDV* управляет подключениями между точкой подключения и приемника. Каждое подключение однозначно идентифицируется «cookie».

Дополнительные сведения об использовании точки подключения библиотеки ATL, см. в статье [точек подключения](../../atl/atl-connection-points.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_ICPLocator`

`IConnectionPointImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="advise"></a>  IConnectionPointImpl::Advise

Устанавливает соединение между точкой подключения и приемника.

```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```

### <a name="remarks"></a>Примечания

Используйте [Unadvise](#unadvise) для завершения соединения.

См. в разделе [IConnectionPoint::Advise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-advise) в Windows SDK.

##  <a name="enumconnections"></a>  IConnectionPointImpl::EnumConnections

Создает перечислитель для итерации по соединениям для точки подключения.

```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```

### <a name="remarks"></a>Примечания

См. в разделе [IConnectionPoint::EnumConnections](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-enumconnections) в Windows SDK.

##  <a name="getconnectioninterface"></a>  IConnectionPointImpl::GetConnectionInterface

Получает IID интерфейса, представленный точкой подключения.

```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```

### <a name="remarks"></a>Примечания

См. в разделе [IConnectionPoint::GetConnectionInterface](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-getconnectioninterface) в Windows SDK.

##  <a name="getconnectionpointcontainer"></a>  IConnectionPointImpl::GetConnectionPointContainer

Извлекает указатель интерфейса на доступный для соединения объект.

```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```

### <a name="remarks"></a>Примечания

См. в разделе [IConnectionPoint::GetConnectionPointContainer](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-getconnectionpointcontainer) в Windows SDK.

##  <a name="m_vec"></a>  IConnectionPointImpl::m_vec

Управляет подключениями между объект точки подключения и в качестве приемника.

```
CDV m_vec;
```

### <a name="remarks"></a>Примечания

По умолчанию `m_vec` имеет тип [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md).

##  <a name="unadvise"></a>  IConnectionPointImpl::Unadvise

Завершает соединение, установленное ранее при помощи [Advise](#advise).

```
STDMETHOD(Unadvise)(DWORD dwCookie);
```

### <a name="remarks"></a>Примечания

См. в разделе [IConnectionPoint::Unadvise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-unadvise) в Windows SDK.

## <a name="see-also"></a>См. также

[IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
