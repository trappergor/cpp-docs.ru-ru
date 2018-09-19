---
title: Класс IConnectionPointContainerImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
dev_langs:
- C++
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27c1d945cf9e801ec1fe2346232aebcad559982a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019910"
---
# <a name="iconnectionpointcontainerimpl-class"></a>Класс IConnectionPointContainerImpl

Этот класс реализует контейнер точек соединения, чтобы управлять коллекцией [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) объектов.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class ATL_NO_VTABLE IConnectionPointContainerImpl 
   : public IConnectionPointContainer
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IConnectionPointContainerImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|Создает перечислитель для перебора точек соединения, поддерживаемых в доступный для соединения объект.|
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|Извлекает указатель интерфейса на точку подключения, который поддерживает указанный идентификатор IID.|

## <a name="remarks"></a>Примечания

`IConnectionPointContainerImpl` реализует контейнер точек соединения, чтобы управлять коллекцией [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) объектов. `IConnectionPointContainerImpl` предоставляет два метода, которые клиент может вызвать для получения дополнительных сведений о подключаемом объекте:

- `EnumConnectionPoints` позволяет клиенту определить, какие исходящие интерфейсы поддерживает объект.

- `FindConnectionPoint` позволяет клиенту определить, поддерживает ли объект определенного исходящего интерфейса.

Сведения об использовании точки подключения библиотеки ATL, см. в статье [точек подключения](../../atl/atl-connection-points.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IConnectionPointContainer`

`IConnectionPointContainerImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="enumconnectionpoints"></a>  IConnectionPointContainerImpl::EnumConnectionPoints

Создает перечислитель для перебора точек соединения, поддерживаемых в доступный для соединения объект.

```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```

### <a name="remarks"></a>Примечания

См. в разделе [IConnectionPointContainer::EnumConnectionPoints](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-enumconnectionpoints) в Windows SDK.

##  <a name="findconnectionpoint"></a>  IConnectionPointContainerImpl::FindConnectionPoint

Извлекает указатель интерфейса на точку подключения, который поддерживает указанный идентификатор IID.

```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```

### <a name="remarks"></a>Примечания

См. в разделе [IConnectionPointContainer::FindConnectionPoint](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) в Windows SDK.

## <a name="see-also"></a>См. также

[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
