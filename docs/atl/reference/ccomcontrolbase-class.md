---
title: Класс CComControlBase
ms.date: 11/04/2016
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
helpviewer_keywords:
- CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
ms.openlocfilehash: 15cfa205337248181f02e6a1218d49e75bda58e6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748111"
---
# <a name="ccomcontrolbase-class"></a>Класс CComControlBase

Этот класс предоставляет методы создания и управления управлением управлением ATL.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class ATL_NO_VTABLE CComControlBase
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CComControlBase::AppearanceType](#appearancetype)|Переопределение, `m_nAppearance` если ваше акционерное имущество не **имеет короткого**типа.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComControlBase:CComControlBase](#ccomcontrolbase)|Конструктор.|
|[CComControlBase::CComControlBase](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComControlBase::ControlqueryInterface](#controlqueryinterface)|Извлекает указатель на запрошенный интерфейс.|
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|Проверяет, что параметр `IOleObjectImpl::DoVerb` *iVerb,* используемый либо активирует пользовательский интерфейс элемента управления *(iVerb* равен OLEIVERB_UIACTIVATE), определяет действие, предпринимаемое при двойном нажатии на элемент управления *(iVerb* равна OLEIVERB_PRIMARY), отображает элемент управления *(iVerb* равен OLEIVERB_SHOW), или активирует элемент управления *(iVerb* равен OLEIVERB_INPLACEACTIVATE).|
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|Проверяет, что параметр `IOleObjectImpl::DoVerb` *iVerb,* используемый вызывает пользовательский интерфейс элемента управления, чтобы активировать и возвращает TRUE.|
|[CComControlBase::DoVerbProperties](#doverbproperties)|Отображает страницы свойств элемента управления.|
|[CComControlBase::FireViewChange](#fireviewchange)|Позвоните по этому методу, чтобы сообщить контейнеру, чтобы перерисовать элемент управления, или уведомить зарегистрированные сообщите раковины, что представление элемента управления изменилось.|
|[CComControlBase::GetAmbientAppearance](#getambientappearance)|Получает DISPID_AMBIENT_APPEARANCE, текущая настройка внешнего вида для управления: 0 для плоской и 1 для 3D.|
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|Извлекает DISPID_AMBIENT_AUTOCLIP, флаг, указывающий, поддерживает ли контейнер автоматическое отсечение области дисплея управления.|
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|Извлекает DISPID_AMBIENT_BACKCOLOR, цвет фона окружающего фона для всех элементов управления, определяемый контейнером.|
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|Извлекает DISPID_AMBIENT_CHARSET, окружающий символ, установленный для всех элементов управления, определяемый контейнером.|
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|Извлекает DISPID_AMBIENT_CODEPAGE, окружающий символ, установленный для всех элементов управления, определяемый контейнером.|
|[CComControlBase::GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|Извлекает DISPID_AMBIENT_DISPLAYASDEFAULT, флаг, который является правдой, если контейнер отметил элемент управления на этом сайте, чтобы быть кнопкой по умолчанию, и, следовательно, кнопка управления должны рисовать себя с толще кадра.|
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|Извлекает DISPID_AMBIENT_DISPLAYNAME, имя контейнера поставил на контроль.|
|[CComControlBase::GetAmbientFont](#getambientfont)|Извлекает указатель на окружающий `IFont` интерфейс контейнера.|
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|Извлекает указатель на интерфейс отправки `IFontDisp` окружающего контейнера.|
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|Извлекает DISPID_AMBIENT_FORECOLOR, цвет переднего плана для всех элементов управления, определяемый контейнером.|
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|Извлекает DISPID_AMBIENT_LOCALEID, идентификатор языка, используемого контейнером.|
|[CComControlBase::GetAmbientMessageОтражение](#getambientmessagereflect)|Извлекает DISPID_AMBIENT_MESSAGEREFLECT, флаг, указывающий, хочет ли контейнер получать оконные сообщения (например, WM_DRAWITEM) в качестве событий.|
|[CComControlBase::GetAmbientPalette](#getambientpalette)|Извлекает DISPID_AMBIENT_PALETTE, используемый для доступа к Hpalette контейнера.|
|[CComControlBase::GetAmbientProperty](#getambientproperty)|Извлекает свойство контейнера, указанное *id*.|
|[CComControlBase:GetAmbientRightToleft](#getambientrighttoleft)|Извлекает DISPID_AMBIENT_RIGHTTOLEFT, направление, в котором содержимое отображается контейнером.|
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|Извлекает DISPID_AMBIENT_SCALEUNITS, окружающие устройства контейнера (например, дюймы или сантиметры) для маркировки дисплеев.|
|[CComControlBase::GetAmbientShowGrabручки](#getambientshowgrabhandles)|Извлекает DISPID_AMBIENT_SHOWGRABHANDLES, флаг, указывающий, позволяет ли элемент управления отображать ручки захвата для себя при активной активности.|
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|Извлекает DISPID_AMBIENT_SHOWHATCHING, флаг, указывающий, позволяет ли контейнер элемент управления отображаться с вылупимым узором при активном uI.|
|[CComControlBase::GetAmbientSupportsMneonics](#getambientsupportsmnemonics)|Извлекает DISPID_AMBIENT_SUPPORTSMNEMONICS, флаг, указывающий, поддерживает ли контейнер мнемоника клавиатуры.|
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|Извлекает DISPID_AMBIENT_TEXTALIGN, выравнивание текста, предпочитаемое контейнером: 0 для общего выравнивания (числа справа, текст влево), 1 для левого выравнивания, 2 для выравнивания центра и 3 для правого выравнивания.|
|[CComControlBase:GetAmbienttoptobottom](#getambienttoptobottom)|Извлекает DISPID_AMBIENT_TOPTOBOTTOM, направление, в котором содержимое отображается контейнером.|
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|Извлекает DISPID_AMBIENT_UIDEAD, флаг, указывающий, хочет ли контейнер, чтобы элемент управления реагировал на действия пользовательского интерфейса.|
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|Извлекает DISPID_AMBIENT_USERMODE, флаг, указывающий, находится ли контейнер в режиме запуска (TRUE) или режиме проектирования (FALSE).|
|[CComControlBase::GetDirty](#getdirty)|Возвращает значение участника `m_bRequiresSave`данных.|
|[CComControlBase::Get'oomInfo](#getzoominfo)|Извлекает значения x и y числителя и знаменателя фактора масштабирования для управления, активированного для редактирования на месте.|
|[CComControlBase::InplaceActivate](#inplaceactivate)|Вызывает переход управления из неактивного состояния в любое состояние, указывает глагол в *iVerb.*|
|[CComControlBase::InternalGetSite](#internalgetsite)|Вызовите этот метод, чтобы запросить сайт управления для указателя на идентифицированный интерфейс.|
|[CComControlBase::OnDraw](#ondraw)|Переопределить этот метод, чтобы нарисовать элемент управления.|
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|По `OnDrawAdvanced` умолчанию подготавливает нормализованный контекст устройства `OnDraw` для рисования, а затем вызывает метод элемента элемента управления.|
|[CComControlBase::OnKillFocus](#onkillfocus)|Проверяет, что элемент управления находится на месте активным и имеет действительный участок управления, а затем сообщает контейнеру, что элемент управления потерял фокус.|
|[CComControlBase::OnMouseActivate](#onmouseactivate)|Проверяет, что пользовательский интерфейс находится в пользовательском режиме, а затем активирует элемент управления.|
|[CComControlBase::Onpaint](#onpaint)|Готовит контейнер для покраски, получает клиентскую зону управления, затем `OnDraw` вызывает метод класса управления.|
|[CComControlBase:OnsetFocus](#onsetfocus)|Проверяет, что элемент управления находится на месте активным и имеет действительный участок управления, а затем сообщает контейнеру, который элемент управления получил фокус.|
|[CComControlBase: :PReTranslateAccelerator](#pretranslateaccelerator)|Переуверьте этот метод, чтобы предоставить свои собственные обработчики ускорителя клавиатуры.|
|[CComControlBase::Sendonclose](#sendonclose)|Уведомляет все консультационные раковины, зарегистрированные у владельца advise, что контроль был закрыт.|
|[CComControlBase::SendonDataChange](#sendondatachange)|Уведомляет все консультационные раковины, зарегистрированные у владельца рекомендаций, что данные управления изменились.|
|[CComControlBase::SendonRename](#sendonrename)|Уведомляет все консультационные раковины, зарегистрированные у владельца advise, что элемент управления имеет новое прозвище.|
|[CComControlBase::SendonSave](#sendonsave)|Уведомляет все консультационные раковины, зарегистрированные у владельца advise, что элемент управления был сохранен.|
|[CComControlBase::SendonViewChange](#sendonviewchange)|Уведомляет все зарегистрированные совещательные раковины о том, что представление элемента управления изменилось.|
|[CComControlBase::SetControlFocus](#setcontrolfocus)|Устанавливает или удаляет фокус клавиатуры к или из управления.|
|[CComControlBase::SetDirty](#setdirty)|Устанавливает член `m_bRequiresSave` данных к значению в *bDirty*.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComControlBase::m_bAutoSize](#m_bautosize)|Флаг, указывающий на элемент управления, не может быть какой-либо другой размер.|
|[CComControlBase:::m_bDrawFromNatural](#m_bdrawfromnatural)|Пометить, `IDataObjectImpl::GetData` `CComControlBase::GetZoomInfo` что и должны `m_sizeNatural` установить `m_sizeExtent`размер управления от, а не от .|
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|Пометить, `IDataObjectImpl::GetData` что при рисовании следует использовать единицы HIMETRIC, а не пиксели.|
|[CComControlBase:::m_bInPlaceActive](#m_binplaceactive)|Флаг, указывающий на то, что элемент управления находится на месте активного.|
|[CComControlBase:::m_bInPlaceSiteEx](#m_binplacesiteex)|Флаг, указывающий `IOleInPlaceSiteEx` на контейнер поддерживает интерфейс и функции управления OCX96, такие как без окон и без мерцания управления.|
|[CComControlBase:::m_bNegotiatedWnd](#m_bnegotiatedwnd)|Флаг, указывающий, вел ли элемент управления переговоры с контейнером о поддержке функций управления OCX96 (таких как без мерцание и элементы управления без окон), и является ли элемент управления оконным окном или без окон.|
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|Пометить, указывающий на элемент управления, необходимо перекомпонировать его презентацию при изменении размера дисплея элемента управления.|
|[CComControlBase:::m_bRequiresSave](#m_brequiressave)|Флаг, указывающий на элемент управления, изменился с момента его последнего сохранения.|
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|Флаг, указывающий на элемент управления, хочет изменить его естественный размер (его немасштабированный физический размер), когда контейнер изменяет размер дисплея элемента управления.|
|[CComControlBase::m_bUIActive](#m_buiactive)|Флаг с указанием пользовательского интерфейса элемента управления, таких как меню и панели инструментов, активен.|
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|Флаг, указывающий на элемент управления, использует область окна, поставляемую контейнерами.|
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|Флаг, указывающий на управление, был без окон, но может быть или не быть без окон сейчас.|
|[CComControlBase::m_bWindowOnly](#m_bwindowonly)|Флаг, указывающий на элемент управления, должен быть оконным, даже если контейнер поддерживает элементы управления без окон.|
|[CComControlBase::m_bWndLess](#m_bwndless)|Флаг, указывающий на управление, не имеет окон.|
|[CComControlBase::m_hWndCD](#m_hwndcd)|Содержит ссылку на ручку окна, связанную с элементом управления.|
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|Подсчет количества раз контейнер замораживал события (отказался принимать события) без промежуток оттепели событий (принятие событий).|
|[CComControlBase:::m_rcPos](#m_rcpos)|Положение в пикселях элемента управления, выраженное в координатах контейнера.|
|[CComControlBase:::m_sizeExtent](#m_sizeextent)|Степень управления в единицах HIMETRIC (каждая единица составляет 0,01 миллиметра) для конкретного дисплея.|
|[CComControlBase::m_sizeNatural](#m_sizenatural)|Физический размер управления в единицах HIMETRIC (каждая единица составляет 0,01 миллиметра).|
|[CComControlBase::m_spAdviseSink](#m_spadvisesink)|Прямой указатель на консультативное соединение на контейнере [(IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink)контейнера).|
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|Объект, `CComDispatchDriver` который позволяет извлекать и устанавливать свойства `IDispatch` контейнера через указатель.|
|[CComControlBase:::m_spClientSite](#m_spclientsite)|Указатель на клиентский сайт управления в контейнере.|
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|Предоставляет стандартные средства для хранения консультативных связей между объектами данных и консультирования раковин.|
|[CComControlBase:::m_spInPlaceSite](#m_spinplacesite)|Указатель на [контейнер ioleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex), или [IOleInPlaceSiteWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) интерфейс указатель.|
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|Обеспечивает стандартную реализацию способа хранения консультативных соединений.|

## <a name="remarks"></a>Remarks

Этот класс предоставляет методы создания и управления управлением управлением ATL. [Класс CComControl](../../atl/reference/ccomcontrol-class.md) происходит `CComControlBase`от . При создании стандартного управления или управления DHTML с помощью ATL Control `CComControlBase`Wizard мастер автоматически выводит ваш класс из.

Для получения дополнительной информации о [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md)создании элемента управления, см. Для получения дополнительной информации о ATL [Creating an ATL Project](../../atl/reference/creating-an-atl-project.md)проект Мастера, см.

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="ccomcontrolbaseappearancetype"></a><a name="appearancetype"></a>CComControlBase::AppearanceType

Переопределение, `m_nAppearance` если ваше акционерное имущество не **имеет короткого**типа.

```
typedef short AppearanceType;
```

### <a name="remarks"></a>Remarks

Мастер управления ATL `m_nAppearance` добавляет свойство запаса краткости типа. Переопределение, `AppearanceType` если вы используете другой тип данных.

## <a name="ccomcontrolbaseccomcontrolbase"></a><a name="ccomcontrolbase"></a>CComControlBase:CComControlBase

Конструктор.

```
CComControlBase(HWND& h);
```

### <a name="parameters"></a>Параметры

*H*<br/>
Ручка к окну, связанная с управлением.

### <a name="remarks"></a>Remarks

Инициализирует размер управления до 5080X5080 единиц HIMETRIC (2"X2") и инициализирует значения члена `CComControlBase` данных до NULL или FALSE.

## <a name="ccomcontrolbaseccomcontrolbase"></a><a name="dtor"></a>CComControlBase::CComControlBase

Деструктор

```
~CComControlBase();
```

### <a name="remarks"></a>Remarks

Если элемент управления окон, `~CComControlBase` уничтожает его, позвонив [DestroyWindow](/windows/win32/api/winuser/nf-winuser-destroywindow).

## <a name="ccomcontrolbasecontrolqueryinterface"></a><a name="controlqueryinterface"></a>CComControlBase::ControlqueryInterface

Извлекает указатель на запрошенный интерфейс.

```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
GUID запрашиваемого интерфейса.

*Ppv*<br/>
Указатель на указатель интерфейса, идентифицированный *iid,* или NULL, если интерфейс не найден.

### <a name="remarks"></a>Remarks

Только обрабатывает интерфейсы в таблице карты COM.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]

## <a name="ccomcontrolbasedoesverbactivate"></a><a name="doesverbactivate"></a>CComControlBase::DoesVerbActivate

Проверяет, что параметр `IOleObjectImpl::DoVerb` *iVerb,* используемый либо активирует пользовательский интерфейс элемента управления *(iVerb* равен OLEIVERB_UIACTIVATE), определяет действие, предпринимаемое при двойном нажатии на элемент управления *(iVerb* равна OLEIVERB_PRIMARY), отображает элемент управления *(iVerb* равен OLEIVERB_SHOW), или активирует элемент управления *(iVerb* равен OLEIVERB_INPLACEACTIVATE).

```
BOOL DoesVerbActivate(LONG iVerb);
```

### <a name="parameters"></a>Параметры

*iVerb*<br/>
Значение, указывающее действие, выполняемые `DoVerb`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если *iVerb* равняется OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW или OLEIVERB_INPLACEACTIVATE; в противном случае, возвращает FALSE.

### <a name="remarks"></a>Remarks

Вы можете переопределить этот метод, чтобы определить свой собственный глагол активации.

## <a name="ccomcontrolbasedoesverbuiactivate"></a><a name="doesverbuiactivate"></a>CComControlBase::DoesVerbUIActivate

Проверяет, что параметр `IOleObjectImpl::DoVerb` *iVerb,* используемый вызывает пользовательский интерфейс элемента управления, чтобы активировать и возвращает TRUE.

```
BOOL DoesVerbUIActivate(LONG iVerb);
```

### <a name="parameters"></a>Параметры

*iVerb*<br/>
Значение, указывающее действие, выполняемые `DoVerb`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если *iVerb* равен OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW или OLEIVERB_INPLACEACTIVATE. В противном случае метод возвращает FALSE.

## <a name="ccomcontrolbasedoverbproperties"></a><a name="doverbproperties"></a>CComControlBase::DoVerbProperties

Отображает страницы свойств элемента управления.

```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```

### <a name="parameters"></a>Параметры

*prcPosRec*<br/>
Зарезервировано.

*hwndParent*<br/>
Ручка окна, содержащая элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]

[!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]

## <a name="ccomcontrolbasefireviewchange"></a><a name="fireviewchange"></a>CComControlBase::FireViewChange

Позвоните по этому методу, чтобы сообщить контейнеру, чтобы перерисовать элемент управления, или уведомить зарегистрированные сообщите раковины, что представление элемента управления изменилось.

```
HRESULT FireViewChange();
```

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

Если элемент управления активен (член данных класса управления [CComControlBase::m_bInPlaceActive](#m_binplaceactive) является правдой), уведомляет контейнер, который требуется перерисовать весь элемент управления. Если элемент управления неактивен, уведомляет зарегистрированные приемники рекомендаций управления (через члена данных класса управления [CComControlBase::m_spAdviseSink),](#m_spadvisesink)что представление элемента управления изменилось.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]

## <a name="ccomcontrolbasegetambientappearance"></a><a name="getambientappearance"></a>CComControlBase::GetAmbientAppearance

Получает DISPID_AMBIENT_APPEARANCE, текущая настройка внешнего вида для управления: 0 для плоской и 1 для 3D.

```
HRESULT GetAmbientAppearance(short& nAppearance);
```

### <a name="parameters"></a>Параметры

*nПоявление*<br/>
Имущество DISPID_AMBIENT_APPEARANCE.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]

## <a name="ccomcontrolbasegetambientautoclip"></a><a name="getambientautoclip"></a>CComControlBase::GetAmbientAutoClip

Извлекает DISPID_AMBIENT_AUTOCLIP, флаг, указывающий, поддерживает ли контейнер автоматическое отсечение области дисплея управления.

```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```

### <a name="parameters"></a>Параметры

*bAutoClip*<br/>
Имущество DISPID_AMBIENT_AUTOCLIP.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientbackcolor"></a><a name="getambientbackcolor"></a>CComControlBase::GetAmbientBackColor

Извлекает DISPID_AMBIENT_BACKCOLOR, цвет фона окружающего фона для всех элементов управления, определяемый контейнером.

```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```

### <a name="parameters"></a>Параметры

*BackColor*<br/>
Свойство DISPID_AMBIENT_BACKCOLOR.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientcharset"></a><a name="getambientcharset"></a>CComControlBase::GetAmbientCharSet

Извлекает DISPID_AMBIENT_CHARSET, окружающий символ, установленный для всех элементов управления, определяемый контейнером.

```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```

### <a name="parameters"></a>Параметры

*bstrCharSet*<br/>
Имущество DISPID_AMBIENT_CHARSET.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="ccomcontrolbasegetambientcodepage"></a><a name="getambientcodepage"></a>CComControlBase::GetAmbientCodePage

Извлекает DISPID_AMBIENT_CODEPAGE, страницу окружающего кода для всех элементов управления, определяемую контейнером.

```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```

### <a name="parameters"></a>Параметры

*ulCodePage*<br/>
Имущество DISPID_AMBIENT_CODEPAGE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="ccomcontrolbasegetambientdisplayasdefault"></a><a name="getambientdisplayasdefault"></a>CComControlBase::GetAmbientDisplayasDefault

Извлекает DISPID_AMBIENT_DISPLAYASDEFAULT, флаг, который является правдой, если контейнер отметил элемент управления на этом сайте, чтобы быть кнопкой по умолчанию, и, следовательно, кнопка управления должны рисовать себя с толще кадра.

```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```

### <a name="parameters"></a>Параметры

*bDisplayAsDefault*<br/>
Имущество DISPID_AMBIENT_DISPLAYASDEFAULT.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientdisplayname"></a><a name="getambientdisplayname"></a>CComControlBase::GetAmbientDisplayName

Извлекает DISPID_AMBIENT_DISPLAYNAME, имя контейнера поставил на контроль.

```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```

### <a name="parameters"></a>Параметры

*bstrDisplayName*<br/>
Имущество DISPID_AMBIENT_DISPLAYNAME.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientfont"></a><a name="getambientfont"></a>CComControlBase::GetAmbientFont

Извлекает указатель на окружающий `IFont` интерфейс контейнера.

```
HRESULT GetAmbientFont(IFont** ppFont);
```

### <a name="parameters"></a>Параметры

*ppФон*<br/>
Указатель на окружающий интерфейс [IFont](/windows/win32/api/ocidl/nn-ocidl-ifont) контейнера.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

Если свойство NULL, указатель NULL. Если указатель не является NULL, абонент должен освободить указатель.

## <a name="ccomcontrolbasegetambientfontdisp"></a><a name="getambientfontdisp"></a>CComControlBase::GetAmbientFontDisp

Извлекает указатель на интерфейс отправки `IFontDisp` окружающего контейнера.

```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```

### <a name="parameters"></a>Параметры

*ppФон*<br/>
Указатель на интерфейс диспетчерской отправки [IFontDisp](/windows/win32/api/ocidl/nn-ocidl-ifontdisp) в контейнере.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Если свойство NULL, указатель NULL. Если указатель не является NULL, абонент должен освободить указатель.

## <a name="ccomcontrolbasegetambientforecolor"></a><a name="getambientforecolor"></a>CComControlBase::GetAmbientForeColor

Извлекает DISPID_AMBIENT_FORECOLOR, цвет переднего плана для всех элементов управления, определяемый контейнером.

```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```

### <a name="parameters"></a>Параметры

*Forecolor*<br/>
Имущество DISPID_AMBIENT_FORECOLOR.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientlocaleid"></a><a name="getambientlocaleid"></a>CComControlBase::GetAmbientLocaleID

Извлекает DISPID_AMBIENT_LOCALEID, идентификатор языка, используемого контейнером.

```
HRESULT GetAmbientLocaleID(LCID& lcid);
```

### <a name="parameters"></a>Параметры

*lcid*<br/>
Имущество DISPID_AMBIENT_LOCALEID.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

Элемент управления может использовать этот идентификатор для адаптации пользовательского интерфейса к различным языкам.

## <a name="ccomcontrolbasegetambientmessagereflect"></a><a name="getambientmessagereflect"></a>CComControlBase::GetAmbientMessageОтражение

Извлекает DISPID_AMBIENT_MESSAGEREFLECT, флаг, указывающий, хочет ли контейнер `WM_DRAWITEM`получать оконные сообщения (например), как события.

```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```

### <a name="parameters"></a>Параметры

*bMessageОтражение*<br/>
Имущество DISPID_AMBIENT_MESSAGEREFLECT.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientpalette"></a><a name="getambientpalette"></a>CComControlBase::GetAmbientPalette

Извлекает DISPID_AMBIENT_PALETTE, используемый для доступа к Hpalette контейнера.

```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```

### <a name="parameters"></a>Параметры

*hPalette*<br/>
Имущество DISPID_AMBIENT_PALETTE.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientproperty"></a><a name="getambientproperty"></a>CComControlBase::GetAmbientProperty

Извлекает свойство контейнера, указанное *dispid.*

```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```

### <a name="parameters"></a>Параметры

*Dispid*<br/>
Идентификация свойства контейнера, подхваченного.

*var*<br/>
Переменная для получения свойства.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

ATL предоставила набор функций помощника для получения определенных свойств, например, [CComControlBase::GetAmbientBackColor](#getambientbackcolor). Если нет подходящего метода, используйте `GetAmbientProperty`.

## <a name="ccomcontrolbasegetambientrighttoleft"></a><a name="getambientrighttoleft"></a>CComControlBase:GetAmbientRightToleft

Извлекает DISPID_AMBIENT_RIGHTTOLEFT, направление, в котором содержимое отображается контейнером.

```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```

### <a name="parameters"></a>Параметры

*bRightToleft*<br/>
Имущество DISPID_AMBIENT_RIGHTTOLEFT. Установите, чтобы true, если содержимое отображается справа налево, FALSE, если он отображается слева направо.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="ccomcontrolbasegetambientscaleunits"></a><a name="getambientscaleunits"></a>CComControlBase::GetAmbientScaleUnits

Извлекает DISPID_AMBIENT_SCALEUNITS, окружающие устройства контейнера (например, дюймы или сантиметры) для маркировки дисплеев.

```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```

### <a name="parameters"></a>Параметры

*bstrScaleUnits*<br/>
Имущество DISPID_AMBIENT_SCALEUNITS.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientshowgrabhandles"></a><a name="getambientshowgrabhandles"></a>CComControlBase::GetAmbientShowGrabручки

Извлекает DISPID_AMBIENT_SHOWGRABHANDLES, флаг, указывающий, позволяет ли элемент управления отображать ручки захвата для себя при активной активности.

```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```

### <a name="parameters"></a>Параметры

*bShowGrab Ручки*<br/>
Имущество DISPID_AMBIENT_SHOWGRABHANDLES.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientshowhatching"></a><a name="getambientshowhatching"></a>CComControlBase::GetAmbientShowHatching

Извлекает DISPID_AMBIENT_SHOWHATCHING, флаг, указывающий, позволяет ли контейнер отображаться с вылупимым узором при активном интерфейсе пользователя элемента управления.

```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```

### <a name="parameters"></a>Параметры

*bShowHatching*<br/>
Имущество DISPID_AMBIENT_SHOWHATCHING.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambientsupportsmnemonics"></a><a name="getambientsupportsmnemonics"></a>CComControlBase::GetAmbientSupportsMneonics

Извлекает DISPID_AMBIENT_SUPPORTSMNEMONICS, флаг, указывающий, поддерживает ли контейнер мнемоника клавиатуры.

```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```

### <a name="parameters"></a>Параметры

*bSupportsMnemonics*<br/>
Имущество DISPID_AMBIENT_SUPPORTSMNEMONICS.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambienttextalign"></a><a name="getambienttextalign"></a>CComControlBase::GetAmbientTextAlign

Извлекает DISPID_AMBIENT_TEXTALIGN, выравнивание текста, предпочитаемое контейнером: 0 для общего выравнивания (числа справа, текст влево), 1 для левого выравнивания, 2 для выравнивания центра и 3 для правого выравнивания.

```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```

### <a name="parameters"></a>Параметры

*nTextAlign*<br/>
Имущество DISPID_AMBIENT_TEXTALIGN.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetambienttoptobottom"></a><a name="getambienttoptobottom"></a>CComControlBase:GetAmbienttoptobottom

Извлекает DISPID_AMBIENT_TOPTOBOTTOM, направление, в котором содержимое отображается контейнером.

```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```

### <a name="parameters"></a>Параметры

*bTopToBottom*<br/>
Имущество DISPID_AMBIENT_TOPTOBOTTOM. Установите, чтобы true, если текст отображается сверху вниз, FALSE, если он отображается снизу вверх.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="ccomcontrolbasegetambientuidead"></a><a name="getambientuidead"></a>CComControlBase::GetAmbientUiDead

Извлекает DISPID_AMBIENT_UIDEAD, флаг, указывающий, хочет ли контейнер, чтобы элемент управления реагировал на действия пользовательского интерфейса.

```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```

### <a name="parameters"></a>Параметры

*bUIDead*<br/>
Имущество DISPID_AMBIENT_UIDEAD.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

Если правда, контроль не должен реагировать. Этот флаг применяется независимо от DISPID_AMBIENT_USERMODE флага. Смотрите [CComControlBase::GetAmbientUserMode](#getambientusermode).

## <a name="ccomcontrolbasegetambientusermode"></a><a name="getambientusermode"></a>CComControlBase::GetAmbientUserMode

Извлекает DISPID_AMBIENT_USERMODE, флаг, указывающий, находится ли контейнер в режиме запуска (TRUE) или режиме проектирования (FALSE).

```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```

### <a name="parameters"></a>Параметры

*bUserMode*<br/>
Имущество DISPID_AMBIENT_USERMODE.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

## <a name="ccomcontrolbasegetdirty"></a><a name="getdirty"></a>CComControlBase::GetDirty

Возвращает значение участника `m_bRequiresSave`данных.

```
BOOL GetDirty();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение [m_bRequiresSave](#m_brequiressave)члена данных.

### <a name="remarks"></a>Remarks

Это значение устанавливается с помощью [CComControlBase::SetDirty](#setdirty).

## <a name="ccomcontrolbasegetzoominfo"></a><a name="getzoominfo"></a>CComControlBase::Get'oomInfo

Извлекает значения x и y числителя и знаменателя фактора масштабирования для управления, активированного для редактирования на месте.

```cpp
void GetZoomInfo(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Параметры

*Ди*<br/>
Структура, которая будет держать числоир и знаменатель фактора масштабирования. Для получения дополнительной информации [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)см.

### <a name="remarks"></a>Remarks

Коэффициент масштабирования — это доля естественного размера элемента управления в его нынешнем размере.

## <a name="ccomcontrolbaseinplaceactivate"></a><a name="inplaceactivate"></a>CComControlBase::InplaceActivate

Вызывает переход управления из неактивного состояния в любое состояние, указывает глагол в *iVerb.*

```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```

### <a name="parameters"></a>Параметры

*iVerb*<br/>
Значение, указывающее действие, выполняемые [IOleObjectImpl::DoVerb](../../atl/reference/ioleobjectimpl-class.md#doverb).

*prcPosRect*<br/>
Указатель на положение элемента управления на месте.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Remarks

Перед активацией этот метод проверяет, имеет ли элемент управления клиентский участок, проверяет, насколько отображается элемент управления, и получает местоположение элемента управления в родительском окне. После активации элемента управления этот метод активирует пользовательский интерфейс элемента управления и говорит контейнеру сделать управление видимым.

Этот метод также `IOleInPlaceSite`получает `IOleInPlaceSiteEx`, `IOleInPlaceSiteWindowless` , или указатель интерфейса для управления и хранит его в данных члена класса управления [CComControlBase::m_spInPlaceSite](#m_spinplacesite). Члены класса управления [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex), [CComControlBase::m_bWndLess,](#m_bwndless) [CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)и [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) настроены на верность по мере необходимости.

## <a name="ccomcontrolbaseinternalgetsite"></a><a name="internalgetsite"></a>CComControlBase::InternalGetSite

Вызовите этот метод, чтобы запросить сайт управления для указателя на идентифицированный интерфейс.

```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
IID указателя интерфейса, который должен быть возвращен в *ppUnkSite*.

*ppUnkSite*<br/>
Адрес переменной указателя, которая получает указатель интерфейса, запрошенный в *riid*.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Если сайт поддерживает запрашиваемый интерфейс в *riid,* указатель возвращается с помощью *ppUnkSite*. В противном случае *ppUnkSite* установлен на NULL.

## <a name="ccomcontrolbasem_bautosize"></a><a name="m_bautosize"></a>CComControlBase::m_bAutoSize

Флаг, указывающий на элемент управления, не может быть какой-либо другой размер.

```
unsigned m_bAutoSize:1;
```

### <a name="remarks"></a>Remarks

Этот флаг проверяется `IOleObjectImpl::SetExtent` и, если true, вызывает функцию, чтобы вернуть E_FAIL.

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

Если вы добавите опцию **Auto Size** на вкладку [Stock Properties](../../atl/reference/stock-properties-atl-control-wizard.md) мастера управления ATL, мастер автоматически создает этот член данных в классе управления, создает методы размещения и получения для свойства и поддерживает [IPropertyNotifySink,](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) чтобы автоматически уведомить контейнер при изменении свойства.

## <a name="ccomcontrolbasem_bdrawfromnatural"></a><a name="m_bdrawfromnatural"></a>CComControlBase:::m_bDrawFromNatural

Пометить, `IDataObjectImpl::GetData` `CComControlBase::GetZoomInfo` что и должны `m_sizeNatural` установить `m_sizeExtent`размер управления от, а не от .

```
unsigned m_bDrawFromNatural:1;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_bdrawgetdatainhimetric"></a><a name="m_bdrawgetdatainhimetric"></a>CComControlBase::m_bDrawGetDataInHimetric

Пометить, `IDataObjectImpl::GetData` что при рисовании следует использовать единицы HIMETRIC, а не пиксели.

```
unsigned m_bDrawGetDataInHimetric:1;
```

### <a name="remarks"></a>Remarks

Каждая логическая единица HIMETRIC составляет 0,01 миллиметра.

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_binplaceactive"></a><a name="m_binplaceactive"></a>CComControlBase:::m_bInPlaceActive

Флаг, указывающий на то, что элемент управления находится на месте активного.

```
unsigned m_bInPlaceActive:1;
```

### <a name="remarks"></a>Remarks

Это означает, что элемент управления виден и его окно, если такого имеется, видно, но его меню и панели инструментов могут быть неактивными. Флаг `m_bUIActive` указывает на пользовательский интерфейс элемента управления, например меню, также активен.

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_binplacesiteex"></a><a name="m_binplacesiteex"></a>CComControlBase:::m_bInPlaceSiteEx

Флаг, указывающий `IOleInPlaceSiteEx` на контейнер поддерживает интерфейс и функции управления OCX96, такие как без окон и без мерцания управления.

```
unsigned m_bInPlaceSiteEx:1;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

Участник `m_spInPlaceSite` данных указывает на интерфейс [IOleInPlaceSite,](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite) [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)или [IOleInPlaceSiteWindowless,](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) `m_bWndLess` в `m_bInPlaceSiteEx` зависимости от значения и флагов. (Член `m_bNegotiatedWnd` данных должен быть `m_spInPlaceSite` правдивым, чтобы указатель был действительным.)

Если `m_bWndLess` FALSE `m_bInPlaceSiteEx` и является `m_spInPlaceSite` правдой, является указателем интерфейса. `IOleInPlaceSiteEx` Смотрите [m_spInPlaceSite](#m_spinplacesite) таблицу, показывающую взаимосвязь между этими тремя участниками данных.

## <a name="ccomcontrolbasem_bnegotiatedwnd"></a><a name="m_bnegotiatedwnd"></a>CComControlBase:::m_bNegotiatedWnd

Флаг, указывающий, вел ли элемент управления переговоры с контейнером о поддержке функций управления OCX96 (таких как без мерцание и элементы управления без окон), и является ли элемент управления оконным окном или без окон.

```
unsigned m_bNegotiatedWnd:1;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

Флаг `m_bNegotiatedWnd` должен быть правдой для указателя, `m_spInPlaceSite` чтобы быть действительным.

## <a name="ccomcontrolbasem_brecomposeonresize"></a><a name="m_brecomposeonresize"></a>CComControlBase::m_bRecomposeOnResize

Пометить, указывающий на элемент управления, необходимо перекомпонировать его презентацию при изменении размера дисплея элемента управления.

```
unsigned m_bRecomposeOnResize:1;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

Этот флаг проверяется [IOleObjectImpl::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent) и, `SetExtent` если true, уведомляет контейнер изменения представления. если этот флаг установлен, то следует установить OLEMISC_RECOMPOSEONRESIZE бит в перечислении [OLEMISC.](/windows/win32/api/oleidl/ne-oleidl-olemisc)

## <a name="ccomcontrolbasem_brequiressave"></a><a name="m_brequiressave"></a>CComControlBase:::m_bRequiresSave

Флаг, указывающий на элемент управления, изменился с момента его последнего сохранения.

```
unsigned m_bRequiresSave:1;
```

### <a name="remarks"></a>Remarks

Значение `m_bRequiresSave` можно установить с [CComControlBase::SetDirty](#setdirty) и получить с [CComControlBase::GetDirty](#getdirty).

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_bresizenatural"></a><a name="m_bresizenatural"></a>CComControlBase::m_bResizeNatural

Флаг, указывающий на элемент управления, хочет изменить его естественный размер (его немасштабированный физический размер), когда контейнер изменяет размер дисплея элемента управления.

```
unsigned m_bResizeNatural:1;
```

### <a name="remarks"></a>Remarks

Этот флаг проверяется, `IOleObjectImpl::SetExtent` и, если true, размер, передаваемый в `SetExtent` назначается `m_sizeNatural`.

Размер, передаваемый `SetExtent` `m_bResizeNatural` `m_sizeExtent`в всегда присваивается, независимо от значения .

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_buiactive"></a><a name="m_buiactive"></a>CComControlBase::m_bUIActive

Флаг с указанием пользовательского интерфейса элемента управления, таких как меню и панели инструментов, активен.

```
unsigned m_bUIActive:1;
```

### <a name="remarks"></a>Remarks

Флаг `m_bInPlaceActive` указывает на то, что элемент управления активен, но не является активным пользовательским интерфейсом.

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_busingwindowrgn"></a><a name="m_busingwindowrgn"></a>CComControlBase::m_bUsingWindowRgn

Флаг, указывающий на элемент управления, использует область окна, поставляемую контейнерами.

```
unsigned m_bUsingWindowRgn:1;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_bwasoncewindowless"></a><a name="m_bwasoncewindowless"></a>CComControlBase::m_bWasOnceWindowless

Флаг, указывающий на управление, был без окон, но может быть или не быть без окон сейчас.

```
unsigned m_bWasOnceWindowless:1;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_bwindowonly"></a><a name="m_bwindowonly"></a>CComControlBase::m_bWindowOnly

Флаг, указывающий на элемент управления, должен быть оконным, даже если контейнер поддерживает элементы управления без окон.

```
unsigned m_bWindowOnly:1;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_bwndless"></a><a name="m_bwndless"></a>CComControlBase::m_bWndLess

Флаг, указывающий на управление, не имеет окон.

```
unsigned m_bWndLess:1;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

Участник `m_spInPlaceSite` данных указывает на [iOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex), или [IOleInPlaceSiteWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) `m_bWndLess` интерфейс, в зависимости от значения и [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex) флаги. (Член данных [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) должно быть правдой для [CComControlBase::m_spInPlaceSite](#m_spinplacesite) указатель, чтобы быть действительным.)

Если `m_bWndLess` это `m_spInPlaceSite` правда, `IOleInPlaceSiteWindowless` является указателем интерфейса. Смотрите [CComControlBase::m_spInPlaceSite](#m_spinplacesite) таблицу, показывающую полную связь между этими членами данных.

## <a name="ccomcontrolbasem_hwndcd"></a><a name="m_hwndcd"></a>CComControlBase::m_hWndCD

Содержит ссылку на ручку окна, связанную с элементом управления.

```
HWND& m_hWndCD;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_nfreezeevents"></a><a name="m_nfreezeevents"></a>CComControlBase::m_nFreezeEvents

Подсчет количества раз контейнер замораживал события (отказался принимать события) без промежуток оттепели событий (принятие событий).

```
short m_nFreezeEvents;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_rcpos"></a><a name="m_rcpos"></a>CComControlBase:::m_rcPos

Положение в пикселях элемента управления, выраженное в координатах контейнера.

```
RECT m_rcPos;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_sizeextent"></a><a name="m_sizeextent"></a>CComControlBase:::m_sizeExtent

Степень управления в единицах HIMETRIC (каждая единица составляет 0,01 миллиметра) для конкретного дисплея.

```
SIZE m_sizeExtent;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

Этот размер масштабируется дисплеем. Физический размер элемента управления `m_sizeNatural` указан в элементе данных и фиксируется.

Вы можете преобразовать размер в пиксели с глобальной функцией [AtlHiMetricToPixel.](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)

## <a name="ccomcontrolbasem_sizenatural"></a><a name="m_sizenatural"></a>CComControlBase::m_sizeNatural

Физический размер управления в единицах HIMETRIC (каждая единица составляет 0,01 миллиметра).

```
SIZE m_sizeNatural;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

Этот размер фиксируется, `m_sizeExtent` в то время как размер в масштабируется дисплеем.

Вы можете преобразовать размер в пиксели с глобальной функцией [AtlHiMetricToPixel.](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)

## <a name="ccomcontrolbasem_spadvisesink"></a><a name="m_spadvisesink"></a>CComControlBase::m_spAdviseSink

Прямой указатель на консультативное соединение на контейнере [(IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink)контейнера).

```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_spambientdispatch"></a><a name="m_spambientdispatch"></a>CComControlBase::m_spAmbientDispatch

Объект, `CComDispatchDriver` который позволяет извлекать и устанавливать свойства `IDispatch` объекта через указатель.

```
CComDispatchDriver m_spAmbientDispatch;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_spclientsite"></a><a name="m_spclientsite"></a>CComControlBase:::m_spClientSite

Указатель на клиентский сайт управления в контейнере.

```
CComPtr<IOleClientSite>
    m_spClientSite;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

## <a name="ccomcontrolbasem_spdataadviseholder"></a><a name="m_spdataadviseholder"></a>CComControlBase::m_spDataAdviseHolder

Предоставляет стандартные средства для хранения консультативных связей между объектами данных и консультирования раковин.

```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

Объект данных — это элемент управления, который может передавать данные и реализует [IDataObject,](/windows/win32/api/objidl/nn-objidl-idataobject)методы которого определяют формат и среду передачи данных.

Интерфейс `m_spDataAdviseHolder` реализует методы [IDataObject::DAdvise](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) и [IDataObject::DUnadvise](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) для установления и удаления консультативных соединений с контейнером. Контейнер управления должен реализовать консультационную раковину, поддерживая интерфейс [IAdviseSink.](/windows/win32/api/objidl/nn-objidl-iadvisesink)

## <a name="ccomcontrolbasem_spinplacesite"></a><a name="m_spinplacesite"></a>CComControlBase:::m_spInPlaceSite

Указатель на [контейнер ioleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex), или [IOleInPlaceSiteWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) интерфейс указатель.

```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

Указатель `m_spInPlaceSite` действителен только в том случае, если [флаг m_bNegotiatedWnd](#m_bnegotiatedwnd) является правдой.

В следующей таблице `m_spInPlaceSite` показано, как тип указателя зависит от [m_bWndLess](#m_bwndless) и [m_bInPlaceSiteEx](#m_binplacesiteex) флагов членов данных:

|тип m_spInPlaceSite|m_bWndLess значение|m_bInPlaceSiteEx значение|
|---------------------------|-----------------------|-----------------------------|
|`IOleInPlaceSiteWindowless`|TRUE|TRUE или FALSE|
|`IOleInPlaceSiteEx`|FALSE|TRUE|
|`IOleInPlaceSite`|FALSE|FALSE|

## <a name="ccomcontrolbasem_spoleadviseholder"></a><a name="m_spoleadviseholder"></a>CComControlBase::m_spOleAdviseHolder

Обеспечивает стандартную реализацию способа хранения консультативных соединений.

```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Чтобы использовать этот элемент данных в классе управления, необходимо объявить его в качестве члена данных в классе управления. Ваш класс управления не унаследует этот элемент данных из базового класса, поскольку он заявлен в рамках соединения в базовом классе.

Интерфейс `m_spOleAdviseHolder` реализует [IOleObject::Advise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise) и [IOleObject::Unadvise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise) методы для установления и удаления консультативных соединений с контейнером. Контейнер управления должен реализовать консультационную раковину, поддерживая интерфейс [IAdviseSink.](/windows/win32/api/objidl/nn-objidl-iadvisesink)

## <a name="ccomcontrolbaseondraw"></a><a name="ondraw"></a>CComControlBase::OnDraw

Переопределить этот метод, чтобы нарисовать элемент управления.

```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Параметры

*Ди*<br/>
Ссылка на [структуру ATL_DRAWINFO,](../../atl/reference/atl-drawinfo-structure.md) содержащую информацию о рисовании, такую как аспект рисования, границы управления и оптимизирован ный рисунок или нет.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

По `OnDraw` умолчанию удаляет или восстанавливает контекст устройства или ничего не делает, в зависимости от флагов, установленных в [CComControlBase::OnDrawAdvanced](#ondrawadvanced).

Метод `OnDraw` автоматически добавляется в класс управления при создании элемента управления с помощью atL Control Wizard. По умолчанию `OnDraw` мастера рисует прямоугольник с меткой "ATL 8.0".

### <a name="example"></a>Пример

Смотрите пример [для CComControlBase::GetAmbientAppearance](#getambientappearance).

## <a name="ccomcontrolbaseondrawadvanced"></a><a name="ondrawadvanced"></a>CComControlBase::OndrawAdvanced

По `OnDrawAdvanced` умолчанию подготавливает нормализованный контекст устройства `OnDraw` для рисования, а затем вызывает метод элемента элемента управления.

```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Параметры

*Ди*<br/>
Ссылка на [структуру ATL_DRAWINFO,](../../atl/reference/atl-drawinfo-structure.md) содержащую информацию о рисовании, такую как аспект рисования, границы управления и оптимизирован ный рисунок или нет.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Переопределить этот метод, если вы хотите принять контекст устройства, пройденое контейнером, без его нормализации.

Смотрите [CComControlBase::OnDraw](#ondraw) для получения более подробной информации.

## <a name="ccomcontrolbaseonkillfocus"></a><a name="onkillfocus"></a>CComControlBase::OnKillFocus

Проверяет, что элемент управления находится на месте активным и имеет действительный участок управления, а затем сообщает контейнеру, что элемент управления потерял фокус.

```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Параметры

*nMsg*<br/>
Зарезервировано.

*wParam*<br/>
Зарезервировано.

*lParam*<br/>
Зарезервировано.

*bHandled*<br/>
Пометить, указано ли сообщение окна успешно обработано. Значение по умолчанию — FALSE.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 1.

## <a name="ccomcontrolbaseonmouseactivate"></a><a name="onmouseactivate"></a>CComControlBase::OnMouseActivate

Проверяет, что пользовательский интерфейс находится в пользовательском режиме, а затем активирует элемент управления.

```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Параметры

*nMsg*<br/>
Зарезервировано.

*wParam*<br/>
Зарезервировано.

*lParam*<br/>
Зарезервировано.

*bHandled*<br/>
Пометить, указано ли сообщение окна успешно обработано. Значение по умолчанию — FALSE.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 1.

## <a name="ccomcontrolbaseonpaint"></a><a name="onpaint"></a>CComControlBase::Onpaint

Готовит контейнер для покраски, получает клиентскую зону управления, затем `OnDrawAdvanced` вызывает метод класса управления.

```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```

### <a name="parameters"></a>Параметры

*nMsg*<br/>
Зарезервировано.

*wParam*<br/>
Существующий HDC.

*lParam*<br/>
Зарезервировано.

*lResult*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение 0.

### <a name="remarks"></a>Remarks

Если *wParam* не `OnPaint` является NULL, предполагает, что он содержит действительный HDC и использует его вместо [CComControlBase::m_hWndCD](#m_hwndcd).

## <a name="ccomcontrolbaseonsetfocus"></a><a name="onsetfocus"></a>CComControlBase:OnsetFocus

Проверяет, что элемент управления находится на месте активным и имеет действительный участок управления, а затем сообщает контейнеру, который элемент управления получил фокус.

```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Параметры

*nMsg*<br/>
Зарезервировано.

*wParam*<br/>
Зарезервировано.

*lParam*<br/>
Зарезервировано.

*bHandled*<br/>
Пометить, указано ли сообщение окна успешно обработано. Значение по умолчанию — FALSE.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает 1.

### <a name="remarks"></a>Remarks

Отправляет в контейнер уведомление о том, что элемент управления получил фокус.

## <a name="ccomcontrolbasepretranslateaccelerator"></a><a name="pretranslateaccelerator"></a>CComControlBase: :PReTranslateAccelerator

Переуверьте этот метод, чтобы предоставить свои собственные обработчики ускорителя клавиатуры.

```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```

### <a name="parameters"></a>Параметры

*pMsg*<br/>
Зарезервировано.

*hRet*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

По умолчанию возвращает FALSE.

## <a name="ccomcontrolbasesendonclose"></a><a name="sendonclose"></a>CComControlBase::Sendonclose

Уведомляет все консультационные раковины, зарегистрированные у владельца advise, что контроль был закрыт.

```
HRESULT SendOnClose();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Отправляет уведомление о том, что элемент управления закрыл свои совещательные раковины.

## <a name="ccomcontrolbasesendondatachange"></a><a name="sendondatachange"></a>CComControlBase::SendonDataChange

Уведомляет все консультационные раковины, зарегистрированные у владельца рекомендаций, что данные управления изменились.

```
HRESULT SendOnDataChange(DWORD advf = 0);
```

### <a name="parameters"></a>Параметры

*advf*<br/>
Советуйте флаги, которые указывают, как вызов [IAdviseSink](/windows/win32/api/objidl/nf-objidl-iadvisesink-ondatachange) производится. Значения взяты из перечисления [ADVF.](/windows/win32/api/objidl/ne-objidl-advf)

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="ccomcontrolbasesendonrename"></a><a name="sendonrename"></a>CComControlBase::SendonRename

Уведомляет все консультационные раковины, зарегистрированные у владельца advise, что элемент управления имеет новое прозвище.

```
HRESULT SendOnRename(IMoniker* pmk);
```

### <a name="parameters"></a>Параметры

*Pmk*<br/>
Указатель на новое прозвище управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Отправляет уведомление об изменении моникера для элемента управления.

## <a name="ccomcontrolbasesendonsave"></a><a name="sendonsave"></a>CComControlBase::SendonSave

Уведомляет все консультационные раковины, зарегистрированные у владельца advise, что элемент управления был сохранен.

```
HRESULT SendOnSave();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Отправляет уведомление о том, что элемент управления только что сохранил свои данные.

## <a name="ccomcontrolbasesendonviewchange"></a><a name="sendonviewchange"></a>CComControlBase::SendonViewChange

Уведомляет все зарегистрированные совещательные раковины о том, что представление элемента управления изменилось.

```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```

### <a name="parameters"></a>Параметры

*dwAspect*<br/>
Аспект или вид управления.

*Lindex*<br/>
Часть представления, которое изменилось. Действует только -1.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

`SendOnViewChange`звонки [iadvisesink::OnViewChange](/windows/win32/api/objidl/nf-objidl-iadvisesink-onviewchange). Единственное значение *lindex* в настоящее время поддерживается -1, что указывает на то, что весь вид представляет интерес.

## <a name="ccomcontrolbasesetcontrolfocus"></a><a name="setcontrolfocus"></a>CComControlBase::SetControlFocus

Устанавливает или удаляет фокус клавиатуры к или из управления.

```
BOOL SetControlFocus(BOOL bGrab);
```

### <a name="parameters"></a>Параметры

*bGrab*<br/>
Если true, устанавливает фокус клавиатуры на управление вызовом. Если FALSE, удаляет фокус клавиатуры из управления вызовом, при условии, что он имеет фокус.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если элемент управления успешно получает фокус; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Для управления окнами вызывается функция [SetFocus](/windows/win32/api/winuser/nf-winuser-setfocus) Windows API. Для управления без окон, [IOleInPlaceSiteWindowless::SetFocus](/windows/win32/api/ocidl/nf-ocidl-ioleinplacesitewindowless-setfocus) называется. Благодаря этому вызову управление без окон получает фокус клавиатуры и может отвечать на сообщения окон.

## <a name="ccomcontrolbasesetdirty"></a><a name="setdirty"></a>CComControlBase::SetDirty

Устанавливает член `m_bRequiresSave` данных к значению в *bDirty*.

```cpp
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Параметры

*bDirty*<br/>
Значение участника данных [CComControlBase::m_bRequiresSave](#m_brequiressave).

### <a name="remarks"></a>Remarks

`SetDirty(TRUE)`следует называть флагом, что элемент управления изменился с момента его последнего сохранения. Значение `m_bRequiresSave` извлекается с [CComControlBase::GetDirty](#getdirty).

## <a name="see-also"></a>См. также раздел

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
