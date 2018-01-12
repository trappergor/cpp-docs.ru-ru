---
title: "Класс IOleObjectImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl::Advise
- ATLCTL/ATL::IOleObjectImpl::Close
- ATLCTL/ATL::IOleObjectImpl::DoVerb
- ATLCTL/ATL::IOleObjectImpl::DoVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::DoVerbHide
- ATLCTL/ATL::IOleObjectImpl::DoVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::DoVerbOpen
- ATLCTL/ATL::IOleObjectImpl::DoVerbPrimary
- ATLCTL/ATL::IOleObjectImpl::DoVerbShow
- ATLCTL/ATL::IOleObjectImpl::DoVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::EnumAdvise
- ATLCTL/ATL::IOleObjectImpl::EnumVerbs
- ATLCTL/ATL::IOleObjectImpl::GetClientSite
- ATLCTL/ATL::IOleObjectImpl::GetClipboardData
- ATLCTL/ATL::IOleObjectImpl::GetExtent
- ATLCTL/ATL::IOleObjectImpl::GetMiscStatus
- ATLCTL/ATL::IOleObjectImpl::GetMoniker
- ATLCTL/ATL::IOleObjectImpl::GetUserClassID
- ATLCTL/ATL::IOleObjectImpl::GetUserType
- ATLCTL/ATL::IOleObjectImpl::InitFromData
- ATLCTL/ATL::IOleObjectImpl::IsUpToDate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::SetClientSite
- ATLCTL/ATL::IOleObjectImpl::SetColorScheme
- ATLCTL/ATL::IOleObjectImpl::SetExtent
- ATLCTL/ATL::IOleObjectImpl::SetHostNames
- ATLCTL/ATL::IOleObjectImpl::SetMoniker
- ATLCTL/ATL::IOleObjectImpl::Unadvise
- ATLCTL/ATL::IOleObjectImpl::Update
dev_langs: C++
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f710953a32ccb32c63742ab28e84818f3a330336
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ioleobjectimpl-class"></a>Класс IOleObjectImpl
Этот класс реализует **IUnknown** и — это основной интерфейс, через который контейнер связывается с элементом управления.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IOleObjectImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IOleObjectImpl::Advise](#advise)|Устанавливает вспомогательное соединение с элементом управления.|  
|[IOleObjectImpl::Close](#close)|Изменяет состояние элемента управления «выполняется» на загружена.|  
|[IOleObjectImpl::DoVerb](#doverb)|Указывает элемент управления для выполнения одного из его перечисленные действия.|  
|[IOleObjectImpl::DoVerbDiscardUndo](#doverbdiscardundo)|Указывает элемент управления, чтобы отменить все состояния отмены, который он входит поддержка.|  
|[IOleObjectImpl::DoVerbHide](#doverbhide)|Указывает элемент управления, чтобы удалить свой пользовательский интерфейс из представления.|  
|[IOleObjectImpl::DoVerbInPlaceActivate](#doverbinplaceactivate)|Работает элемент управления и устанавливает его окна, но не устанавливает пользовательский интерфейс элемента управления.|  
|[IOleObjectImpl::DoVerbOpen](#doverbopen)|Заставляет элемент управления, необходимо изменить открытым в отдельном окне.|  
|[IOleObjectImpl::DoVerbPrimary](#doverbprimary)|Выполняет указанное действие, когда пользователь дважды щелкает элемент управления. Элемент управления определяет действие, как правило, чтобы активировать элемент управления на месте.|  
|[IOleObjectImpl::DoVerbShow](#doverbshow)|Показывает вставленный элемент управления для пользователя.|  
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|Активирует элемент управления на месте и отображает пользовательский интерфейс элемента управления, например меню и панелей инструментов.|  
|[IOleObjectImpl::EnumAdvise](#enumadvise)|Перечисляет соединений для рекомендаций элемента управления.|  
|[IOleObjectImpl::EnumVerbs](#enumverbs)|Перечисляет действия для элемента управления.|  
|[IOleObjectImpl::GetClientSite](#getclientsite)|Извлекает узел клиентского элемента управления.|  
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|Извлекает данные из буфера обмена. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IOleObjectImpl::GetExtent](#getextent)|Получает экстент отображаемую область элемента управления.|  
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|Получает сведения о состоянии элемента управления.|  
|[IOleObjectImpl::GetMoniker](#getmoniker)|Возвращает специальное имя элемента управления. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|Получает идентификатор класса элемента управления.|  
|[IOleObjectImpl::GetUserType](#getusertype)|Возвращает имя пользователя тип элемента управления.|  
|[IOleObjectImpl::InitFromData](#initfromdata)|Инициализирует элемент управления из выбранных данных. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IOleObjectImpl::IsUpToDate](#isuptodate)|Проверяет, является ли элемент управления в актуальном состоянии. Возвращает реализацию ATL `S_OK`.|  
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|Вызывается методом [DoVerbDiscardUndo](#doverbdiscardundo) после отбрасывается состояния отмены.|  
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|Вызывается методом [DoVerbHide](#doverbhide) после элемент управления скрыт.|  
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|Вызывается методом [DoVerbInPlaceActivate](#doverbinplaceactivate) после активации элемента управления на месте.|  
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|Вызывается методом [DoVerbOpen](#doverbopen) после открытия элемента управления для редактирования в отдельном окне.|  
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|Вызывается методом [DoVerbShow](#doverbshow) после элемента управления был сделан видимым.|  
|[IOleObjectImpl::OnPostVerbUIActivate](#onpostverbuiactivate)|Вызывается методом [DoVerbUIActivate](#doverbuiactivate) после активации элемента управления пользовательского интерфейса.|  
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|Вызывается методом [DoVerbDiscardUndo](#doverbdiscardundo) до отмены состояние будет удалено.|  
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|Вызывается методом [DoVerbHide](#doverbhide) прежде, чем элемент управления скрыт.|  
|[IOleObjectImpl::OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|Вызывается методом [DoVerbInPlaceActivate](#doverbinplaceactivate) до активации на месте элемента управления.|  
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|Вызывается методом [DoVerbOpen](#doverbopen) прежде, чем элемент управления был открыт для редактирования в отдельном окне.|  
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|Вызывается методом [DoVerbShow](#doverbshow) прежде, чем элемент управления был сделан видимым.|  
|[IOleObjectImpl::OnPreVerbUIActivate](#onpreverbuiactivate)|Вызывается методом [DoVerbUIActivate](#doverbuiactivate) до активации элемента управления пользовательского интерфейса.|  
|[IOleObjectImpl::SetClientSite](#setclientsite)|Элемент управления сообщает о его клиента сайтом в контейнере.|  
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|Корпорация Майкрософт рекомендует цветовую схему элемент управления приложением, если таковые имеются. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IOleObjectImpl::SetExtent](#setextent)|Задает степень отображаемую область элемента управления.|  
|[IOleObjectImpl::SetHostNames](#sethostnames)|Сообщает родительскому элементу имена приложение контейнера и документе-контейнере.|  
|[IOleObjectImpl::SetMoniker](#setmoniker)|Сообщает родительскому элементу является его моникера. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IOleObjectImpl::Unadvise](#unadvise)|Удаляет вспомогательное соединение с элементом управления.|  
|[IOleObjectImpl::Update](#update)|Обновляет элемент управления. Возвращает реализацию ATL `S_OK`.|  
  
## <a name="remarks"></a>Примечания  
 [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709) интерфейса — это основной интерфейс, через который контейнер связывается с элементом управления. Класс `IOleObjectImpl` предоставляет стандартную реализацию этого интерфейса и реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IOleObject`  
  
 `IOleObjectImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="advise"></a>IOleObjectImpl::Advise  
 Устанавливает вспомогательное соединение с элементом управления.  
  
```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573) в Windows SDK.  
  
##  <a name="close"></a>IOleObjectImpl::Close  
 Изменяет состояние элемента управления «выполняется» на загружена.  
  
```
STDMETHOD(Close)(DWORD dwSaveOption);
```  
  
### <a name="remarks"></a>Примечания  
 Отключает элемент управления и уничтожает окно элемента управления, если он существует. Если данные-член класса элемента управления [CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) — **TRUE** и `dwSaveOption` имеет значение `OLECLOSE_SAVEIFDIRTY` или `OLECLOSE_PROMPTSAVE`, сохраняются свойства элемента управления Перед закрытием.  
  
 Указатели, которые содержатся в данные-члены класса элемента управления [CComControlBase::m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) и [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) освобождаются и данные-члены [CComControlBase:: m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd), [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless), и [CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) присваиваются **FALSE**.  
  
 В разделе [IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922) в Windows SDK.  
  
##  <a name="doverb"></a>IOleObjectImpl::DoVerb  
 Указывает элемент управления для выполнения одного из его перечисленные действия.  
  
```
STDMETHOD(DoVerb)(
    LONG iVerb,
    LPMSG /* pMsg */,
    IOleClientSite* pActiveSite,
    LONG /* lindex */,
    HWND hwndParent,
    LPCRECT lprcPosRect);
```  
  
### <a name="remarks"></a>Примечания  
 В зависимости от значения `iVerb`, один из библиотеки ATL `DoVerb` вспомогательные функции вызывается следующим образом:  
  
|*iVerb* значение|DoVerb вспомогательная функция, вызываемая|  
|-------------------|-----------------------------------|  
|**OLEIVERB_DISCARDUNDOSTATE**|[DoVerbDiscardUndo](#doverbdiscardundo)|  
|`OLEIVERB_HIDE`|[DoVerbHide](#doverbhide)|  
|**OLEIVERB_INPLACEACTIVATE**|[DoVerbInPlaceActivate](#doverbinplaceactivate)|  
|`OLEIVERB_OPEN`|[DoVerbOpen](#doverbopen)|  
|`OLEIVERB_PRIMARY`|[DoVerbPrimary](#doverbprimary)|  
|**OLEIVERB_PROPERTIES**|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|  
|`OLEIVERB_SHOW`|[DoVerbShow](#doverbshow)|  
|`OLEIVERB_UIACTIVATE`|[DoVerbUIActivate](#doverbuiactivate)|  
  
 В разделе [функция IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) в Windows SDK.  
  
##  <a name="doverbdiscardundo"></a>IOleObjectImpl::DoVerbDiscardUndo  
 Указывает элемент управления, чтобы отменить все состояния отмены, который он входит поддержка.  
  
```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Параметры  
 `prcPosRec`  
 [in] Указатель на прямоугольник контейнера хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
##  <a name="doverbhide"></a>IOleObjectImpl::DoVerbHide  
 Деактивирует и удаляет элемент управления пользовательского интерфейса и скрывает элемент управления.  
  
```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Параметры  
 `prcPosRec`  
 [in] Указатель на прямоугольник контейнера хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления. В реализации ATL не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
##  <a name="doverbinplaceactivate"></a>IOleObjectImpl::DoVerbInPlaceActivate  
 Работает элемент управления и устанавливает его окна, но не устанавливает пользовательский интерфейс элемента управления.  
  
```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Параметры  
 `prcPosRec`  
 [in] Указатель на прямоугольник контейнера хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления. В реализации ATL не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 Активирует элемент управления на месте, вызвав [CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate). Если элемент данных класс элемента управления `m_bWindowOnly` — **TRUE**, `DoVerbInPlaceActivate` сначала пытается активировать элемент управления без окна (возможно только в том случае, если контейнер поддерживает [IOleInPlaceSiteWindowless ](http://msdn.microsoft.com/library/windows/desktop/ms682300)). В случае неудачи, функция пытается активировать элемент управления с расширенные функции (возможно только в том случае, если контейнер поддерживает [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461)). В случае неудачи, функция пытается активировать управления без расширенных функций (возможно только в том случае, если контейнер поддерживает [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586)). При успешной активации функции уведомляет контейнера элемента управления был активирован.  
  
##  <a name="doverbopen"></a>IOleObjectImpl::DoVerbOpen  
 Заставляет элемент управления, необходимо изменить открытым в отдельном окне.  
  
```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Параметры  
 `prcPosRec`  
 [in] Указатель на прямоугольник контейнера хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
##  <a name="doverbprimary"></a>IOleObjectImpl::DoVerbPrimary  
 Определяет действие, выполняемое при двойном щелчке элемента управления.  
  
```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```  
  
### <a name="parameters"></a>Параметры  
 `prcPosRec`  
 [in] Указатель на прямоугольник контейнера хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию значение для отображения страницы свойств. Это можно переопределить в классе элемента управления, чтобы вызвать другое поведение при двойном щелчке; Например воспроизведения видео или посетите активным на месте.  
  
##  <a name="doverbshow"></a>IOleObjectImpl::DoVerbShow  
 Указывает контейнер так, чтобы сделать элемент управления видимым.  
  
```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Параметры  
 `prcPosRec`  
 [in] Указатель на прямоугольник контейнера хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления. В реализации ATL не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
##  <a name="doverbuiactivate"></a>IOleObjectImpl::DoVerbUIActivate  
 Активирует элемент управления пользовательского интерфейса и уведомляет контейнер, его меню заменяются составного меню.  
  
```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Параметры  
 `prcPosRec`  
 [in] Указатель на прямоугольник контейнера хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления. В реализации ATL не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
##  <a name="enumadvise"></a>IOleObjectImpl::EnumAdvise  
 Предоставляет перечисление зарегистрированных соединений для рекомендаций для этого элемента управления.  
  
```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleObject::EnumAdvise](http://msdn.microsoft.com/library/windows/desktop/ms682355) в Windows SDK.  
  
##  <a name="enumverbs"></a>IOleObjectImpl::EnumVerbs  
 Предоставляет перечисление зарегистрированных действий (команд) для этого элемента управления путем вызова **OleRegEnumVerbs**.  
  
```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```  
  
### <a name="remarks"></a>Примечания  
 Можно добавить команды в RGS-файле проекта. Например в разделе CIRCCTL. RGS в [CIRC](../../visual-cpp-samples.md) образца.  
  
 В разделе [IOleObject::EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781) в Windows SDK.  
  
##  <a name="getclientsite"></a>IOleObjectImpl::GetClientSite  
 Наведение указателя мыши в элемент управления класса данных [CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) в *ppClientSite* и увеличивает значение счетчика ссылок для указателя.  
  
```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleObject::GetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms692603) в Windows SDK.  
  
##  <a name="getclipboarddata"></a>IOleObjectImpl::GetClipboardData  
 Извлекает данные из буфера обмена.  
  
```
STDMETHOD(GetClipboardData)(    
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleObject::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms682288) в Windows SDK.  
  
##  <a name="getextent"></a>IOleObjectImpl::GetExtent  
 Получает размер отображения выполнение элемента управления в единицах HIMETRIC (0,01 мм на единицу).  
  
```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>Примечания  
 Размер хранится в элемент управления класса данных [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).  
  
 В разделе [IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) в Windows SDK.  
  
##  <a name="getmiscstatus"></a>IOleObjectImpl::GetMiscStatus  
 Возвращает указатель на сведения о состоянии, зарегистрированных для элемента управления путем вызова **OleRegGetMiscStatus**.  
  
```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>Примечания  
 Сведения о состоянии включают поведения, поддерживаемых данными элемента управления и представление. Можно добавить сведения о состоянии в RGS-файле проекта.  
  
 В разделе [IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521) в Windows SDK.  
  
##  <a name="getmoniker"></a>IOleObjectImpl::GetMoniker  
 Возвращает специальное имя элемента управления.  
  
```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleObject::GetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms686576) в Windows SDK.  
  
##  <a name="getuserclassid"></a>IOleObjectImpl::GetUserClassID  
 Возвращает идентификатор класса элемента управления.  
  
```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleObject::GetUserClassID](http://msdn.microsoft.com/library/windows/desktop/ms682313) в Windows SDK.  
  
##  <a name="getusertype"></a>IOleObjectImpl::GetUserType  
 Возвращает имя пользователя тип элемента управления путем вызова **OleRegGetUserType**.  
  
```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```  
  
### <a name="remarks"></a>Примечания  
 Имя пользовательского типа используется для отображения в пользовательских интерфейсах элементы, такие как меню и диалоговые окна. Можно изменить имя пользовательского типа в RGS-файле проекта.  
  
 В разделе [IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643) в Windows SDK.  
  
##  <a name="initfromdata"></a>IOleObjectImpl::InitFromData  
 Инициализирует элемент управления из выбранных данных.  
  
```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) в Windows SDK.  
  
##  <a name="isuptodate"></a>IOleObjectImpl::IsUpToDate  
 Проверяет, является ли элемент управления в актуальном состоянии.  
  
```
STDMETHOD(IsUpToDate)(void);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleObject::IsUpToDate](http://msdn.microsoft.com/library/windows/desktop/ms686624) в Windows SDK.  
  
##  <a name="onpostverbdiscardundo"></a>IOleObjectImpl::OnPostVerbDiscardUndo  
 Вызывается методом [DoVerbDiscardUndo](#doverbdiscardundo) после отбрасывается состояния отмены.  
  
```
HRESULT OnPostVerbDiscardUndo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод с код, который должен выполняться после отмены состояние будет удалено.  
  
##  <a name="onpostverbhide"></a>IOleObjectImpl::OnPostVerbHide  
 Вызывается методом [DoVerbHide](#doverbhide) после элемент управления скрыт.  
  
```
HRESULT OnPostVerbHide();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод с код, который должен выполняться после элемент управления скрыт.  
  
##  <a name="onpostverbinplaceactivate"></a>IOleObjectImpl::OnPostVerbInPlaceActivate  
 Вызывается методом [DoVerbInPlaceActivate](#doverbinplaceactivate) после активации элемента управления на месте.  
  
```
HRESULT OnPostVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод с код, который должен выполняться после активации элемента управления на месте.  
  
##  <a name="onpostverbopen"></a>IOleObjectImpl::OnPostVerbOpen  
 Вызывается методом [DoVerbOpen](#doverbopen) после открытия элемента управления для редактирования в отдельном окне.  
  
```
HRESULT OnPostVerbOpen();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод с код, который должен выполняться после элемента управления был открыт для редактирования в отдельном окне.  
  
##  <a name="onpostverbshow"></a>IOleObjectImpl::OnPostVerbShow  
 Вызывается методом [DoVerbShow](#doverbshow) после элемента управления был сделан видимым.  
  
```
HRESULT OnPostVerbShow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод с код, который должен выполняться после элемента управления был сделан видимым.  
  
##  <a name="onpostverbuiactivate"></a>IOleObjectImpl::OnPostVerbUIActivate  
 Вызывается методом [DoVerbUIActivate](#doverbuiactivate) после активации элемента управления пользовательского интерфейса.  
  
```
HRESULT OnPostVerbUIActivate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, с помощью кода, который требуется выполнить после активации элемента управления пользовательского интерфейса.  
  
##  <a name="onpreverbdiscardundo"></a>IOleObjectImpl::OnPreVerbDiscardUndo  
 Вызывается методом [DoVerbDiscardUndo](#doverbdiscardundo) до отмены состояние будет удалено.  
  
```
HRESULT OnPreVerbDiscardUndo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы избежать состояния отмены удаления, переопределите этот метод возвращает ошибку HRESULT.  
  
##  <a name="onpreverbhide"></a>IOleObjectImpl::OnPreVerbHide  
 Вызывается методом [DoVerbHide](#doverbhide) прежде, чем элемент управления скрыт.  
  
```
HRESULT OnPreVerbHide();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы предотвратить скрываемый элемент управления, переопределите этот метод возвращает ошибку HRESULT.  
  
##  <a name="onpreverbinplaceactivate"></a>IOleObjectImpl::OnPreVerbInPlaceActivate  
 Вызывается методом [DoVerbInPlaceActivate](#doverbinplaceactivate) до активации на месте элемента управления.  
  
```
HRESULT OnPreVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы предотвратить активации на месте элемента управления, переопределите этот метод возвращает ошибку HRESULT.  
  
##  <a name="onpreverbopen"></a>IOleObjectImpl::OnPreVerbOpen  
 Вызывается методом [DoVerbOpen](#doverbopen) прежде, чем элемент управления был открыт для редактирования в отдельном окне.  
  
```
HRESULT OnPreVerbOpen();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы открыть для редактирования в отдельном окне элемент управления, переопределите этот метод возвращает ошибку HRESULT.  
  
##  <a name="onpreverbshow"></a>IOleObjectImpl::OnPreVerbShow  
 Вызывается методом [DoVerbShow](#doverbshow) прежде, чем элемент управления был сделан видимым.  
  
```
HRESULT OnPreVerbShow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы элемент управления было нельзя сделать видимым, переопределите этот метод возвращает ошибку HRESULT.  
  
##  <a name="onpreverbuiactivate"></a>IOleObjectImpl::OnPreVerbUIActivate  
 Вызывается методом [DoVerbUIActivate](#doverbuiactivate) до активации элемента управления пользовательского интерфейса.  
  
```
HRESULT OnPreVerbUIActivate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 Чтобы предотвратить время активации элемента управления пользовательского интерфейса, переопределите этот метод возвращает ошибку HRESULT.  
  
##  <a name="setclientsite"></a>IOleObjectImpl::SetClientSite  
 Элемент управления сообщает о его клиента сайтом в контейнере.  
  
```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```  
  
### <a name="remarks"></a>Примечания  
 Затем метод возвращает `S_OK`.  
  
 В разделе [IOleObject::SetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms684013) в Windows SDK.  
  
##  <a name="setcolorscheme"></a>IOleObjectImpl::SetColorScheme  
 Корпорация Майкрософт рекомендует цветовую схему элемент управления приложением, если таковые имеются.  
  
```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) в Windows SDK.  
  
##  <a name="setextent"></a>IOleObjectImpl::SetExtent  
 Задает степень отображаемую область элемента управления.  
  
```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>Примечания  
 В противном случае `SetExtent` сохраняет значение, на который указывает `psizel` в элемент управления класса данных [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent). Это значение задается в единицах HIMETRIC (0,01 мм на единицу).  
  
 Если данные-член класса элемента управления [CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) — **TRUE**, `SetExtent` также сохраняет значение, на который указывает `psizel` в элемент управления класса данных [CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural).  
  
 Если данные-член класса элемента управления [CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) — **TRUE**, `SetExtent` вызовы `SendOnDataChange` и `SendOnViewChange` известить все приемники зарегистрирована уведомить владельца об изменении размера элемента управления.  
  
 В разделе [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) в Windows SDK.  
  
##  <a name="sethostnames"></a>IOleObjectImpl::SetHostNames  
 Сообщает родительскому элементу имена приложение контейнера и документе-контейнере.  
  
```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) в Windows SDK.  
  
##  <a name="setmoniker"></a>IOleObjectImpl::SetMoniker  
 Сообщает родительскому элементу является его моникера.  
  
```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleObject::SetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679671) в Windows SDK.  
  
##  <a name="unadvise"></a>IOleObjectImpl::Unadvise  
 Удаляет вспомогательное соединение, хранящихся в класс элемента управления `m_spOleAdviseHolder` члена данных.  
  
```
STDMETHOD(Unadvise)(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749) в Windows SDK.  
  
##  <a name="update"></a>IOleObjectImpl::Update  
 Обновляет элемент управления.  
  
```
STDMETHOD(Update)(void);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IOleObject::Update](http://msdn.microsoft.com/library/windows/desktop/ms679699) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Интерфейсы, элементы управления ActiveX](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
