---
title: Класс Иконнектионпоинтконтаинеримпл
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
ms.openlocfilehash: 278ca6b1b9aac9539680d90b6fa0b18df22fc2f0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496013"
---
# <a name="iconnectionpointcontainerimpl-class"></a>Класс Иконнектионпоинтконтаинеримпл

Этот класс реализует контейнер точек соединения для управления коллекцией объектов [иконнектионпоинтимпл](../../atl/reference/iconnectionpointimpl-class.md) .

## <a name="syntax"></a>Синтаксис

```
template<class T>
class ATL_NO_VTABLE IConnectionPointContainerImpl
   : public IConnectionPointContainer
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IConnectionPointContainerImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Иконнектионпоинтконтаинеримпл:: Енумконнектионпоинтс](#enumconnectionpoints)|Создает перечислитель для прохода по точкам соединения, поддерживаемым в подключаемом объекте.|
|[Иконнектионпоинтконтаинеримпл:: Финдконнектионпоинт](#findconnectionpoint)|Извлекает указатель интерфейса на точку соединения, которая поддерживает указанный IID.|

## <a name="remarks"></a>Примечания

`IConnectionPointContainerImpl`реализует контейнер точек соединения для управления коллекцией объектов [иконнектионпоинтимпл](../../atl/reference/iconnectionpointimpl-class.md) . `IConnectionPointContainerImpl`предоставляет два метода, которые клиент может вызвать для получения дополнительных сведений о подключаемом объекте:

- `EnumConnectionPoints`позволяет клиенту определить, какие исходящие интерфейсы поддерживаются объектом.

- `FindConnectionPoint`позволяет клиенту определить, поддерживает ли объект определенный исходящий интерфейс.

Сведения об использовании точек подключения в ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IConnectionPointContainer`

`IConnectionPointContainerImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлком. h

##  <a name="enumconnectionpoints"></a>Иконнектионпоинтконтаинеримпл:: Енумконнектионпоинтс

Создает перечислитель для прохода по точкам соединения, поддерживаемым в подключаемом объекте.

```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```

### <a name="remarks"></a>Примечания

См. раздел [IConnectionPointContainer:: енумконнектионпоинтс](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-enumconnectionpoints) в Windows SDK.

##  <a name="findconnectionpoint"></a>Иконнектионпоинтконтаинеримпл:: Финдконнектионпоинт

Извлекает указатель интерфейса на точку соединения, которая поддерживает указанный IID.

```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```

### <a name="remarks"></a>Примечания

См. раздел [IConnectionPointContainer:: финдконнектионпоинт](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) в Windows SDK.

## <a name="see-also"></a>См. также

[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
