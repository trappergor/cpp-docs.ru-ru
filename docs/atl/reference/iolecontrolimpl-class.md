---
title: Класс IOleControlImpl | Документы Microsoft
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
ms.openlocfilehash: 5a54067f53e83d78f063ae5f3694460452e24b26
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361802"
---
# <a name="iolecontrolimpl-class"></a>Класс IOleControlImpl
Этот класс предоставляет реализацию по умолчанию **IOleControl** интерфейса и реализует **IUnknown**.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class IOleControlImpl
```   
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IOleControlImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IOleControlImpl::FreezeEvents](#freezeevents)|Указывает ли контейнер игнорирует и не принимает события из элемента управления.|  
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|Заполняет сведения о поведении клавиатуры элемента управления. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|Информирует элемент управления, что изменился один или несколько свойств внешнего контейнера. Возвращает реализацию ATL `S_OK`.|  
|[IOleControlImpl::OnMnemonic](#onmnemonic)|Информирует элемент управления о том, что пользователь нажал указанного нажатие клавиши. Возвращает реализацию ATL **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Примечания  
 Класс `IOleControlImpl` предоставляет реализацию по умолчанию [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320) интерфейса и реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="freezeevents"></a>  IOleControlImpl::FreezeEvents  
 В реализации ATL `FreezeEvents` увеличивает класс элемента управления `m_nFreezeEvents` член данных Если `bFreeze` — **TRUE**и уменьшает `m_nFreezeEvents` Если `bFreeze` — **FALSE**.  
  
```
HRESULT FreezeEvents(BOOL bFreeze);
```  
  
### <a name="remarks"></a>Примечания  
 `FreezeEvents` Возвращает `S_OK`.  
  
 В разделе [метод интерфейса IOleControl::FreezeEvents](http://msdn.microsoft.com/library/windows/desktop/ms678482) в Windows SDK.  
  
##  <a name="getcontrolinfo"></a>  IOleControlImpl::GetControlInfo  
 Заполняет сведения о поведении клавиатуры элемента управления.  
  
```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleControl:GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
##  <a name="onambientpropertychange"></a>  IOleControlImpl::OnAmbientPropertyChange  
 Информирует элемент управления, что изменился один или несколько свойств внешнего контейнера.  
  
```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleControl::OnAmbientPropertyChange](http://msdn.microsoft.com/library/windows/desktop/ms690175) в Windows SDK.  
  
##  <a name="onmnemonic"></a>  IOleControlImpl::OnMnemonic  
 Информирует элемент управления о том, что пользователь нажал указанного нажатие клавиши.  
  
```
HRESULT OnMnemonic(LPMSG pMsg);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleControl::OnMnemonic](http://msdn.microsoft.com/library/windows/desktop/ms680699) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)   
 [Интерфейсы, элементы управления ActiveX](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
