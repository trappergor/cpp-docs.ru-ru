---
title: Класс IRunnableObjectImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
dev_langs:
- C++
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 035d59d71dc7166b12b6e894803645aacda83887
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218702"
---
# <a name="irunnableobjectimpl-class"></a>Класс IRunnableObjectImpl
Этот класс реализует `IUnknown` и предоставляет реализацию по умолчанию [IRunnableObject](/windows/desktop/api/objidl/nn-objidl-irunnableobject) интерфейс.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class IRunnableObjectImpl
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `IRunnableObjectImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|Возвращает идентификатор CLSID элемента управления выполнения. Реализация ATL задает CLSID значение GUID_NULL и возвращает E_UNEXPECTED.|  
|[IRunnableObjectImpl::IsRunning](#isrunning)|Определяет, работает ли элемент управления. Реализация ATL возвращает значение TRUE.|  
|[IRunnableObjectImpl::LockRunning](#lockrunning)|Блокирует элемент управления в рабочем состоянии. Реализация ATL, возвращается значение s_ок.|  
|[IRunnableObjectImpl::Run](#run)|Заставляет элемент управления для выполнения. Реализация ATL, возвращается значение s_ок.|  
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|Указывает, что внедряется элемент управления. Реализация ATL, возвращается значение s_ок.|  
  
## <a name="remarks"></a>Примечания  
 [IRunnableObject](/windows/desktop/api/objidl/nn-objidl-irunnableobject) интерфейс позволяет контейнера определить, работает ли элемент управления, для принудительного задания для запуска или закрепить в рабочем состоянии. Класс `IRunnableObjectImpl` предоставляет стандартную реализацию этого интерфейса и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="getrunningclass"></a>  IRunnableObjectImpl::GetRunningClass  
 Возвращает идентификатор CLSID элемента управления выполнения.  
  
```
HRESULT GetRunningClass(LPCLSID lpClsid);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Наборы реализации ATL \* *lpClsid* GUID_NULL и возвращает E_UNEXPECTED.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IRunnableObject::GetRunningClass](/windows/desktop/api/objidl/nf-objidl-irunnableobject-getrunningclass) в Windows SDK.  
  
##  <a name="isrunning"></a>  IRunnableObjectImpl::IsRunning  
 Определяет, работает ли элемент управления.  
  
```
virtual BOOL IsRunning();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация ATL возвращает значение TRUE.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IRunnableObject::IsRunning](/windows/desktop/api/objidl/nf-objidl-irunnableobject-isrunning) в Windows SDK.  
  
##  <a name="lockrunning"></a>  IRunnableObjectImpl::LockRunning  
 Блокирует элемент управления в рабочем состоянии.  
  
```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация ATL, возвращается значение s_ок.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IRunnableObject::LockRunning](/windows/desktop/api/objidl/nf-objidl-irunnableobject-lockrunning) в Windows SDK.  
  
##  <a name="run"></a>  IRunnableObjectImpl::Run  
 Заставляет элемент управления для выполнения.  
  
```
HRESULT Run(LPBINDCTX lpbc);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация ATL, возвращается значение s_ок.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IRunnableObject::Run](/windows/desktop/api/objidl/nf-objidl-irunnableobject-run) в Windows SDK.  
  
##  <a name="setcontainedobject"></a>  IRunnableObjectImpl::SetContainedObject  
 Указывает, что внедряется элемент управления.  
  
```
HRESULT SetContainedObject(BOOL fContained);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация ATL, возвращается значение s_ок.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IRunnableObject::SetContainedObject](/windows/desktop/api/objidl/nf-objidl-irunnableobject-setcontainedobject) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
