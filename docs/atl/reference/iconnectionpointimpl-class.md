---
title: Класс IConnectionPointImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 444dea401fa711b40e4d8229b26c9cdbf6d1fcbc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362644"
---
# <a name="iconnectionpointimpl-class"></a>Класс IConnectionPointImpl
Этот класс реализует точку соединения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>  
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IConnectionPointImpl`.  
  
 `piid`  
 Указатель на IID интерфейса, представленный объектом точки подключения.  
  
 `CDV`  
 Класс, который управляет соединениями. Значение по умолчанию — [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), что позволяет неограниченное число подключений. Можно также использовать [CComUnkArray](../../atl/reference/ccomunkarray-class.md), который задает фиксированное число подключений.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IConnectionPointImpl::Advise](#advise)|Устанавливает соединение между точкой подключения и приемником.|  
|[IConnectionPointImpl::EnumConnections](#enumconnections)|Создает перечислитель для перебора соединений для точки подключения.|  
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|Получает идентификатор IID интерфейса, представленный точкой подключения.|  
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|Получает указатель интерфейса на объект, доступный для соединения.|  
|[IConnectionPointImpl::Unadvise](#unadvise)|Завершает соединение, установленное ранее при помощи `Advise`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[IConnectionPointImpl::m_vec](#m_vec)|Управляет соединениями для точки подключения.|  
  
## <a name="remarks"></a>Примечания  
 `IConnectionPointImpl` реализует точку соединения, который позволяет объекту предоставлять исходящий интерфейс клиенту. Клиент реализует этот интерфейс для объекта, который называется приемником.  
  
 ATL использует [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) для реализации, доступный для соединения объект. Каждая точка подключения в доступный для соединения объект представляет исходящий интерфейс, определяемый `piid`. Класс *CDV* управляет соединениями между точкой подключения и приемником. Для каждого подключения однозначно идентифицируется «cookie».  
  
 Дополнительные сведения об использовании точек соединения в ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_ICPLocator`  
  
 `IConnectionPointImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="advise"></a>  IConnectionPointImpl::Advise  
 Устанавливает соединение между точкой подключения и приемником.  
  
```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```  
  
### <a name="remarks"></a>Примечания  
 Используйте [Unadvise](#unadvise) завершение соединения.  
  
 В разделе [IConnectionPoint::Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) в Windows SDK.  
  
##  <a name="enumconnections"></a>  IConnectionPointImpl::EnumConnections  
 Создает перечислитель для перебора соединений для точки подключения.  
  
```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPoint::EnumConnections](http://msdn.microsoft.com/library/windows/desktop/ms680755) в Windows SDK.  
  
##  <a name="getconnectioninterface"></a>  IConnectionPointImpl::GetConnectionInterface  
 Получает идентификатор IID интерфейса, представленный точкой подключения.  
  
```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPoint::GetConnectionInterface](http://msdn.microsoft.com/library/windows/desktop/ms693468) в Windows SDK.  
  
##  <a name="getconnectionpointcontainer"></a>  IConnectionPointImpl::GetConnectionPointContainer  
 Получает указатель интерфейса на объект, доступный для соединения.  
  
```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPoint::GetConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms679669) в Windows SDK.  
  
##  <a name="m_vec"></a>  IConnectionPointImpl::m_vec  
 Управляет соединениями между объектом точки подключения и приемником.  
  
```
CDV m_vec;
```     
  
### <a name="remarks"></a>Примечания  
 По умолчанию `m_vec` относится к типу [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md).  
  
##  <a name="unadvise"></a>  IConnectionPointImpl::Unadvise  
 Завершает соединение, установленное ранее при помощи [Advise](#advise).  
  
```
STDMETHOD(Unadvise)(DWORD dwCookie);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
