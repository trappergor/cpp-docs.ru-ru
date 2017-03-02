---
title: "Класс IRunnableObjectImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRunnableObjectImpl
dev_langs:
- C++
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
caps.latest.revision: 20
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
ms.openlocfilehash: a9b2698c195ac5bd709e6d40d3c30008d3fa26d4
ms.lasthandoff: 02/24/2017

---
# <a name="irunnableobjectimpl-class"></a>Класс IRunnableObjectImpl
Этот класс реализует **IUnknown** и предоставляет реализацию по умолчанию [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) интерфейса.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class IRunnableObjectImpl
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IRunnableObjectImpl`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|Возвращает идентификатор CLSID элемента управления выполнения. Реализация ATL задает идентификатор CLSID `GUID_NULL` и возвращает **E_UNEXPECTED**.|  
|[IRunnableObjectImpl::IsRunning](#isrunning)|Определяет, выполняется ли элемент управления. Возвращает реализацию ATL **TRUE**.|  
|[IRunnableObjectImpl::LockRunning](#lockrunning)|Блокирует элемент управления в состоянии выполнения. Возвращает реализацию ATL `S_OK`.|  
|[IRunnableObjectImpl::Run](#run)|Заставляет элемент управления для выполнения. Возвращает реализацию ATL `S_OK`.|  
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|Указывает, что внедряется элемент управления. Возвращает реализацию ATL `S_OK`.|  
  
## <a name="remarks"></a>Примечания  
 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) интерфейс позволяет контейнер, чтобы определить, выполняется ли элемент управления, принудительно запустить или закрепить в состоянии выполнения. Класс `IRunnableObjectImpl` предоставляет стандартную реализацию этого интерфейса и реализует **IUnknown** при отправке информации для дампа строит устройства в режиме отладки.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="a-namegetrunningclassa--irunnableobjectimplgetrunningclass"></a><a name="getrunningclass"></a>IRunnableObjectImpl::GetRunningClass  
 Возвращает идентификатор CLSID элемента управления выполнения.  
  
```
HRESULT GetRunningClass(LPCLSID lpClsid);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Задает реализацию ATL \* *lpClsid* для `GUID_NULL` и возвращает **E_UNEXPECTED**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IRunnableObject::GetRunningClass](http://msdn.microsoft.com/library/windows/desktop/ms693734) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameisrunninga--irunnableobjectimplisrunning"></a><a name="isrunning"></a>IRunnableObjectImpl::IsRunning  
 Определяет, выполняется ли элемент управления.  
  
```
virtual BOOL IsRunning();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает реализацию ATL **TRUE**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IRunnableObject::IsRunning](http://msdn.microsoft.com/library/windows/desktop/ms678496) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namelockrunninga--irunnableobjectimpllockrunning"></a><a name="lockrunning"></a>IRunnableObjectImpl::LockRunning  
 Блокирует элемент управления в состоянии выполнения.  
  
```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает реализацию ATL `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IRunnableObject::LockRunning](http://msdn.microsoft.com/library/windows/desktop/ms693361) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameruna--irunnableobjectimplrun"></a><a name="run"></a>IRunnableObjectImpl::Run  
 Заставляет элемент управления для выполнения.  
  
```
HRESULT Run(LPBINDCTX lpbc);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает реализацию ATL `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IRunnableObject::Run](http://msdn.microsoft.com/library/windows/desktop/ms694517) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetcontainedobjecta--irunnableobjectimplsetcontainedobject"></a><a name="setcontainedobject"></a>IRunnableObjectImpl::SetContainedObject  
 Указывает, что внедряется элемент управления.  
  
```
HRESULT SetContainedObject(BOOL fContained);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает реализацию ATL `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IRunnableObject::SetContainedObject](http://msdn.microsoft.com/library/windows/desktop/ms693710) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

