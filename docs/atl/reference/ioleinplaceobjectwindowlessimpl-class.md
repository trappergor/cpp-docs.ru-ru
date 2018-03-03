---
title: "Класс IOleInPlaceObjectWindowlessImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f455172723be4f46751b45d244e74dda5fcacae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>Класс IOleInPlaceObjectWindowlessImpl
Этот класс реализует **IUnknown** и предоставляет методы, позволяющие неоконным получать сообщения окна и участвовать в операции перетаскивания и вставки.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IOleInPlaceObjectWindowlessImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|Обеспечивает контекстную справку. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|Предоставляет `IDropTarget` интерфейс для объекта на месте активно, без окон, который поддерживает перетаскивание. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|Возвращает дескриптор окна.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|Деактивирует активный элемент управления на месте.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|Отправляет сообщение из контейнера в элемент управления без окон, который активен на месте.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|Реактивации ранее отключенного элемента управления. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|Указывает, какая часть элемента управления на месте является видимым.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|Деактивирует и удаляет пользовательский интерфейс, который поддерживает активацию на месте.|  
  
## <a name="remarks"></a>Примечания  
 [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) интерфейс управляет повторной активации и деактивации на месте и определяют, какая часть элемента управления должны быть видимыми. [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) интерфейс позволяет неоконным получать сообщения окна и участвовать в операции перетаскивания и вставки. Класс `IOleInPlaceObjectWindowlessImpl` предоставляет реализацию по умолчанию `IOleInPlaceObject` и `IOleInPlaceObjectWindowless` и реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
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
 В разделе [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) в Windows SDK.  
  
##  <a name="getdroptarget"></a>IOleInPlaceObjectWindowlessImpl::GetDropTarget  
 Возвращает **E_NOTIMPL**.  
  
```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleInPlaceObjectWindowless::GetDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms678535) в Windows SDK.  
  
##  <a name="getwindow"></a>IOleInPlaceObjectWindowlessImpl::GetWindow  
 Контейнер вызывает эту функцию, чтобы получить дескриптор окна элемента управления.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>Примечания  
 Некоторые контейнеры не будет работать с элементом управления, который был без окон, даже если в настоящее время оконные. В реализации ATL Если элемент данных класс элемента управления `m_bWasOnceWindowless` — **TRUE**, функция возвращает **E_FAIL**. В противном случае, если *phwnd* не **NULL**, `GetWindow` задает \* *phwnd* на данные-член класса элемента управления `m_hWnd` и возвращает `S_OK`.  
  
 В разделе [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) в Windows SDK.  
  
##  <a name="inplacedeactivate"></a>IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate  
 Вызывается контейнером, чтобы деактивировать активный элемент управления на месте.  
  
```
HRESULT InPlaceDeactivate(HWND* phwnd);
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод выполняет полный или частичный деактивации в зависимости от состояния элемента управления. При необходимости элемент управления пользовательского интерфейса отключена и окна элемента управления, если таковые имеются, удаляется. Контейнер получает уведомление о том, что элемент управления больше не активна на месте. **IOleInPlaceUIWindow** интерфейса, используемые контейнером для согласования меню и границы пространство освобождается.  
  
 В разделе [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) в Windows SDK.  
  
##  <a name="onwindowmessage"></a>IOleInPlaceObjectWindowlessImpl::OnWindowMessage  
 Отправляет сообщение в другой контейнер в элемент управления без окон, который активен на месте.  
  
```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleInPlaceObjectWindowless::OnWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms693783) в Windows SDK.  
  
##  <a name="reactivateandundo"></a>IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo  
 Возвращает **E_NOTIMPL**.  
  
```
HRESULT ReactivateAndUndo();
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) в Windows SDK.  
  
##  <a name="setobjectrects"></a>IOleInPlaceObjectWindowlessImpl::SetObjectRects  
 Вызывается контейнером для информирования об изменении его размера и положения элемента управления.  
  
```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```  
  
### <a name="remarks"></a>Примечания  
 Обновляет элемент управления `m_rcPos` элемента данных и отображения элемента управления. Отображается только часть элемента управления, который пересекается с отсеченную область. Если ранее выполнена Обрезка отображение элемента управления, но обрезки была удалена, эта функция может вызываться перерисовка полное представление элемента управления.  
  
 В разделе [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) в Windows SDK.  
  
##  <a name="uideactivate"></a>IOleInPlaceObjectWindowlessImpl::UIDeactivate  
 Деактивирует и удаляет пользовательский интерфейс элемента управления, которая поддерживает активацию на месте.  
  
```
HRESULT UIDeactivate();
```  
  
### <a name="remarks"></a>Примечания  
 Задает член данных класс элемента управления `m_bUIActive` для **FALSE**. Это реализация ATL функция всегда возвращает `S_OK`.  
  
 В разделе [IOleInPlaceObject::UIDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms693348) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
