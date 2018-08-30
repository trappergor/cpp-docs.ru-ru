---
title: Класс IOleControlImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
dev_langs:
- C++
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e3ba537568ba59c241378aeba83450db536511a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201341"
---
# <a name="iolecontrolimpl-class"></a>Класс IOleControlImpl
Этот класс предоставляет реализацию по умолчанию `IOleControl` интерфейса и реализует `IUnknown`.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class IOleControlImpl
```   
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `IOleControlImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IOleControlImpl::FreezeEvents](#freezeevents)|Указывает ли контейнер игнорирует или принимает события из элемента управления.|  
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|Заполняет сведения о поведении элемента управления клавиатуры. Реализация ATL возвращает E_NOTIMPL.|  
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|Информирует элемент управления о том, что один или несколько свойствам окружения контейнера был изменен. Реализация ATL, возвращается значение s_ок.|  
|[IOleControlImpl::OnMnemonic](#onmnemonic)|Информирует элемент управления о том, что пользователь нажал на указанный нажатие клавиши. Реализация ATL возвращает E_NOTIMPL.|  
  
## <a name="remarks"></a>Примечания  
 Класс `IOleControlImpl` предоставляет реализацию по умолчанию [IOleControl](/windows/desktop/api/ocidl/nn-ocidl-iolecontrol) интерфейса и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="freezeevents"></a>  IOleControlImpl::FreezeEvents  
 В реализации библиотеки ATL `FreezeEvents` увеличивает класс элемента управления `m_nFreezeEvents` данные-член Если `bFreeze` возвращает значение TRUE, и уменьшает `m_nFreezeEvents` Если `bFreeze` имеет значение FALSE.  
  
```
HRESULT FreezeEvents(BOOL bFreeze);
```  
  
### <a name="remarks"></a>Примечания  
 `FreezeEvents` Возвращает значение S_OK.  
  
 См. в разделе [метод интерфейса IOleControl::FreezeEvents](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-freezeevents) в Windows SDK.  
  
##  <a name="getcontrolinfo"></a>  IOleControlImpl::GetControlInfo  
 Заполняет сведения о поведении элемента управления клавиатуры.  
  
```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleControl:GetControlInfo](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает E_NOTIMPL.  
  
##  <a name="onambientpropertychange"></a>  IOleControlImpl::OnAmbientPropertyChange  
 Информирует элемент управления о том, что один или несколько свойствам окружения контейнера был изменен.  
  
```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleControl::OnAmbientPropertyChange](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange) в Windows SDK.  
  
##  <a name="onmnemonic"></a>  IOleControlImpl::OnMnemonic  
 Информирует элемент управления о том, что пользователь нажал на указанный нажатие клавиши.  
  
```
HRESULT OnMnemonic(LPMSG pMsg);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает E_NOTIMPL.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleControl::OnMnemonic](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-onmnemonic) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)   
 [Интерфейсы, элементы управления ActiveX](/windows/desktop/com/activex-controls-interfaces)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
