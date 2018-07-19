---
title: Класс IOleInPlaceObjectWindowlessImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c48670ca6e7dd38e94a2c57f0a0c0415f654f445
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881494"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>Класс IOleInPlaceObjectWindowlessImpl
Этот класс реализует `IUnknown` и предоставляет методы, позволяющие безоконный элемент управления для получения оконных сообщений и принять участие в операциях перетаскивания и вставки.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `IOleInPlaceObjectWindowlessImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|Обеспечивает контекстную справку. Реализация ATL возвращает E_NOTIMPL.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|Блоки `IDropTarget` интерфейс для на месте активным безоконным объектом, который поддерживает перетаскивание. Реализация ATL возвращает E_NOTIMPL.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|Получает дескриптор окна.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|Деактивирует активный элемент управления на месте.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|Отправляет сообщение из контейнера элемент управления без окон, который активен на месте.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|Повторно активирует ранее отключенного элемента управления. Реализация ATL возвращает E_NOTIMPL.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|Указывает, какая часть встроенного элемента управления является видимым.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|Отключает и удаляет пользовательский интерфейс, который поддерживает активацию на месте.|  
  
## <a name="remarks"></a>Примечания  
 [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) интерфейс управляет повторной активации и деактивации непосредственно управляет и определяет, какая часть элемента управления должны быть видимыми. [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) интерфейс позволяет безоконный элемент управления для получения оконных сообщений и принять участие в операциях перетаскивания и вставки. Класс `IOleInPlaceObjectWindowlessImpl` предоставляет реализацию по умолчанию `IOleInPlaceObject` и `IOleInPlaceObjectWindowless` и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>  IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp  
 Возвращает E_NOTIMPL.  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) в Windows SDK.  
  
##  <a name="getdroptarget"></a>  IOleInPlaceObjectWindowlessImpl::GetDropTarget  
 Возвращает E_NOTIMPL.  
  
```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleInPlaceObjectWindowless::GetDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms678535) в Windows SDK.  
  
##  <a name="getwindow"></a>  IOleInPlaceObjectWindowlessImpl::GetWindow  
 Контейнер вызывает эту функцию, чтобы получить дескриптор окна элемента управления.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>Примечания  
 Некоторые контейнеры не будет работать с элементом управления, без окон, даже если он является в настоящее время оконные. В реализации библиотеки ATL Если элемент данных класса элемента управления `m_bWasOnceWindowless` имеет значение TRUE, функция возвращает E_FAIL. В противном случае, если *phwnd* не равно NULL, `GetWindow` задает \* *phwnd* на данные-член класса элемента управления `m_hWnd` и возвращает значение S_OK.  
  
 См. в разделе [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) в Windows SDK.  
  
##  <a name="inplacedeactivate"></a>  IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate  
 Вызвать с помощью контейнера, чтобы деактивировать активный элемент управления на месте.  
  
```
HRESULT InPlaceDeactivate(HWND* phwnd);
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод выполняет полный или частичный деактивации в зависимости от состояния элемента управления. При необходимости деактивации элемента управления пользовательского интерфейса и окна элемента управления, если таковые имеются, уничтожается. Контейнер отправляется уведомление, что больше не элемент управления активен на месте. `IOleInPlaceUIWindow` Интерфейса, используемые контейнером для согласования меню и границы пространство освобождается.  
  
 См. в разделе [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) в Windows SDK.  
  
##  <a name="onwindowmessage"></a>  IOleInPlaceObjectWindowlessImpl::OnWindowMessage  
 Отправляет сообщение из контейнера элемент управления без окон, который активен на месте.  
  
```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleInPlaceObjectWindowless::OnWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms693783) в Windows SDK.  
  
##  <a name="reactivateandundo"></a>  IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo  
 Возвращает E_NOTIMPL.  
  
```
HRESULT ReactivateAndUndo();
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) в Windows SDK.  
  
##  <a name="setobjectrects"></a>  IOleInPlaceObjectWindowlessImpl::SetObjectRects  
 Вызывается контейнером для информирования об изменении его размера и положения элемента управления.  
  
```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```  
  
### <a name="remarks"></a>Примечания  
 Обновляет элемент управления `m_rcPos` элемента данных и отображения элемента управления. Отображается только часть элемента управления, который пересекается с отсеченную область. Если отображение элемента управления был ранее обрезается, но было удалено обрезки, эта функция может вызываться для перерисовки полное представление элемента управления.  
  
 См. в разделе [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) в Windows SDK.  
  
##  <a name="uideactivate"></a>  IOleInPlaceObjectWindowlessImpl::UIDeactivate  
 Отключает и удаляет пользовательский интерфейс элемента управления, который поддерживает активацию на месте.  
  
```
HRESULT UIDeactivate();
```  
  
### <a name="remarks"></a>Примечания  
 Задает член данных класса элемента управления `m_bUIActive` значение false. Реализация ATL эта функция всегда возвращает значение S_OK.  
  
 См. в разделе [IOleInPlaceObject::UIDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms693348) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
