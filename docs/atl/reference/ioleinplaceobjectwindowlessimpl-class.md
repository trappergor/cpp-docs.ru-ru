---
title: "Класс IOleInPlaceObjectWindowlessImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetDropTarget
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::OnWindowMessage
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::SetObjectRects
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::UIDeactivate
dev_langs:
- C++
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 06ce03a896c9948bff14b4f91ae48000d07c3edd
ms.lasthandoff: 02/24/2017

---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>Класс IOleInPlaceObjectWindowlessImpl
Этот класс реализует **IUnknown** и предоставляет методы, позволяющие безоконный элемент управления для получения оконных сообщений и принимать участие в операциях и перетаскивания.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IOleInPlaceObjectWindowlessImpl`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|Позволяет контекстная справка. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|Предоставляет `IDropTarget` интерфейс для объекта на месте active, без окон, поддерживает перетаскивание. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|Возвращает дескриптор окна.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|Отключает активный элемент управления на месте.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|Отправляет сообщение из контейнера безоконный элемент управления, который является активным на месте.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|Повторно активирует ранее отключенного элемента управления. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|Указывает, какая часть элемента управления на месте является видимым.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|Отключает и удаляет пользовательский интерфейс, который поддерживает активацию на месте.|  
  
## <a name="remarks"></a>Примечания  
 [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) интерфейс управляет повторной активации и деактивации непосредственно управляет и определяет, какая часть элемента управления должны быть видимыми. [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) интерфейс позволяет безоконный элемент управления для получения оконных сообщений и принимать участие в операциях и перетаскивания. Класс `IOleInPlaceObjectWindowlessImpl` предоставляет реализацию по умолчанию `IOleInPlaceObject` и `IOleInPlaceObjectWindowless` и реализует **IUnknown** при отправке информации для дампа строит устройства в режиме отладки.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp  
 Возвращает **E_NOTIMPL**.  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdroptarget"></a>IOleInPlaceObjectWindowlessImpl::GetDropTarget  
 Возвращает **E_NOTIMPL**.  
  
```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleInPlaceObjectWindowless::GetDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms678535) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getwindow"></a>IOleInPlaceObjectWindowlessImpl::GetWindow  
 Контейнер вызывает эту функцию, чтобы получить дескриптор окна элемента управления.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>Примечания  
 Некоторые контейнеры не будет работать с элементом управления, без окон, даже если он находится в данный момент оконные. В реализации библиотеки ATL Если данные-член класса control `m_bWasOnceWindowless` — **TRUE**, функция возвращает **E_FAIL**. В противном случае, если *phwnd* не **NULL**, `GetWindow` задает \* *phwnd* для члена данных класса управления `m_hWnd` и возвращает `S_OK`.  
  
 В разделе [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="inplacedeactivate"></a>IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate  
 Вызвать с помощью контейнера, чтобы деактивировать активный элемент управления на месте.  
  
```
HRESULT InPlaceDeactivate(HWND* phwnd);
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод выполняет полное или частичное деактивации в зависимости от состояния элемента управления. При необходимости отключения элемента управления пользовательского интерфейса и окна элемента управления, если таковые имеются, уничтожается. Контейнер получает уведомление, что элемент управления больше не активным на месте. **IOleInPlaceUIWindow** интерфейс, используемые контейнером для согласования меню и границы пространство освобождается.  
  
 В разделе [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="onwindowmessage"></a>IOleInPlaceObjectWindowlessImpl::OnWindowMessage  
 Отправляет сообщение в другой контейнер безоконный элемент управления, который является активным на месте.  
  
```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleInPlaceObjectWindowless::OnWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms693783) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="reactivateandundo"></a>IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo  
 Возвращает **E_NOTIMPL**.  
  
```
HRESULT ReactivateAndUndo();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setobjectrects"></a>IOleInPlaceObjectWindowlessImpl::SetObjectRects  
 Вызывается контейнером для информирования управления об изменении его размера и положения.  
  
```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```  
  
### <a name="remarks"></a>Примечания  
 Обновляет элемент управления `m_rcPos` элемента данных и отображения элемента управления. Отображается только часть элемента управления, который пересекает отсеченную область. Если отображение элемента управления была ранее обрезается, но вырезку был удален, эта функция может вызываться перерисовывает полное представление элемента управления.  
  
 В разделе [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="uideactivate"></a>IOleInPlaceObjectWindowlessImpl::UIDeactivate  
 Отключает и удаляет пользовательский интерфейс элемента управления, который поддерживает активацию на месте.  
  
```
HRESULT UIDeactivate();
```  
  
### <a name="remarks"></a>Примечания  
 Задает данные-член класса control `m_bUIActive` для **FALSE**. Это реализация ATL функция всегда возвращает `S_OK`.  
  
 В разделе [IOleInPlaceObject::UIDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms693348) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

