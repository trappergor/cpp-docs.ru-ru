---
title: "Класс IRunnableObjectImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
dev_langs: C++
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1ac939d723596f4b0fc3f1013dd3f02cf2aa06b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="irunnableobjectimpl-class"></a>Класс IRunnableObjectImpl
Этот класс реализует **IUnknown** и предоставляет реализацию по умолчанию [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) интерфейса.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class IRunnableObjectImpl
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IRunnableObjectImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|Возвращает CLSID выполнение элемента управления. Реализация ATL задает CLSID `GUID_NULL` и возвращает **E_UNEXPECTED**.|  
|[IRunnableObjectImpl::IsRunning](#isrunning)|Определяет, выполняется ли элемент управления. Возвращает реализацию ATL **TRUE**.|  
|[IRunnableObjectImpl::LockRunning](#lockrunning)|Блокирует элемент управления в запущенном состоянии. Возвращает реализацию ATL `S_OK`.|  
|[IRunnableObjectImpl::Run](#run)|Заставляет элемент управления для выполнения. Возвращает реализацию ATL `S_OK`.|  
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|Указывает, что элемент управления внедрен. Возвращает реализацию ATL `S_OK`.|  
  
## <a name="remarks"></a>Примечания  
 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) интерфейс позволяет контейнера для определения, выполняется ли элемент управления, принудительно запустить или закрепить в состоянии выполнения. Класс `IRunnableObjectImpl` предоставляет стандартную реализацию этого интерфейса и реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="getrunningclass"></a>IRunnableObjectImpl::GetRunningClass  
 Возвращает CLSID выполнение элемента управления.  
  
```
HRESULT GetRunningClass(LPCLSID lpClsid);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Задает реализацию ATL \* *lpClsid* для `GUID_NULL` и возвращает **E_UNEXPECTED**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IRunnableObject::GetRunningClass](http://msdn.microsoft.com/library/windows/desktop/ms693734) в Windows SDK.  
  
##  <a name="isrunning"></a>IRunnableObjectImpl::IsRunning  
 Определяет, выполняется ли элемент управления.  
  
```
virtual BOOL IsRunning();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает реализацию ATL **TRUE**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IRunnableObject::IsRunning](http://msdn.microsoft.com/library/windows/desktop/ms678496) в Windows SDK.  
  
##  <a name="lockrunning"></a>IRunnableObjectImpl::LockRunning  
 Блокирует элемент управления в запущенном состоянии.  
  
```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает реализацию ATL `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IRunnableObject::LockRunning](http://msdn.microsoft.com/library/windows/desktop/ms693361) в Windows SDK.  
  
##  <a name="run"></a>IRunnableObjectImpl::Run  
 Заставляет элемент управления для выполнения.  
  
```
HRESULT Run(LPBINDCTX lpbc);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает реализацию ATL `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IRunnableObject::Run](http://msdn.microsoft.com/library/windows/desktop/ms694517) в Windows SDK.  
  
##  <a name="setcontainedobject"></a>IRunnableObjectImpl::SetContainedObject  
 Указывает, что элемент управления внедрен.  
  
```
HRESULT SetContainedObject(BOOL fContained);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает реализацию ATL `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IRunnableObject::SetContainedObject](http://msdn.microsoft.com/library/windows/desktop/ms693710) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
