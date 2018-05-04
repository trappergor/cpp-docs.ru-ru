---
title: Класс CComControlBase | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComControlBase
- ATLCTL/ATL::CComControlBase
- ATLCTL/ATL::CComControlBase::AppearanceType
- ATLCTL/ATL::CComControlBase::CComControlBase
- ATLCTL/ATL::CComControlBase::ControlQueryInterface
- ATLCTL/ATL::CComControlBase::DoesVerbActivate
- ATLCTL/ATL::CComControlBase::DoesVerbUIActivate
- ATLCTL/ATL::CComControlBase::DoVerbProperties
- ATLCTL/ATL::CComControlBase::FireViewChange
- ATLCTL/ATL::CComControlBase::GetAmbientAppearance
- ATLCTL/ATL::CComControlBase::GetAmbientAutoClip
- ATLCTL/ATL::CComControlBase::GetAmbientBackColor
- ATLCTL/ATL::CComControlBase::GetAmbientCharSet
- ATLCTL/ATL::CComControlBase::GetAmbientCodePage
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayAsDefault
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayName
- ATLCTL/ATL::CComControlBase::GetAmbientFont
- ATLCTL/ATL::CComControlBase::GetAmbientFontDisp
- ATLCTL/ATL::CComControlBase::GetAmbientForeColor
- ATLCTL/ATL::CComControlBase::GetAmbientLocaleID
- ATLCTL/ATL::CComControlBase::GetAmbientMessageReflect
- ATLCTL/ATL::CComControlBase::GetAmbientPalette
- ATLCTL/ATL::CComControlBase::GetAmbientProperty
- ATLCTL/ATL::CComControlBase::GetAmbientRightToLeft
- ATLCTL/ATL::CComControlBase::GetAmbientScaleUnits
- ATLCTL/ATL::CComControlBase::GetAmbientShowGrabHandles
- ATLCTL/ATL::CComControlBase::GetAmbientShowHatching
- ATLCTL/ATL::CComControlBase::GetAmbientSupportsMnemonics
- ATLCTL/ATL::CComControlBase::GetAmbientTextAlign
- ATLCTL/ATL::CComControlBase::GetAmbientTopToBottom
- ATLCTL/ATL::CComControlBase::GetAmbientUIDead
- ATLCTL/ATL::CComControlBase::GetAmbientUserMode
- ATLCTL/ATL::CComControlBase::GetDirty
- ATLCTL/ATL::CComControlBase::GetZoomInfo
- ATLCTL/ATL::CComControlBase::InPlaceActivate
- ATLCTL/ATL::CComControlBase::InternalGetSite
- ATLCTL/ATL::CComControlBase::OnDraw
- ATLCTL/ATL::CComControlBase::OnDrawAdvanced
- ATLCTL/ATL::CComControlBase::OnKillFocus
- ATLCTL/ATL::CComControlBase::OnMouseActivate
- ATLCTL/ATL::CComControlBase::OnPaint
- ATLCTL/ATL::CComControlBase::OnSetFocus
- ATLCTL/ATL::CComControlBase::PreTranslateAccelerator
- ATLCTL/ATL::CComControlBase::SendOnClose
- ATLCTL/ATL::CComControlBase::SendOnDataChange
- ATLCTL/ATL::CComControlBase::SendOnRename
- ATLCTL/ATL::CComControlBase::SendOnSave
- ATLCTL/ATL::CComControlBase::SendOnViewChange
- ATLCTL/ATL::CComControlBase::SetControlFocus
- ATLCTL/ATL::CComControlBase::SetDirty
- ATLCTL/ATL::CComControlBase::m_bAutoSize
- ATLCTL/ATL::CComControlBase::m_bDrawFromNatural
- ATLCTL/ATL::CComControlBase::m_bDrawGetDataInHimetric
- ATLCTL/ATL::CComControlBase::m_bInPlaceActive
- ATLCTL/ATL::CComControlBase::m_bInPlaceSiteEx
- ATLCTL/ATL::CComControlBase::m_bNegotiatedWnd
- ATLCTL/ATL::CComControlBase::m_bRecomposeOnResize
- ATLCTL/ATL::CComControlBase::m_bRequiresSave
- ATLCTL/ATL::CComControlBase::m_bResizeNatural
- ATLCTL/ATL::CComControlBase::m_bUIActive
- ATLCTL/ATL::CComControlBase::m_bUsingWindowRgn
- ATLCTL/ATL::CComControlBase::m_bWasOnceWindowless
- ATLCTL/ATL::CComControlBase::m_bWindowOnly
- ATLCTL/ATL::CComControlBase::m_bWndLess
- ATLCTL/ATL::CComControlBase::m_hWndCD
- ATLCTL/ATL::CComControlBase::m_nFreezeEvents
- ATLCTL/ATL::CComControlBase::m_rcPos
- ATLCTL/ATL::CComControlBase::m_sizeExtent
- ATLCTL/ATL::CComControlBase::m_sizeNatural
- ATLCTL/ATL::CComControlBase::m_spAdviseSink
- ATLCTL/ATL::CComControlBase::m_spAmbientDispatch
- ATLCTL/ATL::CComControlBase::m_spClientSite
- ATLCTL/ATL::CComControlBase::m_spDataAdviseHolder
- ATLCTL/ATL::CComControlBase::m_spInPlaceSite
- ATLCTL/ATL::CComControlBase::m_spOleAdviseHolder
dev_langs:
- C++
helpviewer_keywords:
- CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b72157db26d4cb7d576e32ca704a32b62b4c2da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ccomcontrolbase-class"></a>Класс CComControlBase
Этот класс предоставляет методы для создания и управления ATL элементов управления.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class ATL_NO_VTABLE CComControlBase
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComControlBase::AppearanceType](#appearancetype)|Переопределите, если ваш `m_nAppearance` стандартное свойство не принадлежит типу `short`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComControlBase::CComControlBase](#ccomcontrolbase)|Конструктор.|  
|[CComControlBase:: ~ CComControlBase](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComControlBase::ControlQueryInterface](#controlqueryinterface)|Извлекает указатель на запрошенный интерфейс.|  
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|Проверяет, что `iVerb` параметр, используемый `IOleObjectImpl::DoVerb` либо активирует элемент управления пользовательского интерфейса ( `iVerb` равняется `OLEIVERB_UIACTIVATE`), определяет действие, выполняемое при двойном щелчке элемента управления ( `iVerb` равняется `OLEIVERB_PRIMARY`), отображает элемент управления ( `iVerb` равняется `OLEIVERB_SHOW`), или активирует элемент управления ( `iVerb` равняется **OLEIVERB_INPLACEACTIVATE**).|  
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|Проверяет, что `iVerb` параметр, используемый `IOleObjectImpl::DoVerb` вызывает элемент управления пользовательского интерфейса для активации и возвращает **TRUE**.|  
|[CComControlBase::DoVerbProperties](#doverbproperties)|Отображение страницы свойств элемента управления.|  
|[CComControlBase::FireViewChange](#fireviewchange)|Вызвать этот метод, чтобы указать контейнер для перерисовки элемента управления, или уведомить зарегистрированных advise приемников, которые представления элемента управления изменилось.|  
|[CComControlBase::GetAmbientAppearance](#getambientappearance)|Извлекает **DISPID_AMBIENT_APPEARANCE**, текущий внешний вид, установка для элемента управления: 0 для неструктурированных и 1 для трехмерной прорисовки.|  
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|Извлекает **DISPID_AMBIENT_AUTOCLIP**, флаг, указывающий, поддерживает ли контейнер автоматического обрезки область отображения элемента управления.|  
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|Извлекает **DISPID_AMBIENT_BACKCOLOR**, цвет фона окружения для всех элементов управления, определенных в качестве контейнера.|  
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|Извлекает **DISPID_AMBIENT_CHARSET**, окружения кодировки для всех элементов управления, определенных в качестве контейнера.|  
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|Извлекает **DISPID_AMBIENT_CODEPAGE**, окружения кодировки для всех элементов управления, определенных в качестве контейнера.|  
|[CComControlBase::GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|Извлекает **DISPID_AMBIENT_DISPLAYASDEFAULT**, флаг, который является **TRUE** Если контейнер пометил управления на этом сайте для кнопки по умолчанию, и таким образом себя с следует нарисовать элемент управления button Толщина рамки.|  
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|Извлекает **DISPID_AMBIENT_DISPLAYNAME**, имя контейнера предоставленные элементу управления.|  
|[CComControlBase::GetAmbientFont](#getambientfont)|Извлекает указатель на контейнер окружения `IFont` интерфейса.|  
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|Извлекает указатель на контейнер окружения **IFontDisp** интерфейс диспетчеризации.|  
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|Извлекает **DISPID_AMBIENT_FORECOLOR**, цвет переднего плана окружения для всех элементов управления, определенных в качестве контейнера.|  
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|Извлекает **DISPID_AMBIENT_LOCALEID**, идентификатор языка, используемые контейнером.|  
|[CComControlBase::GetAmbientMessageReflect](#getambientmessagereflect)|Извлекает **DISPID_AMBIENT_MESSAGEREFLECT**, флаг, указывающий хочет получать сообщения окна, контейнера (например, `WM_DRAWITEM`) как события.|  
|[CComControlBase::GetAmbientPalette](#getambientpalette)|Извлекает **DISPID_AMBIENT_PALETTE**, используемый для доступа к контейнеру `HPALETTE`.|  
|[CComControlBase::GetAmbientProperty](#getambientproperty)|Извлекает свойства контейнера, указанного в `id`.|  
|[CComControlBase::GetAmbientRightToLeft](#getambientrighttoleft)|Извлекает **DISPID_AMBIENT_RIGHTTOLEFT**, направление, в котором будет показано содержимое контейнера.|  
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|Извлекает **DISPID_AMBIENT_SCALEUNITS**, окружения единиц (таких как дюймы или сантиметры) для пометки отображает контейнера.|  
|[CComControlBase::GetAmbientShowGrabHandles](#getambientshowgrabhandles)|Извлекает **DISPID_AMBIENT_SHOWGRABHANDLES**, флаг, указывающий, разрешает ли контейнер элемента управления для отображения маркеры захвата для себя, когда активны.|  
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|Извлекает **DISPID_AMBIENT_SHOWHATCHING**, флаг, указывающий, разрешает ли контейнер элемента управления для отображения самой заштрихованного шаблоном при активном пользовательского интерфейса.|  
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|Извлекает **DISPID_AMBIENT_SUPPORTSMNEMONICS**, флаг, указывающий, поддерживает ли контейнер клавиши.|  
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|Извлекает **DISPID_AMBIENT_TEXTALIGN**, предпочтительно контейнером выравнивание текста: 0 для обычного выравнивания (номера, текста справа налево), 1 для выравнивания по левому краю, выравнивание по центру 2 и 3 для выравнивание по правому краю.|  
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|Извлекает **DISPID_AMBIENT_TOPTOBOTTOM**, направление, в котором будет показано содержимое контейнера.|  
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|Извлекает **DISPID_AMBIENT_UIDEAD**, флаг, указывающий, требуется ли контейнер управления реагировать на действия пользовательского интерфейса.|  
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|Извлекает **DISPID_AMBIENT_USERMODE**, флаг, указывающий, является ли контейнер в режиме выполнения ( **TRUE**) или в режиме конструктора ( **FALSE**).|  
|[CComControlBase::GetDirty](#getdirty)|Возвращает значение члена данных `m_bRequiresSave`.|  
|[CComControlBase::GetZoomInfo](#getzoominfo)|Извлекает x и y значения числитель и знаменатель коэффициент масштаба для активации элемента управления для изменения по месту.|  
|[CComControlBase::InPlaceActivate](#inplaceactivate)|Заставляет элемент управления для перехода из неактивного состояния в команду в состоянии `iVerb` указывает.|  
|[CComControlBase::InternalGetSite](#internalgetsite)|Этот метод используется для запроса узла управления для указателя по указанному адресу.|  
|[CComControlBase::OnDraw](#ondraw)|Переопределите этот метод для рисования элемента управления.|  
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|Значение по умолчанию **OnDrawAdvanced** готовит нормализованный контекст устройства для рисования, а затем вызывает класс элемента управления `OnDraw` метод.|  
|[CComControlBase::OnKillFocus](#onkillfocus)|Проверяет, элемент управления активен на месте и имеет допустимый элемент управления сайта, и сообщает контейнера, что элемент управления потерял фокус.|  
|[CComControlBase::OnMouseActivate](#onmouseactivate)|Проверяет, что пользовательский Интерфейс в пользовательском режиме, а затем активирует элемент управления.|  
|[CComControlBase::OnPaint](#onpaint)|Подготавливает контейнера для рисования, возвращает клиентской области элемента управления, а затем вызывает класс элемента управления `OnDraw` метод.|  
|[CComControlBase::OnSetFocus](#onsetfocus)|Проверяет, элемент управления активен на месте и имеет допустимый элемент управления сайта, и сообщает контейнера элемента управления получило фокус.|  
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|Переопределите этот метод, чтобы предоставить свои собственные сочетания обработчики сочетаний клавиш.|  
|[CComControlBase::SendOnClose](#sendonclose)|Уведомляет все приемники зарегистрирована advise владельца, что элемент управления был закрыт.|  
|[CComControlBase::SendOnDataChange](#sendondatachange)|Уведомляет все приемники зарегистрирована держатель уведомлений об изменении данных элемента управления.|  
|[CComControlBase::SendOnRename](#sendonrename)|Уведомляет все приемники зарегистрирована advise владельца, что элемент управления имеет новый моникер.|  
|[CComControlBase::SendOnSave](#sendonsave)|Уведомляет все приемники зарегистрирована держатель advise, сохраненное в элементе управления.|  
|[CComControlBase::SendOnViewChange](#sendonviewchange)|Уведомляет все зарегистрированные приемники измененных представления элемента управления.|  
|[CComControlBase::SetControlFocus](#setcontrolfocus)|Задает или удаляет фокус клавиатуры в или из элемента управления.|  
|[CComControlBase::SetDirty](#setdirty)|Задает элемент `m_bRequiresSave` значению в `bDirty`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComControlBase::m_bAutoSize](#m_bautosize)|Флаг, указывающий, что элемент управления не может быть любых других размеров.|  
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|Флаг, указывающий, что `IDataObjectImpl::GetData` и `CComControlBase::GetZoomInfo` следует установить размер элемента управления из `m_sizeNatural` , а не из `m_sizeExtent`.|  
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|Флаг, указывающий, что `IDataObjectImpl::GetData` единицах HIMETRIC и пикселей не следует использовать при рисовании.|  
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|Флаг, указывающий, что элемент управления является активным на месте.|  
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|Флаг, указывающий, поддерживает контейнера **IOleInPlaceSiteEx** интерфейс и OCX96 контролировать функции, такие как элементы управления без окон и мерцания.|  
|[CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)|Флаг, указывающий ли элемент управления согласование с контейнером о поддержке функций управления OCX96 (например, мерцания без окон и элементов управления), и является ли элемент управления оконных или без окон.|  
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|Флаг, указывающий, что элементу управления необходимо представлять их представлением, когда контейнер изменяет размер отображения элемента управления.|  
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|Флаг, указывающий, что элемент управления был изменен с момента последнего сохранения.|  
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|Флаг, указывающий, хочет изменить размер его естественное экстент (его зависимым фактический размер) элемента управления при изменении размера отображения элемента управления в контейнер.|  
|[CComControlBase::m_bUIActive](#m_buiactive)|Флаг, указывающий элемент управления пользовательского интерфейса, например меню и панелей инструментов, активна.|  
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|Флаг, указывающий, что элемент управления использует область окна, предоставляемый контейнера.|  
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|Флаг, указывающий элемент управления был без окон, но могут находиться не без окон теперь.|  
|[CComControlBase::m_bWindowOnly](#m_bwindowonly)|Флаг, указывающий, что элемент управления должен быть оконные, даже если контейнер поддерживает элементов управления без окон.|  
|[CComControlBase::m_bWndLess](#m_bwndless)|Флаг, указывающий, что элемент управления без окон.|  
|[CComControlBase::m_hWndCD](#m_hwndcd)|Содержит ссылку на дескриптор окна, связанный с элементом управления.|  
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|Число раз контейнера имеет замороженную события (отказался принять события) без промежуточных Разморозить события (принятия событий).|  
|[CComControlBase::m_rcPos](#m_rcpos)|Позиция в точках управления в координатах контейнера.|  
|[CComControlBase::m_sizeExtent](#m_sizeextent)|Область элемента управления в единицах HIMETRIC (каждая единица равна 0,01 мм) для отображения.|  
|[CComControlBase::m_sizeNatural](#m_sizenatural)|Физический размер элемента управления в единицах HIMETRIC (каждая единица равна 0,01 мм).|  
|[CComControlBase::m_spAdviseSink](#m_spadvisesink)|Прямой указатель вспомогательное соединение в контейнере (контейнера [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)).|  
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|Объект `CComDispatchDriver` объект, который позволяет получить и установить свойства контейнера через `IDispatch` указателя.|  
|[CComControlBase::m_spClientSite](#m_spclientsite)|Указатель на сайте клиента элемента управления в контейнере.|  
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|Предоставляет средства стандартный для хранения вспомогательных соединений между объектами данных и приемников уведомлений.|  
|[CComControlBase::m_spInPlaceSite](#m_spinplacesite)|Указатель на контейнер [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), или [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) указатель на интерфейс.|  
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|Предоставляет стандартную реализацию способ сохранения соединений для рекомендаций.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы для создания и управления ATL элементов управления. [Класс CComControl](../../atl/reference/ccomcontrol-class.md) является производным от `CComControlBase`. При создании элемента управления, стандартный элемент управления или DHTML, используя мастер элементов управления ATL, мастер автоматически будет наследовать класс от `CComControlBase`.  
  
 Дополнительные сведения о создании элемента управления см. в разделе [учебник по ATL](../../atl/active-template-library-atl-tutorial.md). Дополнительные сведения о мастере проекта ATL см. в статье [создается проект ATL](../../atl/reference/creating-an-atl-project.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="appearancetype"></a>  CComControlBase::AppearanceType  
 Переопределите, если ваш **m_nAppearance** стандартное свойство не принадлежит типу **короткие**.  
  
```
typedef short AppearanceType;
```  
  
### <a name="remarks"></a>Примечания  
 Мастер элементов управления ATL добавляет **m_nAppearance** stock свойство типа short. Переопределить `AppearanceType` при использовании другого типа данных.  
  
##  <a name="ccomcontrolbase"></a>  CComControlBase::CComControlBase  
 Конструктор.  
  
```
CComControlBase(HWND& h);
```  
  
### <a name="parameters"></a>Параметры  
 `h`  
 Дескриптор окна, связанный с элементом управления.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует размер элемента управления в единицы HIMETRIC 5080 X 5080 (2 "X 2») и инициализирует `CComControlBase` значения члена данных **NULL** или **FALSE**.  
  
##  <a name="dtor"></a>  CComControlBase:: ~ CComControlBase  
 Деструктор  
  
```
~CComControlBase();
```  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления является оконные, `~CComControlBase` уничтожает его путем вызова [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682).  
  
##  <a name="controlqueryinterface"></a>  CComControlBase::ControlQueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 Идентификатор GUID запрашиваемого интерфейса.  
  
 `ppv`  
 Указатель на указатель на интерфейс, определяемый `iid`, или **NULL** Если интерфейс не найден.  
  
### <a name="remarks"></a>Примечания  
 Обрабатывает интерфейсы только в таблицу сопоставлений COM.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]  
  
##  <a name="doesverbactivate"></a>  CComControlBase::DoesVerbActivate  
 Проверяет, что `iVerb` параметр, используемый `IOleObjectImpl::DoVerb` либо активирует элемент управления пользовательского интерфейса ( `iVerb` равняется `OLEIVERB_UIACTIVATE`), определяет действие, выполняемое при двойном щелчке элемента управления ( `iVerb` равняется `OLEIVERB_PRIMARY`), отображает элемент управления ( `iVerb` равняется `OLEIVERB_SHOW`), или активирует элемент управления ( `iVerb` равняется **OLEIVERB_INPLACEACTIVATE**).  
  
```
BOOL DoesVerbActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>Параметры  
 `iVerb`  
 Значение, указывающее действие, выполняемое по `DoVerb`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** Если `iVerb` равняется `OLEIVERB_UIACTIVATE`, `OLEIVERB_PRIMARY`, `OLEIVERB_SHOW`, или **OLEIVERB_INPLACEACTIVATE**; в противном случае возвращает **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Можно переопределить этот метод, чтобы определить собственные команды активации.  
  
##  <a name="doesverbuiactivate"></a>  CComControlBase::DoesVerbUIActivate  
 Проверяет, что `iVerb` параметр, используемый `IOleObjectImpl::DoVerb` вызывает элемент управления пользовательского интерфейса для активации и возвращает **TRUE**.  
  
```
BOOL DoesVerbUIActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>Параметры  
 `iVerb`  
 Значение, указывающее действие, выполняемое по `DoVerb`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** Если `iVerb` равняется `OLEIVERB_UIACTIVATE`, `OLEIVERB_PRIMARY`, `OLEIVERB_SHOW`, или **OLEIVERB_INPLACEACTIVATE**. В противном случае метод возвращает **FALSE**.  
  
##  <a name="doverbproperties"></a>  CComControlBase::DoVerbProperties  
 Отображение страницы свойств элемента управления.  
  
```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```  
  
### <a name="parameters"></a>Параметры  
 `prcPosRec`  
 Зарезервировано.  
  
 *hwndParent*  
 Дескриптор окна, содержащего элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]  
  
 [!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]  
  
##  <a name="fireviewchange"></a>  CComControlBase::FireViewChange  
 Вызвать этот метод, чтобы указать контейнер для перерисовки элемента управления, или уведомить зарегистрированных advise приемников, которые представления элемента управления изменилось.  
  
```
HRESULT FireViewChange();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления является активным (элемент управления класса данных [CComControlBase::m_bInPlaceActive](#m_binplaceactive) — **TRUE**), уведомляет контейнера требуется перерисовать всего элемента управления. Если элемент управления становится неактивным, уведомляет элемент управления зарегистрированных приемников уведомлений (через элемент управления класса данных [CComControlBase::m_spAdviseSink](#m_spadvisesink)) измененного представления элемента управления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]  
  
##  <a name="getambientappearance"></a>  CComControlBase::GetAmbientAppearance  
 Извлекает **DISPID_AMBIENT_APPEARANCE**, текущий внешний вид, установка для элемента управления: 0 для неструктурированных и 1 для трехмерной прорисовки.  
  
```
HRESULT GetAmbientAppearance(short& nAppearance);
```  
  
### <a name="parameters"></a>Параметры  
 `nAppearance`  
 Свойство **DISPID_AMBIENT_APPEARANCE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]  
  
##  <a name="getambientautoclip"></a>  CComControlBase::GetAmbientAutoClip  
 Извлекает **DISPID_AMBIENT_AUTOCLIP**, флаг, указывающий, поддерживает ли контейнер автоматического обрезки область отображения элемента управления.  
  
```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```  
  
### <a name="parameters"></a>Параметры  
 *bAutoClip*  
 Свойство **DISPID_AMBIENT_AUTOCLIP**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientbackcolor"></a>  CComControlBase::GetAmbientBackColor  
 Извлекает **DISPID_AMBIENT_BACKCOLOR**, цвет фона окружения для всех элементов управления, определенных в качестве контейнера.  
  
```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```  
  
### <a name="parameters"></a>Параметры  
 *Цвет фона*  
 Свойство **DISPID_AMBIENT_BACKCOLOR**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientcharset"></a>  CComControlBase::GetAmbientCharSet  
 Извлекает **DISPID_AMBIENT_CHARSET**, окружения кодировки для всех элементов управления, определенных в качестве контейнера.  
  
```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```  
  
### <a name="parameters"></a>Параметры  
 *bstrCharSet*  
 Свойство **DISPID_AMBIENT_CHARSET**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
##  <a name="getambientcodepage"></a>  CComControlBase::GetAmbientCodePage  
 Извлекает **DISPID_AMBIENT_CODEPAGE**, окружения кодовую страницу для всех элементов управления, определенных в качестве контейнера.  
  
```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```  
  
### <a name="parameters"></a>Параметры  
 *ulCodePage*  
 Свойство **DISPID_AMBIENT_CODEPAGE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
##  <a name="getambientdisplayasdefault"></a>  CComControlBase::GetAmbientDisplayAsDefault  
 Извлекает **DISPID_AMBIENT_DISPLAYASDEFAULT**, флаг, который является **TRUE** Если контейнер пометил управления на этом сайте для кнопки по умолчанию, и таким образом себя с следует нарисовать элемент управления button Толщина рамки.  
  
```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```  
  
### <a name="parameters"></a>Параметры  
 `bDisplayAsDefault`  
 Свойство **DISPID_AMBIENT_DISPLAYASDEFAULT**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientdisplayname"></a>  CComControlBase::GetAmbientDisplayName  
 Извлекает **DISPID_AMBIENT_DISPLAYNAME**, имя контейнера предоставленные элементу управления.  
  
```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```  
  
### <a name="parameters"></a>Параметры  
 *bstrDisplayName*  
 Свойство **DISPID_AMBIENT_DISPLAYNAME**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientfont"></a>  CComControlBase::GetAmbientFont  
 Извлекает указатель на контейнер окружения `IFont` интерфейса.  
  
```
HRESULT GetAmbientFont(IFont** ppFont);
```  
  
### <a name="parameters"></a>Параметры  
 `ppFont`  
 Указатель на контейнер окружения [IFont](http://msdn.microsoft.com/library/windows/desktop/ms680673) интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если свойство **NULL**, указатель имеет **NULL**. Если указатель не имеет **NULL**, вызывающий объект должен освободить указатель.  
  
##  <a name="getambientfontdisp"></a>  CComControlBase::GetAmbientFontDisp  
 Извлекает указатель на контейнер окружения **IFontDisp** интерфейс диспетчеризации.  
  
```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```  
  
### <a name="parameters"></a>Параметры  
 `ppFont`  
 Указатель на контейнер окружения [IFontDisp](http://msdn.microsoft.com/library/windows/desktop/ms692695) интерфейс диспетчеризации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Если свойство **NULL**, указатель имеет **NULL**. Если указатель не имеет **NULL**, вызывающий объект должен освободить указатель.  
  
##  <a name="getambientforecolor"></a>  CComControlBase::GetAmbientForeColor  
 Извлекает **DISPID_AMBIENT_FORECOLOR**, цвет переднего плана окружения для всех элементов управления, определенных в качестве контейнера.  
  
```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```  
  
### <a name="parameters"></a>Параметры  
 *Цвет переднего плана*  
 Свойство **DISPID_AMBIENT_FORECOLOR**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientlocaleid"></a>  CComControlBase::GetAmbientLocaleID  
 Извлекает **DISPID_AMBIENT_LOCALEID**, идентификатор языка, используемые контейнером.  
  
```
HRESULT GetAmbientLocaleID(LCID& lcid);
```  
  
### <a name="parameters"></a>Параметры  
 `lcid`  
 Свойство **DISPID_AMBIENT_LOCALEID**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления можно использовать этот идентификатор адаптировать его пользовательский интерфейс для различных языков.  
  
##  <a name="getambientmessagereflect"></a>  CComControlBase::GetAmbientMessageReflect  
 Извлекает **DISPID_AMBIENT_MESSAGEREFLECT**, флаг, указывающий хочет получать сообщения окна, контейнера (например, `WM_DRAWITEM`) как события.  
  
```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```  
  
### <a name="parameters"></a>Параметры  
 `bMessageReflect`  
 Свойство **DISPID_AMBIENT_MESSAGEREFLECT**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientpalette"></a>  CComControlBase::GetAmbientPalette  
 Извлекает **DISPID_AMBIENT_PALETTE**, используемый для доступа к контейнеру `HPALETTE`.  
  
```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```  
  
### <a name="parameters"></a>Параметры  
 `hPalette`  
 Свойство **DISPID_AMBIENT_PALETTE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientproperty"></a>  CComControlBase::GetAmbientProperty  
 Извлекает свойства контейнера, указанного в `dispid`.  
  
```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор свойства контейнера должны быть получены.  
  
 `var`  
 Переменная для получения свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Предоставляет набор вспомогательных функций для получения определенных свойств, например, ATL [CComControlBase::GetAmbientBackColor](#getambientbackcolor). Если имеется не подходящий метод, используйте `GetAmbientProperty`.  
  
##  <a name="getambientrighttoleft"></a>  CComControlBase::GetAmbientRightToLeft  
 Извлекает **DISPID_AMBIENT_RIGHTTOLEFT**, направление, в котором будет показано содержимое контейнера.  
  
```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```  
  
### <a name="parameters"></a>Параметры  
 *bRightToLeft*  
 Свойство **DISPID_AMBIENT_RIGHTTOLEFT**. Значение **TRUE** Если отобразить содержимое справа налево, **FALSE** Если отображается слева направо.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
##  <a name="getambientscaleunits"></a>  CComControlBase::GetAmbientScaleUnits  
 Извлекает **DISPID_AMBIENT_SCALEUNITS**, окружения единиц (таких как дюймы или сантиметры) для пометки отображает контейнера.  
  
```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```  
  
### <a name="parameters"></a>Параметры  
 *bstrScaleUnits*  
 Свойство **DISPID_AMBIENT_SCALEUNITS**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientshowgrabhandles"></a>  CComControlBase::GetAmbientShowGrabHandles  
 Извлекает **DISPID_AMBIENT_SHOWGRABHANDLES**, флаг, указывающий, разрешает ли контейнер элемента управления для отображения маркеры захвата для себя, когда активны.  
  
```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```  
  
### <a name="parameters"></a>Параметры  
 *bShowGrabHandles*  
 Свойство **DISPID_AMBIENT_SHOWGRABHANDLES**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientshowhatching"></a>  CComControlBase::GetAmbientShowHatching  
 Извлекает **DISPID_AMBIENT_SHOWHATCHING**, флаг, указывающий, разрешает ли контейнер элемента управления для отображения самой заштрихованного шаблоном при активном пользовательский интерфейс элемента управления.  
  
```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```  
  
### <a name="parameters"></a>Параметры  
 *bShowHatching*  
 Свойство **DISPID_AMBIENT_SHOWHATCHING**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientsupportsmnemonics"></a>  CComControlBase::GetAmbientSupportsMnemonics  
 Извлекает **DISPID_AMBIENT_SUPPORTSMNEMONICS**, флаг, указывающий, поддерживает ли контейнер клавиши.  
  
```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```  
  
### <a name="parameters"></a>Параметры  
 *bSupportsMnemonics*  
 Свойство **DISPID_AMBIENT_SUPPORTSMNEMONICS**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambienttextalign"></a>  CComControlBase::GetAmbientTextAlign  
 Извлекает **DISPID_AMBIENT_TEXTALIGN**, предпочтительно контейнером выравнивание текста: 0 для обычного выравнивания (номера, текста справа налево), 1 для выравнивания по левому краю, выравнивание по центру 2 и 3 для выравнивание по правому краю.  
  
```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```  
  
### <a name="parameters"></a>Параметры  
 *nTextAlign*  
 Свойство **DISPID_AMBIENT_TEXTALIGN**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambienttoptobottom"></a>  CComControlBase::GetAmbientTopToBottom  
 Извлекает **DISPID_AMBIENT_TOPTOBOTTOM**, направление, в котором будет показано содержимое контейнера.  
  
```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```  
  
### <a name="parameters"></a>Параметры  
 *bTopToBottom*  
 Свойство **DISPID_AMBIENT_TOPTOBOTTOM**. Значение **TRUE** Если текст отображается сверху вниз, **FALSE** если он отображается снизу вверх.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
##  <a name="getambientuidead"></a>  CComControlBase::GetAmbientUIDead  
 Извлекает **DISPID_AMBIENT_UIDEAD**, флаг, указывающий, требуется ли контейнер управления реагировать на действия пользовательского интерфейса.  
  
```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```  
  
### <a name="parameters"></a>Параметры  
 *bUIDead*  
 Свойство **DISPID_AMBIENT_UIDEAD**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если **TRUE**, элемент управления не должен отвечать. Этот флаг применяется независимо от **DISPID_AMBIENT_USERMODE** флаг. В разделе [CComControlBase::GetAmbientUserMode](#getambientusermode).  
  
##  <a name="getambientusermode"></a>  CComControlBase::GetAmbientUserMode  
 Извлекает **DISPID_AMBIENT_USERMODE**, флаг, указывающий, является ли контейнер в режиме выполнения ( **TRUE**) или в режиме конструктора ( **FALSE**).  
  
```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```  
  
### <a name="parameters"></a>Параметры  
 `bUserMode`  
 Свойство **DISPID_AMBIENT_USERMODE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getdirty"></a>  CComControlBase::GetDirty  
 Возвращает значение члена данных `m_bRequiresSave`.  
  
```
BOOL GetDirty();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение члена данных [m_bRequiresSave](#m_brequiressave).  
  
### <a name="remarks"></a>Примечания  
 Это значение задается с помощью [CComControlBase::SetDirty](#setdirty).  
  
##  <a name="getzoominfo"></a>  CComControlBase::GetZoomInfo  
 Извлекает x и y значения числитель и знаменатель коэффициент масштаба для активации элемента управления для изменения по месту.  
  
```
void GetZoomInfo(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Параметры  
 `di`  
 Структура, которая будет содержать числитель и знаменатель коэффициента масштабирования. Дополнительные сведения см. в разделе [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md).  
  
### <a name="remarks"></a>Примечания  
 Масштаб представляет долю размеру элемента управления в его текущем степени.  
  
##  <a name="inplaceactivate"></a>  CComControlBase::InPlaceActivate  
 Заставляет элемент управления для перехода из неактивного состояния в команду в состоянии `iVerb` указывает.  
  
```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `iVerb`  
 Значение, указывающее действие, выполняемое по [IOleObjectImpl::DoVerb](../../atl/reference/ioleobjectimpl-class.md#doverb).  
  
 *prcPosRect*  
 Указатель на позицию элемента управления на месте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Перед активации этот метод проверяет, что элемент управления сайта клиента, проверяет, какая часть элемента управления является видимым и возвращает расположение элемента управления в родительское окно. После активации элемента управления, этот метод активирует элемент управления пользовательского интерфейса и указывает контейнеру, чтобы сделать элемент управления видимым.  
  
 Этот метод также возвращает `IOleInPlaceSite`, **IOleInPlaceSiteEx**, или **IOleInPlaceSiteWindowless** указатель интерфейса для элемента управления и сохраняет его в элемент данных класс элемента управления [CComControlBase::m_spInPlaceSite](#m_spinplacesite). Данные-члены класса элемента управления [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex), [CComControlBase::m_bWndLess](#m_bwndless), [CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)и [ CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) задать значение true, соответствующим образом.  
  
##  <a name="internalgetsite"></a>  CComControlBase::InternalGetSite  
 Этот метод используется для запроса узла управления для указателя по указанному адресу.  
  
```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```  
  
### <a name="parameters"></a>Параметры  
 `riid`  
 Идентификатор IID указатель интерфейса, должны быть возвращены в `ppUnkSite`.  
  
 `ppUnkSite`  
 Адрес переменной указателя, получающей указатель интерфейса, запрашиваемый в `riid`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Если сайт поддерживает интерфейс, запрошенный в `riid`, указатель, возвращенный с помощью параметра `ppUnkSite`. В противном случае `ppUnkSite` имеет значение NULL.  
  
##  <a name="m_bautosize"></a>  CComControlBase::m_bAutoSize  
 Флаг, указывающий, что элемент управления не может быть любых других размеров.  
  
```
unsigned m_bAutoSize:1;
```  
  
### <a name="remarks"></a>Примечания  
 Этот флаг установлен `IOleObjectImpl::SetExtent` и, если **TRUE**, функция возвращает **E_FAIL**.  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 При добавлении **Авторазмер** параметр [свойства набора](../../atl/reference/stock-properties-atl-control-wizard.md) вкладке Мастер элементов управления ATL, мастер автоматически создает этот элемент данных в классе элемента управления, создает put и методов для свойства get и поддерживает [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) автоматическое уведомление контейнера, при изменении значения свойства.  
  
##  <a name="m_bdrawfromnatural"></a>  CComControlBase::m_bDrawFromNatural  
 Флаг, указывающий, что `IDataObjectImpl::GetData` и `CComControlBase::GetZoomInfo` следует установить размер элемента управления из `m_sizeNatural` , а не из `m_sizeExtent`.  
  
```
unsigned m_bDrawFromNatural:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_bdrawgetdatainhimetric"></a>  CComControlBase::m_bDrawGetDataInHimetric  
 Флаг, указывающий, что `IDataObjectImpl::GetData` единицах HIMETRIC и пикселей не следует использовать при рисовании.  
  
```
unsigned m_bDrawGetDataInHimetric:1;
```  
  
### <a name="remarks"></a>Примечания  
 Каждое логическое устройство HIMETRIC равна 0,01 мм.  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_binplaceactive"></a>  CComControlBase::m_bInPlaceActive  
 Флаг, указывающий, что элемент управления является активным на месте.  
  
```
unsigned m_bInPlaceActive:1;
```  
  
### <a name="remarks"></a>Примечания  
 Это означает, что элемент управления является видимым и его, если таковые имеются, отображается окно, но его меню и панелей инструментов могут быть неактивны. `m_bUIActive` Указывает флаг элемента управления пользовательского интерфейса, таких как меню, уже активен.  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_binplacesiteex"></a>  CComControlBase::m_bInPlaceSiteEx  
 Флаг, указывающий, поддерживает контейнера **IOleInPlaceSiteEx** интерфейс и OCX96 контролировать функции, такие как элементы управления без окон и мерцания.  
  
```
unsigned m_bInPlaceSiteEx:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Элемент данных `m_spInPlaceSite` указывает [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), или [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) интерфейс, в зависимости от значения `m_bWndLess` и `m_bInPlaceSiteEx` флаги. (Элемент данных `m_bNegotiatedWnd` должно быть **TRUE** для `m_spInPlaceSite` указатель недействителен.)  
  
 Если `m_bWndLess` — **FALSE** и `m_bInPlaceSiteEx` — **TRUE**, `m_spInPlaceSite` — **IOleInPlaceSiteEx** указатель на интерфейс. В разделе [m_spInPlaceSite](#m_spinplacesite) для таблицы, показывающая связь между членами этих трех данных.  
  
##  <a name="m_bnegotiatedwnd"></a>  CComControlBase::m_bNegotiatedWnd  
 Флаг, указывающий ли элемент управления согласование с контейнером о поддержке функций управления OCX96 (например, мерцания без окон и элементов управления), и является ли элемент управления оконных или без окон.  
  
```
unsigned m_bNegotiatedWnd:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 `m_bNegotiatedWnd` Флаг должен иметь **TRUE** для `m_spInPlaceSite` указатель недействителен.  
  
##  <a name="m_brecomposeonresize"></a>  CComControlBase::m_bRecomposeOnResize  
 Флаг, указывающий, что элементу управления необходимо представлять их представлением, когда контейнер изменяет размер отображения элемента управления.  
  
```
unsigned m_bRecomposeOnResize:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Этот флаг установлен [IOleObjectImpl::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent) и, если **TRUE**, `SetExtent` уведомляет контейнера изменения представления. Если этот флаг установлен, **OLEMISC_RECOMPOSEONRESIZE** бит в [OLEMISC, ПОЗВОЛЯЯ](http://msdn.microsoft.com/library/windows/desktop/ms678497) перечисления также должен быть установлен.  
  
##  <a name="m_brequiressave"></a>  CComControlBase::m_bRequiresSave  
 Флаг, указывающий, что элемент управления был изменен с момента последнего сохранения.  
  
```
unsigned m_bRequiresSave:1;
```  
  
### <a name="remarks"></a>Примечания  
 Значение `m_bRequiresSave` можно задать с помощью [CComControlBase::SetDirty](#setdirty) и полученный с [CComControlBase::GetDirty](#getdirty).  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_bresizenatural"></a>  CComControlBase::m_bResizeNatural  
 Флаг, указывающий, хочет изменить размер его естественное экстент (его зависимым фактический размер) элемента управления при изменении размера отображения элемента управления в контейнер.  
  
```
unsigned m_bResizeNatural:1;
```  
  
### <a name="remarks"></a>Примечания  
 Этот флаг установлен `IOleObjectImpl::SetExtent` и, если **TRUE**, размер передаваемого `SetExtent` назначается `m_sizeNatural`.  
  
 Размер передаваемого `SetExtent` всегда назначается `m_sizeExtent`, независимо от значения `m_bResizeNatural`.  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_buiactive"></a>  CComControlBase::m_bUIActive  
 Флаг, указывающий элемент управления пользовательского интерфейса, например меню и панелей инструментов, активна.  
  
```
unsigned m_bUIActive:1;
```  
  
### <a name="remarks"></a>Примечания  
 `m_bInPlaceActive` Флаг указывает, что элемент управления является активной, но не, его пользовательский интерфейс активен.  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_busingwindowrgn"></a>  CComControlBase::m_bUsingWindowRgn  
 Флаг, указывающий, что элемент управления использует область окна, предоставляемый контейнера.  
  
```
unsigned m_bUsingWindowRgn:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_bwasoncewindowless"></a>  CComControlBase::m_bWasOnceWindowless  
 Флаг, указывающий элемент управления был без окон, но могут находиться не без окон теперь.  
  
```
unsigned m_bWasOnceWindowless:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_bwindowonly"></a>  CComControlBase::m_bWindowOnly  
 Флаг, указывающий, что элемент управления должен быть оконные, даже если контейнер поддерживает элементов управления без окон.  
  
```
unsigned m_bWindowOnly:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_bwndless"></a>  CComControlBase::m_bWndLess  
 Флаг, указывающий, что элемент управления без окон.  
  
```
unsigned m_bWndLess:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Элемент данных `m_spInPlaceSite` указывает [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), или [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) интерфейс, в зависимости от значения `m_bWndLess` и [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex) флаги. (Элемент данных [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) должно быть **TRUE** для [CComControlBase::m_spInPlaceSite](#m_spinplacesite) указатель недействителен.)  
  
 Если `m_bWndLess` — **TRUE**, `m_spInPlaceSite` — **IOleInPlaceSiteWindowless** указатель на интерфейс. В разделе [CComControlBase::m_spInPlaceSite](#m_spinplacesite) для таблицы, показывающая завершения связь между этими элементами данных.  
  
##  <a name="m_hwndcd"></a>  CComControlBase::m_hWndCD  
 Содержит ссылку на дескриптор окна, связанный с элементом управления.  
  
```
HWND& m_hWndCD;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_nfreezeevents"></a>  CComControlBase::m_nFreezeEvents  
 Число раз контейнера имеет замороженную события (отказался принять события) без промежуточных Разморозить события (принятия событий).  
  
```
short m_nFreezeEvents;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_rcpos"></a>  CComControlBase::m_rcPos  
 Позиция в точках управления в координатах контейнера.  
  
```
RECT m_rcPos;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_sizeextent"></a>  CComControlBase::m_sizeExtent  
 Область элемента управления в единицах HIMETRIC (каждая единица равна 0,01 мм) для отображения.  
  
```
SIZE m_sizeExtent;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Этот размер масштабируется по отображения. Физический размер элемента управления указывается в `m_sizeNatural` элемент данных и является фиксированным.  
  
 Размер можно преобразовать в точках с глобальной функции [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).  
  
##  <a name="m_sizenatural"></a>  CComControlBase::m_sizeNatural  
 Физический размер элемента управления в единицах HIMETRIC (каждая единица равна 0,01 мм).  
  
```
SIZE m_sizeNatural;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Этот размер фиксирован при размер в `m_sizeExtent` умноженного на экране.  
  
 Размер можно преобразовать в точках с глобальной функции [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).  
  
##  <a name="m_spadvisesink"></a>  CComControlBase::m_spAdviseSink  
 Прямой указатель вспомогательное соединение в контейнере (контейнера [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)).  
  
```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```     
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_spambientdispatch"></a>  CComControlBase::m_spAmbientDispatch  
 Объект `CComDispatchDriver` объект, который позволяет получить и задать свойства объекта через `IDispatch` указателя.  
  
```
CComDispatchDriver m_spAmbientDispatch;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_spclientsite"></a>  CComControlBase::m_spClientSite  
 Указатель на сайте клиента элемента управления в контейнере.  
  
```
CComPtr<IOleClientSite>
    m_spClientSite;
```     
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_spdataadviseholder"></a>  CComControlBase::m_spDataAdviseHolder  
 Предоставляет средства стандартный для хранения вспомогательных соединений между объектами данных и приемников уведомлений.  
  
```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```     
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Объект данных — это элемент управления, который можно перенести данные и типов, реализующих [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421), методы которого укажите Средний формат и передачи данных.  
  
 Интерфейс `m_spDataAdviseHolder` реализует [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) и [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) методы для установки и удаления вспомогательных соединений для контейнера. Контейнер элемента управления должен реализовывать приемника уведомлений с помощью поддержки [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) интерфейса.  
  
##  <a name="m_spinplacesite"></a>  CComControlBase::m_spInPlaceSite  
 Указатель на контейнер [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), или [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) указатель на интерфейс.  
  
```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```     
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 `m_spInPlaceSite` Указатель является действительным только тогда, когда [m_bNegotiatedWnd](#m_bnegotiatedwnd) установлен флаг **TRUE**.  
  
 В следующей таблице показаны как `m_spInPlaceSite` зависит от типа указателя [m_bWndLess](#m_bwndless) и [m_bInPlaceSiteEx](#m_binplacesiteex) флаги элемента данных:  
  
|m_spInPlaceSite тип|m_bWndLess значение|m_bInPlaceSiteEx значение|  
|---------------------------|-----------------------|-----------------------------|  
|**IOleInPlaceSiteWindowless**|**ЗНАЧЕНИЕ TRUE**|**Значение TRUE,** или **FALSE**|  
|**IOleInPlaceSiteEx**|**ЗНАЧЕНИЕ FALSE**|**ЗНАЧЕНИЕ TRUE**|  
|`IOleInPlaceSite`|**ЗНАЧЕНИЕ FALSE**|**ЗНАЧЕНИЕ FALSE**|  
  
##  <a name="m_spoleadviseholder"></a>  CComControlBase::m_spOleAdviseHolder  
 Предоставляет стандартную реализацию способ сохранения соединений для рекомендаций.  
  
```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```     
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Для использования этого элемента данных в пределах класса элемента управления, необходимо объявить его как элемента данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Интерфейс `m_spOleAdviseHolder` реализует [IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573) и [IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749) методы для установки и удаления вспомогательных соединений для контейнера. Контейнер элемента управления должен реализовывать приемника уведомлений с помощью поддержки [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) интерфейса.  
  
##  <a name="ondraw"></a>  CComControlBase::OnDraw  
 Переопределите этот метод для рисования элемента управления.  
  
```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Параметры  
 `di`  
 Ссылку на [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) структуру, содержащую графическую информацию, например аспекта draw, границы элемента управления и ли Рисование оптимизирован, или нет.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию `OnDraw` удаляет или восстанавливает контекст устройства или не выполняет никаких действий, в зависимости от набора флагов в [CComControlBase::OnDrawAdvanced](#ondrawadvanced).  
  
 `OnDraw` Автоматически добавляется метод для класса элемента управления при создании элемента управления с помощью мастера элементов управления ATL. По умолчанию мастер `OnDraw` Рисование прямоугольника с меткой «ATL 8.0».  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CComControlBase::GetAmbientAppearance](#getambientappearance).  
  
##  <a name="ondrawadvanced"></a>  CComControlBase::OnDrawAdvanced  
 Значение по умолчанию `OnDrawAdvanced` готовит нормализованный контекст устройства для рисования, а затем вызывает класс элемента управления `OnDraw` метод.  
  
```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Параметры  
 `di`  
 Ссылку на [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) структуру, содержащую графическую информацию, например аспекта draw, границы элемента управления и ли Рисование оптимизирован, или нет.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если вы хотите принять контекст устройства контейнером без нормализации.  
  
 В разделе [CComControlBase::OnDraw](#ondraw) для получения дополнительных сведений.  
  
##  <a name="onkillfocus"></a>  CComControlBase::OnKillFocus  
 Проверяет, элемент управления активен на месте и имеет допустимый элемент управления сайта, и сообщает контейнера, что элемент управления потерял фокус.  
  
```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Параметры  
 `nMsg`  
 Зарезервировано.  
  
 `wParam`  
 Зарезервировано.  
  
 `lParam`  
 Зарезервировано.  
  
 `bHandled`  
 Флаг, указывающий, было ли сообщение окна обработано успешно. Значение по умолчанию — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение 1.  
  
##  <a name="onmouseactivate"></a>  CComControlBase::OnMouseActivate  
 Проверяет, что пользовательский Интерфейс в пользовательском режиме, а затем активирует элемент управления.  
  
```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Параметры  
 `nMsg`  
 Зарезервировано.  
  
 `wParam`  
 Зарезервировано.  
  
 `lParam`  
 Зарезервировано.  
  
 `bHandled`  
 Флаг, указывающий, было ли сообщение окна обработано успешно. Значение по умолчанию — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение 1.  
  
##  <a name="onpaint"></a>  CComControlBase::OnPaint  
 Подготавливает контейнера для рисования, возвращает клиентской области элемента управления, а затем вызывает класс элемента управления `OnDrawAdvanced` метод.  
  
```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```  
  
### <a name="parameters"></a>Параметры  
 `nMsg`  
 Зарезервировано.  
  
 `wParam`  
 HDC существующий.  
  
 `lParam`  
 Зарезервировано.  
  
 `lResult`  
 Зарезервировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает ноль.  
  
### <a name="remarks"></a>Примечания  
 Если `wParam` не равно NULL, `OnPaint` предполагается содержит допустимый HDC и использует его вместо [CComControlBase::m_hWndCD](#m_hwndcd).  
  
##  <a name="onsetfocus"></a>  CComControlBase::OnSetFocus  
 Проверяет, элемент управления активен на месте и имеет допустимый элемент управления сайта, и сообщает контейнера элемента управления получило фокус.  
  
```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Параметры  
 `nMsg`  
 Зарезервировано.  
  
 `wParam`  
 Зарезервировано.  
  
 `lParam`  
 Зарезервировано.  
  
 `bHandled`  
 Флаг, указывающий, было ли сообщение окна обработано успешно. Значение по умолчанию — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение 1.  
  
### <a name="remarks"></a>Примечания  
 Отправляет уведомление в контейнер, что элемент управления получил фокус.  
  
##  <a name="pretranslateaccelerator"></a>  CComControlBase::PreTranslateAccelerator  
 Переопределите этот метод, чтобы предоставить свои собственные сочетания обработчики сочетаний клавиш.  
  
```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```  
  
### <a name="parameters"></a>Параметры  
 `pMsg`  
 Зарезервировано.  
  
 *hRet*  
 Зарезервировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 По умолчанию возвращает **FALSE**.  
  
##  <a name="sendonclose"></a>  CComControlBase::SendOnClose  
 Уведомляет все приемники зарегистрирована advise владельца, что элемент управления был закрыт.  
  
```
HRESULT SendOnClose();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Отправляет уведомление, что элемент управления закрыл его приемники.  
  
##  <a name="sendondatachange"></a>  CComControlBase::SendOnDataChange  
 Уведомляет все приемники зарегистрирована держатель уведомлений об изменении данных элемента управления.  
  
```
HRESULT SendOnDataChange(DWORD advf = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *ADVF*  
 Флаги, указывающие способ вызова [IAdviseSink::OnDataChange](http://msdn.microsoft.com/library/windows/desktop/ms687283) выполняется. Значения в диапазоне от [ADVF](http://msdn.microsoft.com/library/windows/desktop/ms693742) перечисления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
##  <a name="sendonrename"></a>  CComControlBase::SendOnRename  
 Уведомляет все приемники зарегистрирована advise владельца, что элемент управления имеет новый моникер.  
  
```
HRESULT SendOnRename(IMoniker* pmk);
```  
  
### <a name="parameters"></a>Параметры  
 *PMK*  
 Указатель на новый специальное имя элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Отправляет уведомление об изменении моникера для элемента управления.  
  
##  <a name="sendonsave"></a>  CComControlBase::SendOnSave  
 Уведомляет все приемники зарегистрирована держатель advise, сохраненное в элементе управления.  
  
```
HRESULT SendOnSave();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Отправляет уведомление элемента управления просто сохранил свои данные.  
  
##  <a name="sendonviewchange"></a>  CComControlBase::SendOnViewChange  
 Уведомляет все зарегистрированные приемники измененных представления элемента управления.  
  
```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```  
  
### <a name="parameters"></a>Параметры  
 `dwAspect`  
 Аспект или представление элемента управления.  
  
 *Индекс*  
 Часть представления, которая была изменена. Допустимо только значение -1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 `SendOnViewChange` вызовы [IAdviseSink::OnViewChange](http://msdn.microsoft.com/library/windows/desktop/ms694337). Только значение *индекс* в настоящее время поддерживается-1, показывает, что все представление процента.  
  
##  <a name="setcontrolfocus"></a>  CComControlBase::SetControlFocus  
 Задает или удаляет фокус клавиатуры в или из элемента управления.  
  
```
BOOL SetControlFocus(BOOL bGrab);
```  
  
### <a name="parameters"></a>Параметры  
 *bGrab*  
 Если **TRUE**, устанавливает фокус клавиатуры вызывающему элементу управления. Если **FALSE**, удаляет фокус из вызывающего элемента управления, предоставляемые в фокусе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** Если успешно, элемент управления получает фокус; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Для элемента Оконные функции Windows API [SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms646312) вызывается. Для элемента управления без окна [IOleInPlaceSiteWindowless::SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms679745) вызывается. Посредством этого вызова элемента управления без окна получает фокус клавиатуры и может отвечать на сообщения окна.  
  
##  <a name="setdirty"></a>  CComControlBase::SetDirty  
 Задает элемент `m_bRequiresSave` значению в `bDirty`.  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>Параметры  
 `bDirty`  
 Значение элемента данных [CComControlBase::m_bRequiresSave](#m_brequiressave).  
  
### <a name="remarks"></a>Примечания  
 **SetDirty(TRUE)** должен вызываться для флага, что элемент управления изменилось с момента последнего сохранения. Значение `m_bRequiresSave` извлекается с [CComControlBase::GetDirty](#getdirty).  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
