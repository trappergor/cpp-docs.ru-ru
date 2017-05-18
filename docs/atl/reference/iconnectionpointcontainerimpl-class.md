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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 81a68cae1d961f2846c1a807432f22ae92ca3b89
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="iconnectionpointcontainerimpl-class"></a>Класс IConnectionPointContainerImpl
Этот класс реализует контейнера точки подключения для управления коллекцией [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class ATL_NO_VTABLE IConnectionPointContainerImpl 
   : public IConnectionPointContainer
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IConnectionPointContainerImpl`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|Создает перечислитель для перебора точек соединения, поддерживаемых в доступный для соединения объект.|  
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|Получает указатель интерфейса на точку подключения, которая поддерживает указанный идентификатор IID.|  
  
## <a name="remarks"></a>Примечания  
 `IConnectionPointContainerImpl`реализует контейнера точки подключения для управления коллекцией [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) объектов. `IConnectionPointContainerImpl`предоставляет два метода, которые клиент может вызвать для получения дополнительных сведений о подключаемый объекта:  
  
- `EnumConnectionPoints`позволяет клиенту определить, какие исходящие интерфейсы поддерживает объект.  
  
- `FindConnectionPoint`позволяет клиенту определить, поддерживает ли объект определенного исходящего интерфейса.  
  
 Сведения об использовании точки подключения библиотеки ATL, см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IConnectionPointContainer`  
  
 `IConnectionPointContainerImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="enumconnectionpoints"></a>IConnectionPointContainerImpl::EnumConnectionPoints  
 Создает перечислитель для перебора точек соединения, поддерживаемых в доступный для соединения объект.  
  
```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPointContainer::EnumConnectionPoints](http://msdn.microsoft.com/library/windows/desktop/ms682460) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="findconnectionpoint"></a>IConnectionPointContainerImpl::FindConnectionPoint  
 Получает указатель интерфейса на точку подключения, которая поддерживает указанный идентификатор IID.  
  
```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

