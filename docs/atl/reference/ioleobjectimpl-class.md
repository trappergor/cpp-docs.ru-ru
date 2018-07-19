---
title: Класс IOleObjectImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aec4de071df8dcca960a0f1cb802375e5553ceb3
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880308"
---
# <a name="ioleobjectimpl-class"></a>Класс IOleObjectImpl
Этот класс реализует `IUnknown` и — это основной интерфейс, через который контейнер взаимодействует с элементом управления.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `IOleObjectImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IOleObjectImpl::Advise](#advise)|Устанавливает вспомогательное соединение с элементом управления.|  
|[IOleObjectImpl::Close](#close)|Изменяет состояние элемента управления «выполняется» на загруженных.|  
|[IOleObjectImpl::DoVerb](#doverb)|Сообщает родительскому элементу для выполнения одной из его перечисленные действия.|  
|[IOleObjectImpl::DoVerbDiscardUndo](#doverbdiscardundo)|Сообщает родительскому элементу, чтобы отменить все состояния отмены, это субъект.|  
|[IOleObjectImpl::DoVerbHide](#doverbhide)|Сообщает родительскому элементу, чтобы удалить его пользовательский интерфейс из представления.|  
|[IOleObjectImpl::DoVerbInPlaceActivate](#doverbinplaceactivate)|Выполняет элемент управления и устанавливает его окна, но не устанавливает элемент управления пользовательского интерфейса.|  
|[IOleObjectImpl::DoVerbOpen](#doverbopen)|Элемент управления можно изменять открытым в отдельном окне.|  
|[IOleObjectImpl::DoVerbPrimary](#doverbprimary)|Выполняет указанное действие, когда пользователь дважды щелкает элемент управления. Элемент управления определяет действие, как правило, чтобы активировать элемент управления на месте.|  
|[IOleObjectImpl::DoVerbShow](#doverbshow)|Показывает элемент управления вновь добавленному пользователю.|  
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|Активирует элемент управления на месте и показан пользовательский интерфейс элемента управления, такие как меню и панелей инструментов.|  
|[IOleObjectImpl::EnumAdvise](#enumadvise)|Перечисляет вспомогательных соединений с элемента управления.|  
|[IOleObjectImpl::EnumVerbs](#enumverbs)|Перечисляет действия для элемента управления.|  
|[IOleObjectImpl::GetClientSite](#getclientsite)|Извлекает узел клиентского элемента управления.|  
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|Извлекает данные из буфера обмена. Реализация ATL возвращает E_NOTIMPL.|  
|[IOleObjectImpl::GetExtent](#getextent)|Получает экстент область отображения элемента управления.|  
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|Получает сведения о состоянии элемента управления.|  
|[IOleObjectImpl::GetMoniker](#getmoniker)|Получает моникер элемента управления. Реализация ATL возвращает E_NOTIMPL.|  
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|Извлекает идентификатор класса элемента управления.|  
|[IOleObjectImpl::GetUserType](#getusertype)|Извлекает имя пользовательского типа элемента управления.|  
|[IOleObjectImpl::InitFromData](#initfromdata)|Инициализирует элемент управления из выбранных данных. Реализация ATL возвращает E_NOTIMPL.|  
|[IOleObjectImpl::IsUpToDate](#isuptodate)|Проверяет, является ли элемент управления в актуальном состоянии. Реализация ATL, возвращается значение s_ок.|  
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|Вызывается средой [DoVerbDiscardUndo](#doverbdiscardundo) после отбрасывания состояния отмены.|  
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|Вызывается средой [DoVerbHide](#doverbhide) после скрытия элемента управления.|  
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|Вызывается средой [DoVerbInPlaceActivate](#doverbinplaceactivate) после активации элемента управления на месте.|  
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|Вызывается средой [DoVerbOpen](#doverbopen) после открытия элемента управления для редактирования в отдельном окне.|  
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|Вызывается средой [DoVerbShow](#doverbshow) после элемента управления видимой.|  
|[IOleObjectImpl::OnPostVerbUIActivate](#onpostverbuiactivate)|Вызывается средой [DoVerbUIActivate](#doverbuiactivate) после активации элемента управления пользовательского интерфейса.|  
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|Вызывается средой [DoVerbDiscardUndo](#doverbdiscardundo) до отмены состояние удаляется.|  
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|Вызывается средой [DoVerbHide](#doverbhide) прежде, чем элемент управления скрыт.|  
|[IOleObjectImpl::OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|Вызывается средой [DoVerbInPlaceActivate](#doverbinplaceactivate) прежде, чем элемент управления активирован на месте.|  
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|Вызывается средой [DoVerbOpen](#doverbopen) прежде, чем элемент управления был открыт для редактирования в отдельном окне.|  
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|Вызывается средой [DoVerbShow](#doverbshow) прежде, чем элемент управления стала видимой.|  
|[IOleObjectImpl::OnPreVerbUIActivate](#onpreverbuiactivate)|Вызывается средой [DoVerbUIActivate](#doverbuiactivate) до активации элемента управления пользовательского интерфейса.|  
|[IOleObjectImpl::SetClientSite](#setclientsite)|Указывает элементу управления о своему клиентскому сайту в контейнере.|  
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|Рекомендует цветовую схему для приложения элемента управления, если таковые имеются. Реализация ATL возвращает E_NOTIMPL.|  
|[IOleObjectImpl::SetExtent](#setextent)|Задает степень область отображения элемента управления.|  
|[IOleObjectImpl::SetHostNames](#sethostnames)|Сообщает родительскому элементу, имена приложения-контейнера и документе-контейнере.|  
|[IOleObjectImpl::SetMoniker](#setmoniker)|Сообщает родительскому элементу Каково его моникер. Реализация ATL возвращает E_NOTIMPL.|  
|[IOleObjectImpl::Unadvise](#unadvise)|Удаляет вспомогательное соединение с элементом управления.|  
|[IOleObjectImpl::Update](#update)|Обновляет элемент управления. Реализация ATL, возвращается значение s_ок.|  
  
## <a name="remarks"></a>Примечания  
 [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709) это основной интерфейс, через который контейнер взаимодействует с элементом управления. Класс `IOleObjectImpl` предоставляет стандартную реализацию этого интерфейса и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IOleObject`  
  
 `IOleObjectImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="advise"></a>  IOleObjectImpl::Advise  
 Устанавливает вспомогательное соединение с элементом управления.  
  
```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573) в Windows SDK.  
  
##  <a name="close"></a>  IOleObjectImpl::Close  
 Изменяет состояние элемента управления «выполняется» на загруженных.  
  
```
STDMETHOD(Close)(DWORD dwSaveOption);
```  
  
### <a name="remarks"></a>Примечания  
 Отключает элемент управления и уничтожает окно элемента управления, если он существует. Если член данных класса элемента управления [CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) имеет значение TRUE и *dwSaveOption* OLECLOSE_SAVEIFDIRTY или OLECLOSE_PROMPTSAVE, свойства элемента управления сохранены перед закрытием.  
  
 Указатели, хранящиеся в данные-члены класса элемента управления [CComControlBase::m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) и [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) освобождаются и данные-члены [CComControlBase:: m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd), [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless), и [CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) имеют значение FALSE.  
  
 См. в разделе [IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922) в Windows SDK.  
  
##  <a name="doverb"></a>  IOleObjectImpl::DoVerb  
 Сообщает родительскому элементу для выполнения одной из его перечисленные действия.  
  
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
  
|*iVerb* значение|DoVerb вспомогательную функцию, именуемую|  
|-------------------|-----------------------------------|  
|OLEIVERB_DISCARDUNDOSTATE|[DoVerbDiscardUndo](#doverbdiscardundo)|  
|OLEIVERB_HIDE|[DoVerbHide](#doverbhide)|  
|OLEIVERB_INPLACEACTIVATE|[DoVerbInPlaceActivate](#doverbinplaceactivate)|  
|OLEIVERB_OPEN|[DoVerbOpen](#doverbopen)|  
|OLEIVERB_PRIMARY|[DoVerbPrimary](#doverbprimary)|  
|OLEIVERB_PROPERTIES|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|  
|OLEIVERB_SHOW|[DoVerbShow](#doverbshow)|  
|OLEIVERB_UIACTIVATE|[DoVerbUIActivate](#doverbuiactivate)|  
  
 См. в разделе [функция IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) в Windows SDK.  
  
##  <a name="doverbdiscardundo"></a>  IOleObjectImpl::DoVerbDiscardUndo  
 Сообщает родительскому элементу, чтобы отменить все состояния отмены, это субъект.  
  
```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Параметры  
 *prcPosRec*  
 [in] Указатель на прямоугольник, контейнер хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
##  <a name="doverbhide"></a>  IOleObjectImpl::DoVerbHide  
 Отключает и удаляет элемент управления пользовательского интерфейса и скрывает элемент управления.  
  
```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Параметры  
 *prcPosRec*  
 [in] Указатель на прямоугольник, контейнер хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления. В реализации ATL не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
##  <a name="doverbinplaceactivate"></a>  IOleObjectImpl::DoVerbInPlaceActivate  
 Выполняет элемент управления и устанавливает его окна, но не устанавливает элемент управления пользовательского интерфейса.  
  
```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Параметры  
 *prcPosRec*  
 [in] Указатель на прямоугольник, контейнер хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления. В реализации ATL не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Активирует элемент управления на месте, вызвав [CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate). Если элемент данных класса элемента управления `m_bWindowOnly` имеет значение TRUE, `DoVerbInPlaceActivate` сначала попытается выполнить активацию элемента управления без окна (возможно только в том случае, если контейнер поддерживает [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300)). В случае неудачи функция пытается активировать элемент управления с помощью расширенных функций (возможно только в том случае, если контейнер поддерживает [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461)). В случае неудачи функция пытается активировать элемент управления без расширенных функций (возможно только в том случае, если контейнер поддерживает [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586)). При успешной активации функции уведомляет контейнер, что элемент управления был активирован.  
  
##  <a name="doverbopen"></a>  IOleObjectImpl::DoVerbOpen  
 Элемент управления можно изменять открытым в отдельном окне.  
  
```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Параметры  
 *prcPosRec*  
 [in] Указатель на прямоугольник, контейнер хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
##  <a name="doverbprimary"></a>  IOleObjectImpl::DoVerbPrimary  
 Определяет действие, выполняемое при двойном щелчке элемента управления.  
  
```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```  
  
### <a name="parameters"></a>Параметры  
 *prcPosRec*  
 [in] Указатель на прямоугольник, контейнер хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию значение для отображения страницы свойств. Это можно переопределить в классе элемента управления для вызова к другим действиям по двойному щелчку; Например воспроизведения видео или посетите локально активными.  
  
##  <a name="doverbshow"></a>  IOleObjectImpl::DoVerbShow  
 Сообщает контейнеру, чтобы сделать элемент управления видимым.  
  
```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Параметры  
 *prcPosRec*  
 [in] Указатель на прямоугольник, контейнер хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления. В реализации ATL не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="doverbuiactivate"></a>  IOleObjectImpl::DoVerbUIActivate  
 Активирует элемент управления пользовательского интерфейса и уведомляет контейнер, что его меню заменено составным меню.  
  
```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Параметры  
 *prcPosRec*  
 [in] Указатель на прямоугольник, контейнер хочет для рисования в элемент управления.  
  
 *hwndParent*  
 [in] Дескриптор окна, содержащего элемент управления. В реализации ATL не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="enumadvise"></a>  IOleObjectImpl::EnumAdvise  
 Предоставляет перечисление зарегистрированных вспомогательных соединений для этого элемента управления.  
  
```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleObject::EnumAdvise](http://msdn.microsoft.com/library/windows/desktop/ms682355) в Windows SDK.  
  
##  <a name="enumverbs"></a>  IOleObjectImpl::EnumVerbs  
 Предоставляет перечисление зарегистрированных действий (команды) для данного элемента управления путем вызова `OleRegEnumVerbs`.  
  
```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```  
  
### <a name="remarks"></a>Примечания  
 Можно добавить команды в RGS-файл проекта. Например см. в разделе CIRCCTL. RGS в [Кр](../../visual-cpp-samples.md) образца.  
  
 См. в разделе [IOleObject::EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781) в Windows SDK.  
  
##  <a name="getclientsite"></a>  IOleObjectImpl::GetClientSite  
 Наведение указателя мыши в элементе управления класс данных [CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) в *ppClientSite* и увеличивает счетчик ссылок для указателя.  
  
```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleObject::GetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms692603) в Windows SDK.  
  
##  <a name="getclipboarddata"></a>  IOleObjectImpl::GetClipboardData  
 Извлекает данные из буфера обмена.  
  
```
STDMETHOD(GetClipboardData)(    
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает E_NOTIMPL.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleObject::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms682288) в Windows SDK.  
  
##  <a name="getextent"></a>  IOleObjectImpl::GetExtent  
 Извлекает отображаемый размер элемента, работающей в единицах HIMETRIC (0,01 мм на единицу).  
  
```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>Примечания  
 Размер хранится в данные-член класса элемента управления [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).  
  
 См. в разделе [IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) в Windows SDK.  
  
##  <a name="getmiscstatus"></a>  IOleObjectImpl::GetMiscStatus  
 Возвращает указатель на сведения о зарегистрированных состоянии для элемента управления путем вызова `OleRegGetMiscStatus`.  
  
```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>Примечания  
 Сведения о состоянии включают поведения, поддерживаемых данными, управления и представление. Сведения о состоянии можно добавить к RGS-файл проекта.  
  
 См. в разделе [IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521) в Windows SDK.  
  
##  <a name="getmoniker"></a>  IOleObjectImpl::GetMoniker  
 Получает моникер элемента управления.  
  
```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает E_NOTIMPL.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleObject::GetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms686576) в Windows SDK.  
  
##  <a name="getuserclassid"></a>  IOleObjectImpl::GetUserClassID  
 Возвращает идентификатор класса элемента управления.  
  
```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleObject::GetUserClassID](http://msdn.microsoft.com/library/windows/desktop/ms682313) в Windows SDK.  
  
##  <a name="getusertype"></a>  IOleObjectImpl::GetUserType  
 Возвращает имя пользовательского типа элемента управления путем вызова `OleRegGetUserType`.  
  
```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```  
  
### <a name="remarks"></a>Примечания  
 Имя пользовательского типа используется для отображения в элементах пользовательских интерфейсов, например меню и диалоговые окна. Можно изменить имя пользовательского типа в RGS-файл проекта.  
  
 См. в разделе [IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643) в Windows SDK.  
  
##  <a name="initfromdata"></a>  IOleObjectImpl::InitFromData  
 Инициализирует элемент управления из выбранных данных.  
  
```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает E_NOTIMPL.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) в Windows SDK.  
  
##  <a name="isuptodate"></a>  IOleObjectImpl::IsUpToDate  
 Проверяет, является ли элемент управления в актуальном состоянии.  
  
```
STDMETHOD(IsUpToDate)(void);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleObject::IsUpToDate](http://msdn.microsoft.com/library/windows/desktop/ms686624) в Windows SDK.  
  
##  <a name="onpostverbdiscardundo"></a>  IOleObjectImpl::OnPostVerbDiscardUndo  
 Вызывается средой [DoVerbDiscardUndo](#doverbdiscardundo) после отбрасывания состояния отмены.  
  
```
HRESULT OnPostVerbDiscardUndo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределения этого метода код, который должен выполняться после отмены состояние удаляется.  
  
##  <a name="onpostverbhide"></a>  IOleObjectImpl::OnPostVerbHide  
 Вызывается средой [DoVerbHide](#doverbhide) после скрытия элемента управления.  
  
```
HRESULT OnPostVerbHide();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределения этого метода код, который должен выполняться после скрытия элемента управления.  
  
##  <a name="onpostverbinplaceactivate"></a>  IOleObjectImpl::OnPostVerbInPlaceActivate  
 Вызывается средой [DoVerbInPlaceActivate](#doverbinplaceactivate) после активации элемента управления на месте.  
  
```
HRESULT OnPostVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределения этого метода код, который должен выполняться после активации элемента управления на месте.  
  
##  <a name="onpostverbopen"></a>  IOleObjectImpl::OnPostVerbOpen  
 Вызывается средой [DoVerbOpen](#doverbopen) после открытия элемента управления для редактирования в отдельном окне.  
  
```
HRESULT OnPostVerbOpen();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределения этого метода код, который должен выполняться после элемента управления был открыт для редактирования в отдельном окне.  
  
##  <a name="onpostverbshow"></a>  IOleObjectImpl::OnPostVerbShow  
 Вызывается средой [DoVerbShow](#doverbshow) после элемента управления видимой.  
  
```
HRESULT OnPostVerbShow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределения этого метода код, который должен выполняться после элемента управления стала видимой.  
  
##  <a name="onpostverbuiactivate"></a>  IOleObjectImpl::OnPostVerbUIActivate  
 Вызывается средой [DoVerbUIActivate](#doverbuiactivate) после активации элемента управления пользовательского интерфейса.  
  
```
HRESULT OnPostVerbUIActivate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод с кодом, которые нужно выполнить после активации элемента управления пользовательского интерфейса.  
  
##  <a name="onpreverbdiscardundo"></a>  IOleObjectImpl::OnPreVerbDiscardUndo  
 Вызывается средой [DoVerbDiscardUndo](#doverbdiscardundo) до отмены состояние удаляется.  
  
```
HRESULT OnPreVerbDiscardUndo();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Чтобы избежать состояния отмены будет отброшен, переопределите этот метод возвращает ошибку HRESULT.  
  
##  <a name="onpreverbhide"></a>  IOleObjectImpl::OnPreVerbHide  
 Вызывается средой [DoVerbHide](#doverbhide) прежде, чем элемент управления скрыт.  
  
```
HRESULT OnPreVerbHide();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Чтобы предотвратить скрытый элемент управления, переопределите этот метод возвращает ошибку HRESULT.  
  
##  <a name="onpreverbinplaceactivate"></a>  IOleObjectImpl::OnPreVerbInPlaceActivate  
 Вызывается средой [DoVerbInPlaceActivate](#doverbinplaceactivate) прежде, чем элемент управления активирован на месте.  
  
```
HRESULT OnPreVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Чтобы предотвратить активацию на месте элемента управления, переопределите этот метод возвращает ошибку HRESULT.  
  
##  <a name="onpreverbopen"></a>  IOleObjectImpl::OnPreVerbOpen  
 Вызывается средой [DoVerbOpen](#doverbopen) прежде, чем элемент управления был открыт для редактирования в отдельном окне.  
  
```
HRESULT OnPreVerbOpen();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Чтобы открыть для редактирования в отдельном окне, элемент управления, переопределите этот метод возвращает ошибку HRESULT.  
  
##  <a name="onpreverbshow"></a>  IOleObjectImpl::OnPreVerbShow  
 Вызывается средой [DoVerbShow](#doverbshow) прежде, чем элемент управления стала видимой.  
  
```
HRESULT OnPreVerbShow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Чтобы элемент управления было нельзя сделать видимым, переопределите этот метод возвращает ошибку HRESULT.  
  
##  <a name="onpreverbuiactivate"></a>  IOleObjectImpl::OnPreVerbUIActivate  
 Вызывается средой [DoVerbUIActivate](#doverbuiactivate) до активации элемента управления пользовательского интерфейса.  
  
```
HRESULT OnPreVerbUIActivate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Чтобы предотвратить активации элемента управления пользовательского интерфейса, переопределите этот метод возвращает ошибку HRESULT.  
  
##  <a name="setclientsite"></a>  IOleObjectImpl::SetClientSite  
 Указывает элементу управления о своему клиентскому сайту в контейнере.  
  
```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```  
  
### <a name="remarks"></a>Примечания  
 Затем метод возвращает значение S_OK.  
  
 См. в разделе [IOleObject::SetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms684013) в Windows SDK.  
  
##  <a name="setcolorscheme"></a>  IOleObjectImpl::SetColorScheme  
 Рекомендует цветовую схему для приложения элемента управления, если таковые имеются.  
  
```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает E_NOTIMPL.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) в Windows SDK.  
  
##  <a name="setextent"></a>  IOleObjectImpl::SetExtent  
 Задает степень область отображения элемента управления.  
  
```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>Примечания  
 В противном случае `SetExtent` сохраняет значение, на которые указывают `psizel` в данные-член класса элемента управления [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent). Это значение задается в единицах HIMETRIC (0,01 мм на единицу).  
  
 Если член данных класса элемента управления [CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) имеет значение TRUE, `SetExtent` также хранит значение, на которые указывают `psizel` в данные-член класса элемента управления [CComControlBase::m_sizeNatural ](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural).  
  
 Если член данных класса элемента управления [CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) имеет значение TRUE, `SetExtent` вызовы `SendOnDataChange` и `SendOnViewChange` для уведомления все приемники зарегистрировано владелец advise размера элемента управления с изменить.  
  
 См. в разделе [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) в Windows SDK.  
  
##  <a name="sethostnames"></a>  IOleObjectImpl::SetHostNames  
 Сообщает родительскому элементу, имена приложения-контейнера и документе-контейнере.  
  
```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) в Windows SDK.  
  
##  <a name="setmoniker"></a>  IOleObjectImpl::SetMoniker  
 Сообщает родительскому элементу Каково его моникер.  
  
```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает E_NOTIMPL.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleObject::SetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679671) в Windows SDK.  
  
##  <a name="unadvise"></a>  IOleObjectImpl::Unadvise  
 Удаляет вспомогательное соединение, хранящихся в классе элемента управления `m_spOleAdviseHolder` элемент данных.  
  
```
STDMETHOD(Unadvise)(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749) в Windows SDK.  
  
##  <a name="update"></a>  IOleObjectImpl::Update  
 Обновляет элемент управления.  
  
```
STDMETHOD(Update)(void);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IOleObject::Update](http://msdn.microsoft.com/library/windows/desktop/ms679699) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Интерфейсы, элементы управления ActiveX](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
