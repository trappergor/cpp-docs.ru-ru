---
title: Класс Иконнектионпоинтимпл
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
ms.openlocfilehash: bd88fd5d00df0347c0bd2161129b8cfa3ca35406
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496083"
---
# <a name="iconnectionpointimpl-class"></a>Класс Иконнектионпоинтимпл

Этот класс реализует точку соединения.

## <a name="syntax"></a>Синтаксис

```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IConnectionPointImpl`.

*пиид*<br/>
Указатель на идентификатор IID интерфейса, представленного объектом точки подключения.

*КДВ*<br/>
Класс, управляющий соединениями. Значение по умолчанию — [ккомдинамикункаррай](../../atl/reference/ccomdynamicunkarray-class.md), что позволяет устанавливать неограниченное число подключений. Можно также использовать [ккомункаррай](../../atl/reference/ccomunkarray-class.md), который указывает фиксированное число соединений.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Иконнектионпоинтимпл:: Advise](#advise)|Устанавливает соединение между точкой подключения и приемником.|
|[Иконнектионпоинтимпл:: Енумконнектионс](#enumconnections)|Создает перечислитель для прохода по соединениям для точки подключения.|
|[Иконнектионпоинтимпл:: Жетконнектионинтерфаце](#getconnectioninterface)|Возвращает идентификатор IID интерфейса, представленного точкой подключения.|
|[Иконнектионпоинтимпл:: Жетконнектионпоинтконтаинер](#getconnectionpointcontainer)|Извлекает указатель интерфейса на объект, который можно подключить.|
|[Иконнектионпоинтимпл:: unadvise](#unadvise)|Завершает соединение, установленное ранее с `Advise`помощью.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Иконнектионпоинтимпл:: m_vec](#m_vec)|Управляет соединениями для точки подключения.|

## <a name="remarks"></a>Примечания

`IConnectionPointImpl`реализует точку подключения, которая позволяет объекту предоставлять клиенту исходящий интерфейс. Клиент реализует этот интерфейс для объекта, называемого приемником.

ATL использует [иконнектионпоинтконтаинеримпл](../../atl/reference/iconnectionpointcontainerimpl-class.md) для реализации объекта, доступного для соединения. Каждая точка подключения в подключаемом объекте представляет исходящий интерфейс, идентифицируемый *пиид*. Класс *КДВ* управляет соединениями между точкой подключения и приемником. Каждое соединение однозначно идентифицируется с помощью "cookie".

Дополнительные сведения об использовании точек подключения в ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_ICPLocator`

`IConnectionPointImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="advise"></a>Иконнектионпоинтимпл:: Advise

Устанавливает соединение между точкой подключения и приемником.

```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```

### <a name="remarks"></a>Примечания

Чтобы завершить вызов соединения, используйте параметр [unadvise](#unadvise) .

См. раздел [IConnectionPoint:: Advise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) в Windows SDK.

##  <a name="enumconnections"></a>Иконнектионпоинтимпл:: Енумконнектионс

Создает перечислитель для прохода по соединениям для точки подключения.

```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```

### <a name="remarks"></a>Примечания

См. раздел [IConnectionPoint:: енумконнектионс](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-enumconnections) в Windows SDK.

##  <a name="getconnectioninterface"></a>Иконнектионпоинтимпл:: Жетконнектионинтерфаце

Возвращает идентификатор IID интерфейса, представленного точкой подключения.

```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```

### <a name="remarks"></a>Примечания

См. раздел [IConnectionPoint:: жетконнектионинтерфаце](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectioninterface) в Windows SDK.

##  <a name="getconnectionpointcontainer"></a>Иконнектионпоинтимпл:: Жетконнектионпоинтконтаинер

Извлекает указатель интерфейса на объект, который можно подключить.

```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```

### <a name="remarks"></a>Примечания

См. раздел [IConnectionPoint:: жетконнектионпоинтконтаинер](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectionpointcontainer) в Windows SDK.

##  <a name="m_vec"></a>Иконнектионпоинтимпл:: m_vec

Управляет соединениями между объектом точки подключения и приемником.

```
CDV m_vec;
```

### <a name="remarks"></a>Примечания

По умолчанию `m_vec` имеет тип [ккомдинамикункаррай](../../atl/reference/ccomdynamicunkarray-class.md).

##  <a name="unadvise"></a>Иконнектионпоинтимпл:: unadvise

Завершает подключение, установленное ранее с помощью [advise](#advise).

```
STDMETHOD(Unadvise)(DWORD dwCookie);
```

### <a name="remarks"></a>Примечания

См. раздел [IConnectionPoint:: unadvise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise) в Windows SDK.

## <a name="see-also"></a>См. также

[IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
