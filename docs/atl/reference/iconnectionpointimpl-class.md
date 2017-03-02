---
title: "Класс IConnectionPointImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.IConnectionPointImpl
- IConnectionPointImpl
- ATL::IConnectionPointImpl
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: c9788496bbed3734b959d0ab4c49c89a176ea199
ms.lasthandoff: 02/24/2017

---
# <a name="iconnectionpointimpl-class"></a>Класс IConnectionPointImpl
Этот класс реализует точку подключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>  
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IConnectionPointImpl`.  
  
 `piid`  
 Указатель на идентификатор IID интерфейса, представленного объектом точки подключения.  
  
 `CDV`  
 Класс, который управляет соединениями. Значение по умолчанию — [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), который позволяет неограниченное число подключений. Можно также использовать [CComUnkArray](../../atl/reference/ccomunkarray-class.md), который указывает ограниченное число подключений.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IConnectionPointImpl::Advise](#advise)|Устанавливает соединение между точкой подключения и приемником.|  
|[IConnectionPointImpl::EnumConnections](#enumconnections)|Создает перечислитель для перебора соединений для точки подключения.|  
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|Получает идентификатор IID интерфейса, представленного точки подключения.|  
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|Получает указатель интерфейса на объект, доступный для подключения.|  
|[IConnectionPointImpl::Unadvise](#unadvise)|Завершает соединение, установленное ранее при помощи `Advise`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[IConnectionPointImpl::m_vec](#m_vec)|Управляет соединениями точки подключения.|  
  
## <a name="remarks"></a>Примечания  
 `IConnectionPointImpl`реализует точку подключения, которая позволяет объекту предоставлять исходящий интерфейс для клиента. Клиент реализует этот интерфейс для объекта, который называется приемником.  
  
 Использует ATL [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) реализовать доступный для соединения объект. Каждая точка подключения в доступный для соединения объект представляет исходящий интерфейс, определяемый `piid`. Класс *CDV* управляет соединениями между точкой подключения и приемником. Для каждого подключения однозначно идентифицируется файл «cookie».  
  
 Дополнительные сведения об использовании точек соединения в ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_ICPLocator`  
  
 `IConnectionPointImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="a-nameadvisea--iconnectionpointimpladvise"></a><a name="advise"></a>IConnectionPointImpl::Advise  
 Устанавливает соединение между точкой подключения и приемником.  
  
```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```  
  
### <a name="remarks"></a>Примечания  
 Используйте [Unadvise](#unadvise) завершение соединения.  
  
 В разделе [IConnectionPoint::Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameenumconnectionsa--iconnectionpointimplenumconnections"></a><a name="enumconnections"></a>IConnectionPointImpl::EnumConnections  
 Создает перечислитель для перебора соединений для точки подключения.  
  
```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPoint::EnumConnections](http://msdn.microsoft.com/library/windows/desktop/ms680755) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetconnectioninterfacea--iconnectionpointimplgetconnectioninterface"></a><a name="getconnectioninterface"></a>IConnectionPointImpl::GetConnectionInterface  
 Получает идентификатор IID интерфейса, представленного точки подключения.  
  
```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPoint::GetConnectionInterface](http://msdn.microsoft.com/library/windows/desktop/ms693468) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetconnectionpointcontainera--iconnectionpointimplgetconnectionpointcontainer"></a><a name="getconnectionpointcontainer"></a>IConnectionPointImpl::GetConnectionPointContainer  
 Получает указатель интерфейса на объект, доступный для подключения.  
  
```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPoint::GetConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms679669) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemveca--iconnectionpointimplmvec"></a><a name="m_vec"></a>IConnectionPointImpl::m_vec  
 Управляет соединениями между объект точки подключения и приемником.  
  
```
CDV m_vec;
```     
  
### <a name="remarks"></a>Примечания  
 По умолчанию `m_vec` типа [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md).  
  
##  <a name="a-nameunadvisea--iconnectionpointimplunadvise"></a><a name="unadvise"></a>IConnectionPointImpl::Unadvise  
 Завершает соединение, установленное ранее при помощи [Advise](#advise).  
  
```
STDMETHOD(Unadvise)(DWORD dwCookie);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

