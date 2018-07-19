---
title: Класс CComControlBase | Документация Майкрософт
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
ms.openlocfilehash: ace66d9528534b382eda02160372bfc56aced0f5
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882999"
---
# <a name="ccomcontrolbase-class"></a>Класс CComControlBase
Этот класс предоставляет методы для создания и управления элементами управления ATL.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class ATL_NO_VTABLE CComControlBase
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComControlBase::AppearanceType](#appearancetype)|Переопределить, если ваш `m_nAppearance` не стандартное свойство типа **короткие**.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComControlBase::CComControlBase](#ccomcontrolbase)|Конструктор.|  
|[CComControlBase:: ~ CComControlBase](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComControlBase::ControlQueryInterface](#controlqueryinterface)|Извлекает указатель на запрошенный интерфейс.|  
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|Проверяет, что *iVerb* параметра, используемого методом `IOleObjectImpl::DoVerb` либо активирует элемента управления пользовательского интерфейса (*iVerb* равно OLEIVERB_UIACTIVATE), определяет действие, выполняемое при двойном щелчке элемент управления (*iVerb* равно OLEIVERB_PRIMARY), отображает элемент управления (*iVerb* равно OLEIVERB_SHOW), или активирует элемент управления (*iVerb* равно OLEIVERB _INPLACEACTIVATE).|  
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|Проверяет, что *iVerb* параметра, используемого методом `IOleObjectImpl::DoVerb` заставляет элемент управления пользовательского интерфейса для активации и возвращает значение TRUE.|  
|[CComControlBase::DoVerbProperties](#doverbproperties)|Отображает страницы свойств элемента управления.|  
|[CComControlBase::FireViewChange](#fireviewchange)|Вызовите этот метод, чтобы указать контейнер для перерисовки элемента управления или уведомлять зарегистрированных advise, приемники представление элемента управления изменилось.|  
|[CComControlBase::GetAmbientAppearance](#getambientappearance)|Извлекает DISPID_AMBIENT_APPEARANCE, текущий внешний вид, установка для элемента управления: 0 для неструктурированных и 1 для 3D.|  
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|Извлекает DISPID_AMBIENT_AUTOCLIP, флаг, указывающий, поддерживает ли контейнер автоматического обрезки отображаемой области элемента управления.|  
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|Извлекает DISPID_AMBIENT_BACKCOLOR, цвет фона окружения для всех элементов управления, определенные с помощью контейнера.|  
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|Извлекает DISPID_AMBIENT_CHARSET окружения кодировки для всех элементов управления, определенные с помощью контейнера.|  
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|Извлекает DISPID_AMBIENT_CODEPAGE окружения кодировки для всех элементов управления, определенные с помощью контейнера.|  
|[CComControlBase::GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|Извлекает DISPID_AMBIENT_DISPLAYASDEFAULT, флаг, который имеет значение TRUE, если контейнер помечен элемент управления на этом сайте, как кнопка по умолчанию, и таким образом управления "Кнопка" следует рисовать сам полужирным фреймом.|  
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|Извлекает DISPID_AMBIENT_DISPLAYNAME, имя контейнера предоставил к элементу управления.|  
|[CComControlBase::GetAmbientFont](#getambientfont)|Извлекает указатель на контейнер окружения `IFont` интерфейс.|  
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|Извлекает указатель на контейнер окружения `IFontDisp` интерфейс диспетчеризации.|  
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|Извлекает DISPID_AMBIENT_FORECOLOR цвета основного цвета окружения для всех элементов управления, определенные с помощью контейнера.|  
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|Извлекает DISPID_AMBIENT_LOCALEID, идентификатор языка, используемые контейнером.|  
|[CComControlBase::GetAmbientMessageReflect](#getambientmessagereflect)|Извлекает DISPID_AMBIENT_MESSAGEREFLECT, флаг, указывающий, хочет получать сообщения окна (например, WM_DRAWITEM), как события контейнера.|  
|[CComControlBase::GetAmbientPalette](#getambientpalette)|Извлекает DISPID_AMBIENT_PALETTE, используемый для доступа к HPALETTE контейнера.|  
|[CComControlBase::GetAmbientProperty](#getambientproperty)|Извлекает свойства контейнера, указанного параметром *идентификатор*.|  
|[CComControlBase::GetAmbientRightToLeft](#getambientrighttoleft)|Извлекает DISPID_AMBIENT_RIGHTTOLEFT, направление, в котором содержимое отображается в контейнере.|  
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|Извлекает DISPID_AMBIENT_SCALEUNITS окружения единицах (таких как дюймы или сантиметры) для работы с метками отображает контейнера.|  
|[CComControlBase::GetAmbientShowGrabHandles](#getambientshowgrabhandles)|Извлекает DISPID_AMBIENT_SHOWGRABHANDLES, флаг, указывающий, допускает ли контейнер элемента управления для отображения маркеров захвата для себя в активном состоянии.|  
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|Извлекает DISPID_AMBIENT_SHOWHATCHING, флаг, указывающий, допускает ли контейнер элемента управления для отображения окна с заштрихованный шаблон при активном пользовательского интерфейса.|  
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|Извлекает DISPID_AMBIENT_SUPPORTSMNEMONICS, флаг, указывающий, поддерживает ли контейнер клавиши.|  
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|Извлекает DISPID_AMBIENT_TEXTALIGN, предпочитаемый контейнер выравнивание текста: 0 для общего выравнивания (числа, текста справа налево), 1 для выравнивание по левому краю, 2 для выравнивание по центру и 3 для выравнивание по правому краю.|  
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|Извлекает DISPID_AMBIENT_TOPTOBOTTOM, направление, в котором содержимое отображается в контейнере.|  
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|Извлекает DISPID_AMBIENT_UIDEAD, флаг, указывающий, требуется ли контейнер элемента управления реагировать на действия пользовательского интерфейса.|  
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|Извлекает DISPID_AMBIENT_USERMODE, флаг, указывающий, является ли контейнер в режиме выполнения (TRUE) или в режиме конструктора (FALSE).|  
|[CComControlBase::GetDirty](#getdirty)|Возвращает значение члена данных `m_bRequiresSave`.|  
|[CComControlBase::GetZoomInfo](#getzoominfo)|Извлекает x и y значения числителя и знаменателя значения масштаба для активации элемента управления для редактирование на месте.|  
|[CComControlBase::InPlaceActivate](#inplaceactivate)|Вызывает переход элемента управления из неактивного состояния в команде в состоянии *iVerb* указывает.|  
|[CComControlBase::InternalGetSite](#internalgetsite)|Вызовите этот метод, чтобы запросить сайт элемента управления для указателя в определенный интерфейс.|  
|[CComControlBase::OnDraw](#ondraw)|Переопределите этот метод для рисования элемента управления.|  
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|Значение по умолчанию `OnDrawAdvanced` готовит нормализованный контекст устройства для рисования, а затем вызывает класс элемента управления `OnDraw` метод.|  
|[CComControlBase::OnKillFocus](#onkillfocus)|Проверяет, что элемент управления активен на месте и имеет допустимый элемент управления сайта, а затем сообщает контейнеру, что элемент управления потерял фокус.|  
|[CComControlBase::OnMouseActivate](#onmouseactivate)|Проверяет, что пользовательский Интерфейс в пользовательском режиме, а затем активирует элемент управления.|  
|[CComControlBase::OnPaint](#onpaint)|Подготавливает контейнер для рисования, получает клиентской области элемента управления, а затем вызывает класс элемента управления `OnDraw` метод.|  
|[CComControlBase::OnSetFocus](#onsetfocus)|Проверяет, что элемент управления активен на месте и имеет допустимый элемент управления сайта, а затем информирует контейнера элемента управления получил фокус.|  
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|Переопределите этот метод, чтобы предоставить собственные сочетания обработчики сочетаний клавиш.|  
|[CComControlBase::SendOnClose](#sendonclose)|Уведомляет все приемники зарегистрировано владелец advise, что элемент управления был закрыт.|  
|[CComControlBase::SendOnDataChange](#sendondatachange)|Уведомляет все приемники зарегистрировано владелец уведомлений об изменении данных элемента управления.|  
|[CComControlBase::SendOnRename](#sendonrename)|Уведомляет все приемники зарегистрировано владелец advise, что элемент управления имеет новый моникер.|  
|[CComControlBase::SendOnSave](#sendonsave)|Уведомляет все приемники зарегистрировано advise, которому он был сохранен.|  
|[CComControlBase::SendOnViewChange](#sendonviewchange)|Уведомляет все зарегистрированные приемники уведомлений, представление элемента управления изменилось.|  
|[CComControlBase::SetControlFocus](#setcontrolfocus)|Задает или удаляет фокус клавиатуры на или из элемента управления.|  
|[CComControlBase::SetDirty](#setdirty)|Задает элемент данных `m_bRequiresSave` значению *bDirty*.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComControlBase::m_bAutoSize](#m_bautosize)|Флаг, указывающий, что элемент управления не может быть любой другой размер.|  
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|Флаг, указывающий, что `IDataObjectImpl::GetData` и `CComControlBase::GetZoomInfo` должен устанавливать размер элемента управления из `m_sizeNatural` , а не из `m_sizeExtent`.|  
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|Флаг, указывающий, что `IDataObjectImpl::GetData` единицах HIMETRIC и пикселей не следует использовать при рисовании.|  
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|Флаг, указывающий, что элемент управления является активным на месте.|  
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|Флаг, указывающий, что контейнер поддерживает `IOleInPlaceSiteEx` интерфейс и OCX96 контролировать функции, такие как элементы управления без окон и без мерцания.|  
|[CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)|Флаг, указывающее, является ли элемент управления согласовано с контейнером о поддержке функций управления OCX96 (таких как элементы управления без мерцания и без окон) и является ли элемент управления оконного или без окон.|  
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|Флаг, указывающий, что элемент управления требует переделать это их представлением, когда контейнер изменяет отображаемый размер элемента управления.|  
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|Флаг, указывающий, что элемент управления был изменен с момента последнего сохранения.|  
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|Флаг, указывающий элемент управления хочет изменить его естественное экстент (его немасштабированным фактический размер) при изменении размера отображения элемента управления в контейнер.|  
|[CComControlBase::m_bUIActive](#m_buiactive)|Флаг, указывающий, элемента управления пользовательского интерфейса, например меню и панелей инструментов, активна.|  
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|Флаг, указывающий, что элемент управления используется область окна, предоставляемую контейнера.|  
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|Флаг, указывающий элемент управления был без окон, но может быть не безоконный теперь.|  
|[CComControlBase::m_bWindowOnly](#m_bwindowonly)|Флаг, указывающий, что элемент управления должен быть оконные, даже если контейнер поддерживает элементы управления без окон.|  
|[CComControlBase::m_bWndLess](#m_bwndless)|Флаг, указывающий, что элемент управления без окон.|  
|[CComControlBase::m_hWndCD](#m_hwndcd)|Содержит ссылку на дескриптор окна, связанный с элементом управления.|  
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|Число раз контейнера зафиксирован события (отказался принимать события) без промежуточных Разморозить событий (принятие события).|  
|[CComControlBase::m_rcPos](#m_rcpos)|Позиция элемента управления, выраженная в координатах контейнера в пикселях.|  
|[CComControlBase::m_sizeExtent](#m_sizeextent)|Область элемента управления в единицах HIMETRIC (каждая единица равна 0,01 мм) для отображения.|  
|[CComControlBase::m_sizeNatural](#m_sizenatural)|Физический размер элемента управления в единицах HIMETRIC (каждая единица равна 0,01 мм).|  
|[CComControlBase::m_spAdviseSink](#m_spadvisesink)|Прямой указатель на вспомогательного соединения в контейнере (контейнера [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)).|  
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|Объект `CComDispatchDriver` объект, который позволяет получать и задавать свойства контейнера через `IDispatch` указатель.|  
|[CComControlBase::m_spClientSite](#m_spclientsite)|Указатель на сайте клиента элемента управления в контейнере.|  
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|Предоставляет стандартный средства и сохраним вспомогательных соединений между объектами данных приемниками уведомлений.|  
|[CComControlBase::m_spInPlaceSite](#m_spinplacesite)|Указатель на контейнера [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), или [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) указатель на интерфейс.|  
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|Предоставляет стандартную реализацию способ сохранения вспомогательных соединений.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы для создания и управления элементами управления ATL. [Класс CComControl](../../atl/reference/ccomcontrol-class.md) является производным от `CComControlBase`. При создании элемента управления стандартного элемента управления или DHTML, с помощью мастера управления ATL, мастер автоматически будут производными от класса `CComControlBase`.  
  
 Дополнительные сведения о создании элемента управления, см. в разделе [учебник по ATL](../../atl/active-template-library-atl-tutorial.md). Дополнительные сведения о мастере проекта ATL, см. в статье [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="appearancetype"></a>  CComControlBase::AppearanceType  
 Переопределить, если ваш `m_nAppearance` не стандартное свойство типа **короткие**.  
  
```
typedef short AppearanceType;
```  
  
### <a name="remarks"></a>Примечания  
 Мастер элементов управления ATL добавляет `m_nAppearance` свойство типа short склада. Переопределить `AppearanceType` Если вы используете другой тип данных.  
  
##  <a name="ccomcontrolbase"></a>  CComControlBase::CComControlBase  
 Конструктор.  
  
```
CComControlBase(HWND& h);
```  
  
### <a name="parameters"></a>Параметры  
 *h*  
 Дескриптор окна, связанный с элементом управления.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует размер элемента управления в единицы HIMETRIC 5080 X 5080 (2 "X 2») и инициализирует `CComControlBase` значения членов данных значение NULL или значение FALSE.  
  
##  <a name="dtor"></a>  CComControlBase:: ~ CComControlBase  
 Деструктор  
  
```
~CComControlBase();
```  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления оконные, `~CComControlBase` уничтожает его путем вызова [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682).  
  
##  <a name="controlqueryinterface"></a>  CComControlBase::ControlQueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```  
  
### <a name="parameters"></a>Параметры  
 *IID*  
 Идентификатор GUID запрашиваемого интерфейса.  
  
 *ppv*  
 Указатель на указатель интерфейса, идентифицируемый *iid*, или значение NULL, если интерфейс не найден.  
  
### <a name="remarks"></a>Примечания  
 обрабатывает интерфейсы только в таблицу сопоставлений COM.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]  
  
##  <a name="doesverbactivate"></a>  CComControlBase::DoesVerbActivate  
 Проверяет, что *iVerb* параметра, используемого методом `IOleObjectImpl::DoVerb` либо активирует элемента управления пользовательского интерфейса (*iVerb* равно OLEIVERB_UIACTIVATE), определяет действие, выполняемое при двойном щелчке элемент управления (*iVerb* равно OLEIVERB_PRIMARY), отображает элемент управления (*iVerb* равно OLEIVERB_SHOW), или активирует элемент управления (*iVerb* равно OLEIVERB _INPLACEACTIVATE).  
  
```
BOOL DoesVerbActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>Параметры  
 *iVerb*  
 Значение, указывающее, действия, которые будут произведены методом `DoVerb`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если *iVerb* равно OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW или OLEIVERB_INPLACEACTIVATE; в противном случае возвращает FALSE.  
  
### <a name="remarks"></a>Примечания  
 Можно переопределить этот метод, чтобы определить свои собственные команды активации.  
  
##  <a name="doesverbuiactivate"></a>  CComControlBase::DoesVerbUIActivate  
 Проверяет, что *iVerb* параметра, используемого методом `IOleObjectImpl::DoVerb` заставляет элемент управления пользовательского интерфейса для активации и возвращает значение TRUE.  
  
```
BOOL DoesVerbUIActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>Параметры  
 *iVerb*  
 Значение, указывающее, действия, которые будут произведены методом `DoVerb`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если *iVerb* равно OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW или OLEIVERB_INPLACEACTIVATE. В противном случае метод возвращает значение FALSE.  
  
##  <a name="doverbproperties"></a>  CComControlBase::DoVerbProperties  
 Отображает страницы свойств элемента управления.  
  
```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```  
  
### <a name="parameters"></a>Параметры  
 *prcPosRec*  
 Зарезервировано.  
  
 *hwndParent*  
 Дескриптор окна, содержащего элемент управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]  
  
 [!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]  
  
##  <a name="fireviewchange"></a>  CComControlBase::FireViewChange  
 Вызовите этот метод, чтобы указать контейнер для перерисовки элемента управления или уведомлять зарегистрированных advise, приемники представление элемента управления изменилось.  
  
```
HRESULT FireViewChange();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления активен (данные-член класса элемента управления [CComControlBase::m_bInPlaceActive](#m_binplaceactive) имеет значение TRUE), уведомляет контейнер, необходимость перерисовки всей элемента управления. Если элемент управления неактивным, уведомляет элемент управления из зарегистрированных приемников уведомлений (через данные-член класса элемента управления [CComControlBase::m_spAdviseSink](#m_spadvisesink)), представление элемента управления изменилось.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]  
  
##  <a name="getambientappearance"></a>  CComControlBase::GetAmbientAppearance  
 Извлекает DISPID_AMBIENT_APPEARANCE, текущий внешний вид, установка для элемента управления: 0 для неструктурированных и 1 для 3D.  
  
```
HRESULT GetAmbientAppearance(short& nAppearance);
```  
  
### <a name="parameters"></a>Параметры  
 *nAppearance*  
 Свойство DISPID_AMBIENT_APPEARANCE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]  
  
##  <a name="getambientautoclip"></a>  CComControlBase::GetAmbientAutoClip  
 Извлекает DISPID_AMBIENT_AUTOCLIP, флаг, указывающий, поддерживает ли контейнер автоматического обрезки отображаемой области элемента управления.  
  
```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```  
  
### <a name="parameters"></a>Параметры  
 *bAutoClip*  
 Свойство DISPID_AMBIENT_AUTOCLIP.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientbackcolor"></a>  CComControlBase::GetAmbientBackColor  
 Извлекает DISPID_AMBIENT_BACKCOLOR, цвет фона окружения для всех элементов управления, определенные с помощью контейнера.  
  
```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```  
  
### <a name="parameters"></a>Параметры  
 *BackColor*  
 Свойство DISPID_AMBIENT_BACKCOLOR.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientcharset"></a>  CComControlBase::GetAmbientCharSet  
 Извлекает DISPID_AMBIENT_CHARSET окружения кодировки для всех элементов управления, определенные с помощью контейнера.  
  
```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```  
  
### <a name="parameters"></a>Параметры  
 *bstrCharSet*  
 Свойство DISPID_AMBIENT_CHARSET.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
##  <a name="getambientcodepage"></a>  CComControlBase::GetAmbientCodePage  
 Извлекает DISPID_AMBIENT_CODEPAGE окружения кодовую страницу для всех элементов управления, определенные с помощью контейнера.  
  
```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```  
  
### <a name="parameters"></a>Параметры  
 *ulCodePage*  
 Свойство DISPID_AMBIENT_CODEPAGE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
##  <a name="getambientdisplayasdefault"></a>  CComControlBase::GetAmbientDisplayAsDefault  
 Извлекает DISPID_AMBIENT_DISPLAYASDEFAULT, флаг, который имеет значение TRUE, если контейнер помечен элемент управления на этом сайте, как кнопка по умолчанию, и таким образом управления "Кнопка" следует рисовать сам полужирным фреймом.  
  
```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```  
  
### <a name="parameters"></a>Параметры  
 *bDisplayAsDefault*  
 Свойство DISPID_AMBIENT_DISPLAYASDEFAULT.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientdisplayname"></a>  CComControlBase::GetAmbientDisplayName  
 Извлекает DISPID_AMBIENT_DISPLAYNAME, имя контейнера предоставил к элементу управления.  
  
```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```  
  
### <a name="parameters"></a>Параметры  
 *bstrDisplayName*  
 Свойство DISPID_AMBIENT_DISPLAYNAME.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientfont"></a>  CComControlBase::GetAmbientFont  
 Извлекает указатель на контейнер окружения `IFont` интерфейс.  
  
```
HRESULT GetAmbientFont(IFont** ppFont);
```  
  
### <a name="parameters"></a>Параметры  
 *ppFont*  
 Указатель на контейнер окружения [IFont](http://msdn.microsoft.com/library/windows/desktop/ms680673) интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если свойство имеет значение NULL, указателем является значение NULL. Если указатель не равен NULL, вызывающий объект должен освободить указатель.  
  
##  <a name="getambientfontdisp"></a>  CComControlBase::GetAmbientFontDisp  
 Извлекает указатель на контейнер окружения `IFontDisp` интерфейс диспетчеризации.  
  
```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```  
  
### <a name="parameters"></a>Параметры  
 *ppFont*  
 Указатель на контейнер окружения [IFontDisp](http://msdn.microsoft.com/library/windows/desktop/ms692695) интерфейс диспетчеризации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Если свойство имеет значение NULL, указателем является значение NULL. Если указатель не равен NULL, вызывающий объект должен освободить указатель.  
  
##  <a name="getambientforecolor"></a>  CComControlBase::GetAmbientForeColor  
 Извлекает DISPID_AMBIENT_FORECOLOR цвета основного цвета окружения для всех элементов управления, определенные с помощью контейнера.  
  
```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```  
  
### <a name="parameters"></a>Параметры  
 *Цвет переднего плана*  
 Свойство DISPID_AMBIENT_FORECOLOR.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientlocaleid"></a>  CComControlBase::GetAmbientLocaleID  
 Извлекает DISPID_AMBIENT_LOCALEID, идентификатор языка, используемые контейнером.  
  
```
HRESULT GetAmbientLocaleID(LCID& lcid);
```  
  
### <a name="parameters"></a>Параметры  
 *lcid*  
 Свойство DISPID_AMBIENT_LOCALEID.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления можно использовать этот идентификатор адаптировать его пользовательский интерфейс для различных языков.  
  
##  <a name="getambientmessagereflect"></a>  CComControlBase::GetAmbientMessageReflect  
 Извлекает DISPID_AMBIENT_MESSAGEREFLECT, флаг, указывающий, хочет получать сообщения окна, контейнера (такие как `WM_DRAWITEM`) как события.  
  
```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```  
  
### <a name="parameters"></a>Параметры  
 *bMessageReflect*  
 Свойство DISPID_AMBIENT_MESSAGEREFLECT.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientpalette"></a>  CComControlBase::GetAmbientPalette  
 Извлекает DISPID_AMBIENT_PALETTE, используемый для доступа к HPALETTE контейнера.  
  
```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```  
  
### <a name="parameters"></a>Параметры  
 *hPalette*  
 Свойство DISPID_AMBIENT_PALETTE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientproperty"></a>  CComControlBase::GetAmbientProperty  
 Извлекает свойства контейнера, указанного параметром *dispid*.  
  
```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```  
  
### <a name="parameters"></a>Параметры  
 *Идентификатор DISPID*  
 Идентификатор извлекаемого свойства контейнера.  
  
 *var*  
 Переменная для получения свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Предоставляет набор вспомогательных функций для получения определенных свойств, например, ATL [CComControlBase::GetAmbientBackColor](#getambientbackcolor). Если нет подходящего метода доступен, используйте `GetAmbientProperty`.  
  
##  <a name="getambientrighttoleft"></a>  CComControlBase::GetAmbientRightToLeft  
 Извлекает DISPID_AMBIENT_RIGHTTOLEFT, направление, в котором содержимое отображается в контейнере.  
  
```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```  
  
### <a name="parameters"></a>Параметры  
 *bRightToLeft*  
 Свойство DISPID_AMBIENT_RIGHTTOLEFT. Значение TRUE, если содержимое отображается справа налево, FALSE, если он отображается слева направо.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
##  <a name="getambientscaleunits"></a>  CComControlBase::GetAmbientScaleUnits  
 Извлекает DISPID_AMBIENT_SCALEUNITS окружения единицах (таких как дюймы или сантиметры) для работы с метками отображает контейнера.  
  
```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```  
  
### <a name="parameters"></a>Параметры  
 *bstrScaleUnits*  
 Свойство DISPID_AMBIENT_SCALEUNITS.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientshowgrabhandles"></a>  CComControlBase::GetAmbientShowGrabHandles  
 Извлекает DISPID_AMBIENT_SHOWGRABHANDLES, флаг, указывающий, допускает ли контейнер элемента управления для отображения маркеров захвата для себя в активном состоянии.  
  
```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```  
  
### <a name="parameters"></a>Параметры  
 *bShowGrabHandles*  
 Свойство DISPID_AMBIENT_SHOWGRABHANDLES.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientshowhatching"></a>  CComControlBase::GetAmbientShowHatching  
 Извлекает DISPID_AMBIENT_SHOWHATCHING, флаг, указывающий, допускает ли контейнер элемента управления для отображения окна с заштрихованный шаблон при активном элемента управления пользовательского интерфейса.  
  
```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```  
  
### <a name="parameters"></a>Параметры  
 *bShowHatching*  
 Свойство DISPID_AMBIENT_SHOWHATCHING.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambientsupportsmnemonics"></a>  CComControlBase::GetAmbientSupportsMnemonics  
 Извлекает DISPID_AMBIENT_SUPPORTSMNEMONICS, флаг, указывающий, поддерживает ли контейнер клавиши.  
  
```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```  
  
### <a name="parameters"></a>Параметры  
 *bSupportsMnemonics*  
 Свойство DISPID_AMBIENT_SUPPORTSMNEMONICS.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambienttextalign"></a>  CComControlBase::GetAmbientTextAlign  
 Извлекает DISPID_AMBIENT_TEXTALIGN, предпочитаемый контейнер выравнивание текста: 0 для общего выравнивания (числа, текста справа налево), 1 для выравнивание по левому краю, 2 для выравнивание по центру и 3 для выравнивание по правому краю.  
  
```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```  
  
### <a name="parameters"></a>Параметры  
 *nTextAlign*  
 Свойство DISPID_AMBIENT_TEXTALIGN.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
##  <a name="getambienttoptobottom"></a>  CComControlBase::GetAmbientTopToBottom  
 Извлекает DISPID_AMBIENT_TOPTOBOTTOM, направление, в котором содержимое отображается в контейнере.  
  
```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```  
  
### <a name="parameters"></a>Параметры  
 *bTopToBottom*  
 Свойство DISPID_AMBIENT_TOPTOBOTTOM. Значение TRUE, если текст отображается сверху вниз, значение FALSE, если он отображается нижней к началу страницы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
##  <a name="getambientuidead"></a>  CComControlBase::GetAmbientUIDead  
 Извлекает DISPID_AMBIENT_UIDEAD, флаг, указывающий, требуется ли контейнер элемента управления реагировать на действия пользовательского интерфейса.  
  
```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```  
  
### <a name="parameters"></a>Параметры  
 *bUIDead*  
 Свойство DISPID_AMBIENT_UIDEAD.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Значение TRUE, если элемент управления не должен возвращать. Этот флаг применяется независимо от того, флаг DISPID_AMBIENT_USERMODE. См. в разделе [CComControlBase::GetAmbientUserMode](#getambientusermode).  
  
##  <a name="getambientusermode"></a>  CComControlBase::GetAmbientUserMode  
 Извлекает DISPID_AMBIENT_USERMODE, флаг, указывающий, является ли контейнер в режиме выполнения (TRUE) или в режиме конструктора (FALSE).  
  
```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```  
  
### <a name="parameters"></a>Параметры  
 *bUserMode*  
 Свойство DISPID_AMBIENT_USERMODE.  
  
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
 Извлекает x и y значения числителя и знаменателя значения масштаба для активации элемента управления для редактирование на месте.  
  
```
void GetZoomInfo(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Параметры  
 *Внедрение зависимостей*  
 Структура, которая будет содержать числителя и знаменателя значения масштаба. Дополнительные сведения см. в разделе [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md).  
  
### <a name="remarks"></a>Примечания  
 Коэффициент масштабирования — это доля естественному размеру элемента управления в его текущем степени.  
  
##  <a name="inplaceactivate"></a>  CComControlBase::InPlaceActivate  
 Вызывает переход элемента управления из неактивного состояния в команде в состоянии *iVerb* указывает.  
  
```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *iVerb*  
 Значение, указывающее, действия, которые будут произведены методом [IOleObjectImpl::DoVerb](../../atl/reference/ioleobjectimpl-class.md#doverb).  
  
 *prcPosRect*  
 Указатель на положение элемента управления на месте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Перед активацией этот метод проверяет, что элемент управления на сайте клиента, проверяет, какая часть элемента управления является видимым и возвращает расположение элемента управления в родительское окно. После активации элемента управления, этот метод активирует элемента управления пользовательского интерфейса и сообщает контейнеру, чтобы сделать элемент управления видимым.  
  
 Этот метод также возвращает `IOleInPlaceSite`, `IOleInPlaceSiteEx`, или `IOleInPlaceSiteWindowless` указатель интерфейса для элемента управления и сохраняет его в элемент данных класса элемента управления [CComControlBase::m_spInPlaceSite](#m_spinplacesite). Данные-члены класса элемента управления [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex), [CComControlBase::m_bWndLess](#m_bwndless), [CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)и [ CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) присваивается значение true, соответствующим образом.  
  
##  <a name="internalgetsite"></a>  CComControlBase::InternalGetSite  
 Вызовите этот метод, чтобы запросить сайт элемента управления для указателя в определенный интерфейс.  
  
```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```  
  
### <a name="parameters"></a>Параметры  
 *riid*  
 Идентификатор IID указателя интерфейса, который должен быть возвращен в *ppUnkSite*.  
  
 *ppUnkSite*  
 Адрес переменной указателя, получающей указатель интерфейса, запрашиваемый в *riid*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Если узел поддерживает интерфейс, запрошенный в *riid*, указатель, возвращенный с помощью параметра *ppUnkSite*. В противном случае *ppUnkSite* имеет значение NULL.  
  
##  <a name="m_bautosize"></a>  CComControlBase::m_bAutoSize  
 Флаг, указывающий, что элемент управления не может быть любой другой размер.  
  
```
unsigned m_bAutoSize:1;
```  
  
### <a name="remarks"></a>Примечания  
 Этот флаг установлен по `IOleObjectImpl::SetExtent` чего, если значение равно TRUE, функция возвращает E_FAIL.  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 При добавлении **Авторазмер** параметр [свойства запасов](../../atl/reference/stock-properties-atl-control-wizard.md) вкладке Мастер элементов управления ATL, мастер автоматически создает эти данные-член в классе элемента управления, создает put и получения методы для свойства и поддерживает [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) автоматическое уведомление контейнера при изменении свойства.  
  
##  <a name="m_bdrawfromnatural"></a>  CComControlBase::m_bDrawFromNatural  
 Флаг, указывающий, что `IDataObjectImpl::GetData` и `CComControlBase::GetZoomInfo` должен устанавливать размер элемента управления из `m_sizeNatural` , а не из `m_sizeExtent`.  
  
```
unsigned m_bDrawFromNatural:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_bdrawgetdatainhimetric"></a>  CComControlBase::m_bDrawGetDataInHimetric  
 Флаг, указывающий, что `IDataObjectImpl::GetData` единицах HIMETRIC и пикселей не следует использовать при рисовании.  
  
```
unsigned m_bDrawGetDataInHimetric:1;
```  
  
### <a name="remarks"></a>Примечания  
 Каждое логическое устройство HIMETRIC — 0,01 миллиметр.  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_binplaceactive"></a>  CComControlBase::m_bInPlaceActive  
 Флаг, указывающий, что элемент управления является активным на месте.  
  
```
unsigned m_bInPlaceActive:1;
```  
  
### <a name="remarks"></a>Примечания  
 Это означает, что элемент управления является видимым и его окно, если таковые имеются, видимо, но его меню и панелей инструментов могут быть неактивными. `m_bUIActive` Флаг указывает, пользовательский интерфейс элемента управления, таких как меню, уже активен.  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_binplacesiteex"></a>  CComControlBase::m_bInPlaceSiteEx  
 Флаг, указывающий, что контейнер поддерживает `IOleInPlaceSiteEx` интерфейс и OCX96 контролировать функции, такие как элементы управления без окон и без мерцания.  
  
```
unsigned m_bInPlaceSiteEx:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Элемент данных `m_spInPlaceSite` указывает [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), или [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) интерфейс, в зависимости от значения `m_bWndLess` и `m_bInPlaceSiteEx` флаги. (Элемент данных `m_bNegotiatedWnd` должно быть значение TRUE для `m_spInPlaceSite` указатель недействителен.)  
  
 Если `m_bWndLess` имеет значение FALSE и `m_bInPlaceSiteEx` имеет значение TRUE, `m_spInPlaceSite` является `IOleInPlaceSiteEx` указатель на интерфейс. См. в разделе [m_spInPlaceSite](#m_spinplacesite) для таблицы, показывающая отношение между эти элементы три данных.  
  
##  <a name="m_bnegotiatedwnd"></a>  CComControlBase::m_bNegotiatedWnd  
 Флаг, указывающее, является ли элемент управления согласовано с контейнером о поддержке функций управления OCX96 (таких как элементы управления без мерцания и без окон) и является ли элемент управления оконного или без окон.  
  
```
unsigned m_bNegotiatedWnd:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 `m_bNegotiatedWnd` Флаг должен иметь значение ИСТИНА для `m_spInPlaceSite` указатель недействителен.  
  
##  <a name="m_brecomposeonresize"></a>  CComControlBase::m_bRecomposeOnResize  
 Флаг, указывающий, что элемент управления требует переделать это их представлением, когда контейнер изменяет отображаемый размер элемента управления.  
  
```
unsigned m_bRecomposeOnResize:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Этот флаг установлен по [IOleObjectImpl::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent) и, если значение равно TRUE, `SetExtent` уведомляет контейнер, изменения представления. Если этот флаг установлен, OLEMISC_RECOMPOSEONRESIZE бит в [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) перечисления также должен быть установлен.  
  
##  <a name="m_brequiressave"></a>  CComControlBase::m_bRequiresSave  
 Флаг, указывающий, что элемент управления был изменен с момента последнего сохранения.  
  
```
unsigned m_bRequiresSave:1;
```  
  
### <a name="remarks"></a>Примечания  
 Значение `m_bRequiresSave` можно задать с помощью [CComControlBase::SetDirty](#setdirty) и получить с помощью [CComControlBase::GetDirty](#getdirty).  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_bresizenatural"></a>  CComControlBase::m_bResizeNatural  
 Флаг, указывающий элемент управления хочет изменить его естественное экстент (его немасштабированным фактический размер) при изменении размера отображения элемента управления в контейнер.  
  
```
unsigned m_bResizeNatural:1;
```  
  
### <a name="remarks"></a>Примечания  
 Этот флаг установлен по `IOleObjectImpl::SetExtent` и, если значение равно TRUE, размер передаваемого `SetExtent` назначается `m_sizeNatural`.  
  
 Переданный размер `SetExtent` всегда назначается `m_sizeExtent`, независимо от значения `m_bResizeNatural`.  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_buiactive"></a>  CComControlBase::m_bUIActive  
 Флаг, указывающий, элемента управления пользовательского интерфейса, например меню и панелей инструментов, активна.  
  
```
unsigned m_bUIActive:1;
```  
  
### <a name="remarks"></a>Примечания  
 `m_bInPlaceActive` Флаг указывает, что элемент управления является активной, но не его пользовательский интерфейс является активным.  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_busingwindowrgn"></a>  CComControlBase::m_bUsingWindowRgn  
 Флаг, указывающий, что элемент управления используется область окна, предоставляемую контейнера.  
  
```
unsigned m_bUsingWindowRgn:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_bwasoncewindowless"></a>  CComControlBase::m_bWasOnceWindowless  
 Флаг, указывающий элемент управления был без окон, но может быть не безоконный теперь.  
  
```
unsigned m_bWasOnceWindowless:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_bwindowonly"></a>  CComControlBase::m_bWindowOnly  
 Флаг, указывающий, что элемент управления должен быть оконные, даже если контейнер поддерживает элементы управления без окон.  
  
```
unsigned m_bWindowOnly:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_bwndless"></a>  CComControlBase::m_bWndLess  
 Флаг, указывающий, что элемент управления без окон.  
  
```
unsigned m_bWndLess:1;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Элемент данных `m_spInPlaceSite` указывает [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), или [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) интерфейс, в зависимости от значения `m_bWndLess` и [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex) флаги. (Элемент данных [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) должно быть значение TRUE для [CComControlBase::m_spInPlaceSite](#m_spinplacesite) указатель недействителен.)  
  
 Если `m_bWndLess` имеет значение TRUE, `m_spInPlaceSite` является `IOleInPlaceSiteWindowless` указатель на интерфейс. См. в разделе [CComControlBase::m_spInPlaceSite](#m_spinplacesite) таблицу с указанием на полный соотношение этих элементах данных.  
  
##  <a name="m_hwndcd"></a>  CComControlBase::m_hWndCD  
 Содержит ссылку на дескриптор окна, связанный с элементом управления.  
  
```
HWND& m_hWndCD;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_nfreezeevents"></a>  CComControlBase::m_nFreezeEvents  
 Число раз контейнера зафиксирован события (отказался принимать события) без промежуточных Разморозить событий (принятие события).  
  
```
short m_nFreezeEvents;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_rcpos"></a>  CComControlBase::m_rcPos  
 Позиция элемента управления, выраженная в координатах контейнера в пикселях.  
  
```
RECT m_rcPos;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_sizeextent"></a>  CComControlBase::m_sizeExtent  
 Область элемента управления в единицах HIMETRIC (каждая единица равна 0,01 мм) для отображения.  
  
```
SIZE m_sizeExtent;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Этот размер масштабируется по отображения. Указан физический размер элемента управления в `m_sizeNatural` элемент данных и является фиксированным.  
  
 Вы можете преобразовать размер пикселей с помощью глобальной функции [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).  
  
##  <a name="m_sizenatural"></a>  CComControlBase::m_sizeNatural  
 Физический размер элемента управления в единицах HIMETRIC (каждая единица равна 0,01 мм).  
  
```
SIZE m_sizeNatural;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Этот размер фиксирован, во время размер в `m_sizeExtent` масштабируется по отображения.  
  
 Вы можете преобразовать размер пикселей с помощью глобальной функции [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).  
  
##  <a name="m_spadvisesink"></a>  CComControlBase::m_spAdviseSink  
 Прямой указатель на вспомогательного соединения в контейнере (контейнера [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)).  
  
```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```     
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_spambientdispatch"></a>  CComControlBase::m_spAmbientDispatch  
 Объект `CComDispatchDriver` объект, который позволяет получить и задать свойства объекта с помощью `IDispatch` указатель.  
  
```
CComDispatchDriver m_spAmbientDispatch;
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_spclientsite"></a>  CComControlBase::m_spClientSite  
 Указатель на сайте клиента элемента управления в контейнере.  
  
```
CComPtr<IOleClientSite>
    m_spClientSite;
```     
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
##  <a name="m_spdataadviseholder"></a>  CComControlBase::m_spDataAdviseHolder  
 Предоставляет стандартный средства и сохраним вспомогательных соединений между объектами данных приемниками уведомлений.  
  
```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```     
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Объект данных является элементом управления, который может передавать данные, реализующий [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421), методы которого укажите среду формат и передачи данных.  
  
 Интерфейс `m_spDataAdviseHolder` реализует [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) и [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) методы для установки и удаления вспомогательных соединений в контейнер. Контейнер элемента управления должен реализовывать приемника уведомлений, поддерживая [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) интерфейс.  
  
##  <a name="m_spinplacesite"></a>  CComControlBase::m_spInPlaceSite  
 Указатель на контейнера [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), или [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) указатель на интерфейс.  
  
```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```     
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 `m_spInPlaceSite` Указатель является действительным только если [m_bNegotiatedWnd](#m_bnegotiatedwnd) флаг имеет значение TRUE.  
  
 В следующей таблице показано как `m_spInPlaceSite` зависит от типа указателя [m_bWndLess](#m_bwndless) и [m_bInPlaceSiteEx](#m_binplacesiteex) флаги член данных:  
  
|m_spInPlaceSite тип|m_bWndLess значение|m_bInPlaceSiteEx значение|  
|---------------------------|-----------------------|-----------------------------|  
|`IOleInPlaceSiteWindowless`|true|Значение TRUE или FALSE|  
|`IOleInPlaceSiteEx`|false|true|  
|`IOleInPlaceSite`|false|false|  
  
##  <a name="m_spoleadviseholder"></a>  CComControlBase::m_spOleAdviseHolder  
 Предоставляет стандартную реализацию способ сохранения вспомогательных соединений.  
  
```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```     
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Чтобы использовать эти данные-член в классе элемента управления, необходимо объявить ее как член данных в классе элемента управления. Класса элемента управления не наследует эти данные-член базового класса, так как он объявлен в пределах объединения в базовом классе.  
  
 Интерфейс `m_spOleAdviseHolder` реализует [IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573) и [IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749) методы для установки и удаления вспомогательных соединений в контейнер. Контейнер элемента управления должен реализовывать приемника уведомлений, поддерживая [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) интерфейс.  
  
##  <a name="ondraw"></a>  CComControlBase::OnDraw  
 Переопределите этот метод для рисования элемента управления.  
  
```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Параметры  
 *Внедрение зависимостей*  
 Ссылку на [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) структуру, содержащую графической информации, такие как аспект draw, границы элемента управления, и ли Рисование оптимизирован или нет.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию `OnDraw` удаляет или восстанавливает контекст устройства или не выполняет никаких действий, в зависимости от набора флагов в [CComControlBase::OnDrawAdvanced](#ondrawadvanced).  
  
 `OnDraw` Автоматически добавляется метод к классу элемента управления при создании элемента управления с помощью мастера управления ATL. По умолчанию мастер `OnDraw` рисует прямоугольник с надписью «ATL 8.0».  
  
### <a name="example"></a>Пример  
 См. в примере [CComControlBase::GetAmbientAppearance](#getambientappearance).  
  
##  <a name="ondrawadvanced"></a>  CComControlBase::OnDrawAdvanced  
 Значение по умолчанию `OnDrawAdvanced` готовит нормализованный контекст устройства для рисования, а затем вызывает класс элемента управления `OnDraw` метод.  
  
```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Параметры  
 *Внедрение зависимостей*  
 Ссылку на [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) структуру, содержащую графической информации, такие как аспект draw, границы элемента управления, и ли Рисование оптимизирован или нет.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если вы хотите принять контекст устройства контейнером без нормализации.  
  
 См. в разделе [CComControlBase::OnDraw](#ondraw) для получения дополнительных сведений.  
  
##  <a name="onkillfocus"></a>  CComControlBase::OnKillFocus  
 Проверяет, что элемент управления активен на месте и имеет допустимый элемент управления сайта, а затем сообщает контейнеру, что элемент управления потерял фокус.  
  
```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Параметры  
 *nMsg*  
 Зарезервировано.  
  
 *wParam*  
 Зарезервировано.  
  
 *lParam*  
 Зарезервировано.  
  
 *bHandled*  
 Флаг, указывающий, было ли успешно обработано сообщение окна. Значение по умолчанию — FALSE.  
  
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
 *nMsg*  
 Зарезервировано.  
  
 *wParam*  
 Зарезервировано.  
  
 *lParam*  
 Зарезервировано.  
  
 *bHandled*  
 Флаг, указывающий, было ли успешно обработано сообщение окна. Значение по умолчанию — FALSE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение 1.  
  
##  <a name="onpaint"></a>  CComControlBase::OnPaint  
 Подготавливает контейнер для рисования, получает клиентской области элемента управления, а затем вызывает класс элемента управления `OnDrawAdvanced` метод.  
  
```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```  
  
### <a name="parameters"></a>Параметры  
 *nMsg*  
 Зарезервировано.  
  
 *wParam*  
 HDC существующий.  
  
 *lParam*  
 Зарезервировано.  
  
 *lResult*  
 Зарезервировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает ноль.  
  
### <a name="remarks"></a>Примечания  
 Если *wParam* не равно NULL, `OnPaint` предполагается, что он содержит допустимый HDC и использует его вместо [CComControlBase::m_hWndCD](#m_hwndcd).  
  
##  <a name="onsetfocus"></a>  CComControlBase::OnSetFocus  
 Проверяет, что элемент управления активен на месте и имеет допустимый элемент управления сайта, а затем информирует контейнера элемента управления получил фокус.  
  
```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Параметры  
 *nMsg*  
 Зарезервировано.  
  
 *wParam*  
 Зарезервировано.  
  
 *lParam*  
 Зарезервировано.  
  
 *bHandled*  
 Флаг, указывающий, было ли успешно обработано сообщение окна. Значение по умолчанию — FALSE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение 1.  
  
### <a name="remarks"></a>Примечания  
 Отправляет уведомление в контейнер, что элемент управления получил фокус.  
  
##  <a name="pretranslateaccelerator"></a>  CComControlBase::PreTranslateAccelerator  
 Переопределите этот метод, чтобы предоставить собственные сочетания обработчики сочетаний клавиш.  
  
```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```  
  
### <a name="parameters"></a>Параметры  
 *pMsg*  
 Зарезервировано.  
  
 *hRet*  
 Зарезервировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 По умолчанию возвращает значение FALSE.  
  
##  <a name="sendonclose"></a>  CComControlBase::SendOnClose  
 Уведомляет все приемники зарегистрировано владелец advise, что элемент управления был закрыт.  
  
```
HRESULT SendOnClose();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Отправляет уведомление, что элемент управления закрыл его приемники уведомлений.  
  
##  <a name="sendondatachange"></a>  CComControlBase::SendOnDataChange  
 Уведомляет все приемники зарегистрировано владелец уведомлений об изменении данных элемента управления.  
  
```
HRESULT SendOnDataChange(DWORD advf = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *ADVF*  
 Флаги, указывающие способ вызова [IAdviseSink::OnDataChange](http://msdn.microsoft.com/library/windows/desktop/ms687283) выполняется. Значения: от [ADVF](http://msdn.microsoft.com/library/windows/desktop/ms693742) перечисления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
##  <a name="sendonrename"></a>  CComControlBase::SendOnRename  
 Уведомляет все приемники зарегистрировано владелец advise, что элемент управления имеет новый моникер.  
  
```
HRESULT SendOnRename(IMoniker* pmk);
```  
  
### <a name="parameters"></a>Параметры  
 *PMK*  
 Указатель на новый моникер элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Отправляет уведомление об изменении моникер для элемента управления.  
  
##  <a name="sendonsave"></a>  CComControlBase::SendOnSave  
 Уведомляет все приемники зарегистрировано advise, которому он был сохранен.  
  
```
HRESULT SendOnSave();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Отправляет уведомление, что элемент управления только что защитила его данные.  
  
##  <a name="sendonviewchange"></a>  CComControlBase::SendOnViewChange  
 Уведомляет все зарегистрированные приемники уведомлений, представление элемента управления изменилось.  
  
```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```  
  
### <a name="parameters"></a>Параметры  
 *dwAspect*  
 Аспект или представление элемента управления.  
  
 *Индекс*  
 Часть представления, которая была изменена. Допустимо только значение -1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 `SendOnViewChange` вызовы [IAdviseSink::OnViewChange](http://msdn.microsoft.com/library/windows/desktop/ms694337). Только значение *индекс* в настоящее время поддерживается является -1, означающее, что всего представления представляет интерес.  
  
##  <a name="setcontrolfocus"></a>  CComControlBase::SetControlFocus  
 Задает или удаляет фокус клавиатуры на или из элемента управления.  
  
```
BOOL SetControlFocus(BOOL bGrab);
```  
  
### <a name="parameters"></a>Параметры  
 *bGrab*  
 Если значение равно TRUE, устанавливает фокус клавиатуры для вызывающего элемента управления. Если значение равно FALSE, то удаляется фокус клавиатуры из вызывающего элемента управления, предоставляемые он имеет фокус.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если элемент управления успешно получает фокус; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Для оконного элемента управления, функции Windows API [SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms646312) вызывается. Для элемента управления без окон [IOleInPlaceSiteWindowless::SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms679745) вызывается. Через этот вызов безоконный элемент управления получает фокус клавиатуры и может отвечать на сообщения окна.  
  
##  <a name="setdirty"></a>  CComControlBase::SetDirty  
 Задает элемент данных `m_bRequiresSave` значению *bDirty*.  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>Параметры  
 *bDirty*  
 Значение элемента данных [CComControlBase::m_bRequiresSave](#m_brequiressave).  
  
### <a name="remarks"></a>Примечания  
 `SetDirty(TRUE)` должен вызываться для флага, что элемент управления был изменен с момента последнего сохранения. Значение `m_bRequiresSave` возвращается с помощью [CComControlBase::GetDirty](#getdirty).  
  
## <a name="see-also"></a>См. также  
 [Класс CComControl](../../atl/reference/ccomcontrol-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
