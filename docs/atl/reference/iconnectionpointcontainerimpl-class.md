---
title: "Класс IConnectionPointContainerImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f5e3a6ee6790c4fa0e93fe312d6a6b840b754a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  
|Имя|Описание:|  
|----------|-----------------|  
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|Создает перечислитель для перебора точек соединения, поддерживаемых в объект, доступный для соединения.|  
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|Получает указатель интерфейса точки подключения, который поддерживает указанный IID.|  
  
## <a name="remarks"></a>Примечания  
 `IConnectionPointContainerImpl`реализует контейнер точки подключения для управления коллекцией [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) объектов. `IConnectionPointContainerImpl`предоставляет два метода, которые клиент может вызвать для получения дополнительных сведений об объекте, доступном для подключения:  
  
- `EnumConnectionPoints`позволяет клиенту определить, какие исходящие интерфейсы поддерживает объекта.  
  
- `FindConnectionPoint`позволяет клиенту определить, поддерживает ли объект определенного исходящего интерфейса.  
  
 Сведения об использовании точки подключения библиотеки ATL, см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IConnectionPointContainer`  
  
 `IConnectionPointContainerImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="enumconnectionpoints"></a>IConnectionPointContainerImpl::EnumConnectionPoints  
 Создает перечислитель для перебора точек соединения, поддерживаемых в объект, доступный для соединения.  
  
```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPointContainer::EnumConnectionPoints](http://msdn.microsoft.com/library/windows/desktop/ms682460) в Windows SDK.  
  
##  <a name="findconnectionpoint"></a>IConnectionPointContainerImpl::FindConnectionPoint  
 Получает указатель интерфейса точки подключения, который поддерживает указанный IID.  
  
```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
