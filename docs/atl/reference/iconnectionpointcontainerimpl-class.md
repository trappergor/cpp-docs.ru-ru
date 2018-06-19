---
title: Класс IConnectionPointContainerImpl | Документы Microsoft
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
ms.openlocfilehash: af5e8b1bc1af0a515cc8fad0500c3f7d040b1eb9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361174"
---
# <a name="iconnectionpointcontainerimpl-class"></a>Класс IConnectionPointContainerImpl
Этот класс реализует контейнер точки подключения для управления коллекцией [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class ATL_NO_VTABLE IConnectionPointContainerImpl 
   : public IConnectionPointContainer
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IConnectionPointContainerImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|Создает перечислитель для перебора точек соединения, поддерживаемых в объект, доступный для соединения.|  
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|Получает указатель интерфейса точки подключения, который поддерживает указанный IID.|  
  
## <a name="remarks"></a>Примечания  
 `IConnectionPointContainerImpl` реализует контейнер точки подключения для управления коллекцией [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) объектов. `IConnectionPointContainerImpl` предоставляет два метода, которые клиент может вызвать для получения дополнительных сведений об объекте, доступном для подключения:  
  
- `EnumConnectionPoints` позволяет клиенту определить, какие исходящие интерфейсы поддерживает объекта.  
  
- `FindConnectionPoint` позволяет клиенту определить, поддерживает ли объект определенного исходящего интерфейса.  
  
 Сведения об использовании точки подключения библиотеки ATL, см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IConnectionPointContainer`  
  
 `IConnectionPointContainerImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="enumconnectionpoints"></a>  IConnectionPointContainerImpl::EnumConnectionPoints  
 Создает перечислитель для перебора точек соединения, поддерживаемых в объект, доступный для соединения.  
  
```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPointContainer::EnumConnectionPoints](http://msdn.microsoft.com/library/windows/desktop/ms682460) в Windows SDK.  
  
##  <a name="findconnectionpoint"></a>  IConnectionPointContainerImpl::FindConnectionPoint  
 Получает указатель интерфейса точки подключения, который поддерживает указанный IID.  
  
```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
