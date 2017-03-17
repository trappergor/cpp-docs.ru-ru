---
title: "Класс IOleControlImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5e63849a504b931de30141dd91af557f16c67fd8
ms.lasthandoff: 02/24/2017

---
# <a name="iolecontrolimpl-class"></a>Класс IOleControlImpl
Этот класс предоставляет реализацию по умолчанию **IOleControl** интерфейса и реализует **IUnknown**.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class IOleControlImpl
```   
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IOleControlImpl`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IOleControlImpl::FreezeEvents](#freezeevents)|Указывает ли контейнер игнорирует или принимает события из элемента управления.|  
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|Заполняет сведения о поведении клавиатуры элемента управления. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|Информирует элемент управления один или несколько свойств внешнего контейнера изменилось. Возвращает реализацию ATL `S_OK`.|  
|[IOleControlImpl::OnMnemonic](#onmnemonic)|Информирует элемент управления, пользователь нажал указанного нажатия клавиши. Возвращает реализацию ATL **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Примечания  
 Класс `IOleControlImpl` предоставляет реализацию по умолчанию [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320) интерфейса и реализует **IUnknown** при отправке информации для дампа строит устройства в режиме отладки.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="freezeevents"></a>IOleControlImpl::FreezeEvents  
 В реализации библиотеки ATL `FreezeEvents` увеличивает класс элемента управления `m_nFreezeEvents` член данных при `bFreeze` — **TRUE**и уменьшает `m_nFreezeEvents` Если `bFreeze` — **FALSE**.  
  
```
HRESULT FreezeEvents(BOOL bFreeze);
```  
  
### <a name="remarks"></a>Примечания  
 `FreezeEvents`Возвращает `S_OK`.  
  
 В разделе [IOleControl::FreezeEvents](http://msdn.microsoft.com/library/windows/desktop/ms678482) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getcontrolinfo"></a>IOleControlImpl::GetControlInfo  
 Заполняет сведения о поведении клавиатуры элемента управления.  
  
```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleControl:GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
##  <a name="onambientpropertychange"></a>IOleControlImpl::OnAmbientPropertyChange  
 Информирует элемент управления один или несколько свойств внешнего контейнера изменилось.  
  
```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleControl::OnAmbientPropertyChange](http://msdn.microsoft.com/library/windows/desktop/ms690175) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onmnemonic"></a>IOleControlImpl::OnMnemonic  
 Информирует элемент управления, пользователь нажал указанного нажатия клавиши.  
  
```
HRESULT OnMnemonic(LPMSG pMsg);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleControl::OnMnemonic](http://msdn.microsoft.com/library/windows/desktop/ms680699) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Класс IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)   
 [Интерфейсы, элементы управления ActiveX](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

