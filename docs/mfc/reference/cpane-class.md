---
title: "Класс CPane | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPane
- AFXPANE/CPane
- AFXPANE/CPane::AdjustSizeImmediate
- AFXPANE/CPane::AllocElements
- AFXPANE/CPane::AllowShowOnPaneMenu
- AFXPANE/CPane::CalcAvailableSize
- AFXPANE/CPane::CalcInsideRect
- AFXPANE/CPane::CalcRecentDockedRect
- AFXPANE/CPane::CalcSize
- AFXPANE/CPane::CanBeDocked
- AFXPANE/CPane::CanBeTabbedDocument
- AFXPANE/CPane::ConvertToTabbedDocument
- AFXPANE/CPane::CopyState
- AFXPANE/CPane::Create
- AFXPANE/CPane::CreateDefaultMiniframe
- AFXPANE/CPane::CreateEx
- AFXPANE/CPane::DockByMouse
- AFXPANE/CPane::DockPane
- AFXPANE/CPane::DockPaneStandard
- AFXPANE/CPane::DockToFrameWindow
- AFXPANE/CPane::DoesAllowSiblingBars
- AFXPANE/CPane::FloatPane
- AFXPANE/CPane::GetAvailableExpandSize
- AFXPANE/CPane::GetAvailableStretchSize
- AFXPANE/CPane::GetBorders
- AFXPANE/CPane::GetClientHotSpot
- AFXPANE/CPane::GetDockSiteRow
- AFXPANE/CPane::GetExclusiveRowMode
- AFXPANE/CPane::GetHotSpot
- AFXPANE/CPane::GetMinSize
- AFXPANE/CPane::GetPaneName
- AFXPANE/CPane::GetVirtualRect
- AFXPANE/CPane::IsChangeState
- AFXPANE/CPane::IsDragMode
- AFXPANE/CPane::IsInFloatingMultiPaneFrameWnd
- AFXPANE/CPane::IsLeftOf
- AFXPANE/CPane::IsResizable
- AFXPANE/CPane::IsTabbed
- AFXPANE/CPane::LoadState
- AFXPANE/CPane::MoveByAlignment
- AFXPANE/CPane::MovePane
- AFXPANE/CPane::OnAfterChangeParent
- AFXPANE/CPane::OnBeforeChangeParent
- AFXPANE/CPane::OnPressCloseButton
- AFXPANE/CPane::OnShowControlBarMenu
- AFXPANE/CPane::OnShowControlBarMenu
- AFXPANE/CPane::RecalcLayout
- AFXPANE/CPane::SaveState
- AFXPANE/CPane::SetActiveInGroup
- AFXPANE/CPane::SetBorders
- AFXPANE/CPane::SetClientHotSpot
- AFXPANE/CPane::SetDockState
- AFXPANE/CPane::SetExclusiveRowMode
- AFXPANE/CPane::SetMiniFrameRTC
- AFXPANE/CPane::SetMinSize
- AFXPANE/CPane::SetVirtualRect
- AFXPANE/CPane::StretchPaneDeferWndPos
- AFXPANE/CPane::ToggleAutoHide
- AFXPANE/CPane::UndockPane
- AFXPANE/CPane::UpdateVirtualRect
- AFXPANE/CPane::OnAfterDock
- AFXPANE/CPane::OnAfterFloat
- AFXPANE/CPane::OnBeforeDock
- AFXPANE/CPane::OnBeforeFloat
- AFXPANE/CPane::m_bHandleMinSize
- AFXPANE/CPane::m_recentDockInfo
dev_langs:
- C++
helpviewer_keywords:
- CPane class
ms.assetid: 5c651a64-3c79-4d94-9676-45f6402a6bc5
caps.latest.revision: 30
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
ms.openlocfilehash: 586133277aa4a9d89ca15cdd496a1ca7e4232632
ms.lasthandoff: 02/24/2017

---
# <a name="cpane-class"></a>CPane Class
`CPane` Класс является улучшением из [CControlBar-класс](../../mfc/reference/ccontrolbar-class.md). При обновлении существующего проекта MFC, замените все вхождения `CControlBar` с `CPane`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPane : public CBasePane  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CPane::~CPane`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPane::AdjustSizeImmediate](#adjustsizeimmediate)|Немедленно повторно вычисляет макет панели.|  
|[CPane::AllocElements](#allocelements)|Выделяет память для внутреннего использования.|  
|[CPane::AllowShowOnPaneMenu](#allowshowonpanemenu)|Указывает, указан ли области в списке созданных средой выполнения панелей для приложения.|  
|[CPane::CalcAvailableSize](#calcavailablesize)|Вычисляет разность размер текущего окна прямоугольника и указанного прямоугольника.|  
|[CPane::CalcInsideRect](#calcinsiderect)|Вычисляет внутри прямоугольника, области, принимая во внимание границы и захват.|  
|[CPane::CalcRecentDockedRect](#calcrecentdockedrect)|Вычисляет недавно закрепленной прямоугольника.|  
|[CPane::CalcSize](#calcsize)|Вычисляет размер панели.|  
|[CPane::CanBeDocked](#canbedocked)|Определяет ли область можно закрепить в области заданного базового.|  
|[CPane::CanBeTabbedDocument](#canbetabbeddocument)|Определяет, можно ли преобразовать области документа с вкладками.|  
|[CPane::ConvertToTabbedDocument](#converttotabbeddocument)|Преобразует закрепляемой области документа с вкладками.|  
|[CPane::CopyState](#copystate)|Копирует состояние области. (Переопределяет [CBasePane::CopyState](../../mfc/reference/cbasepane-class.md#copystate).)|  
|[CPane::Create](#create)|Создает панель элементов управления и присоединяет его к `CPane` объекта.|  
|[CPane::CreateDefaultMiniframe](#createdefaultminiframe)|Создает для плавающей панели окна области.|  
|[CPane::CreateEx](#createex)|Создает панель элементов управления и присоединяет его к `CPane` объекта.|  
|`CPane::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CPane::DockByMouse](#dockbymouse)|Закрепляет область с помощью мыши закрепление метод.|  
|[CPane::DockPane](#dockpane)|Закрепляет плавающей панели базовой области.|  
|[CPane::DockPaneStandard](#dockpanestandard)|Закрепляет область с помощью структуры (standard) закрепления.|  
|[CPane::DockToFrameWindow](#docktoframewindow)|Закрепляет Закрепляемая область кадра. (Переопределяет `CBasePane::DockToFrameWindow`.)|  
|[CPane::DoesAllowSiblingBars](#doesallowsiblingbars)|Указывает ли можно закрепить другой области на той же строке, где закреплена текущей области.|  
|[CPane::FloatPane](#floatpane)|Смещает области.|  
|[CPane::GetAvailableExpandSize](#getavailableexpandsize)|Возвращает сумму, в пикселях, которые могут быть развернуты в области.|  
|[CPane::GetAvailableStretchSize](#getavailablestretchsize)|Возвращает сумму, в пикселях, который можно сжать области.|  
|[CPane::GetBorders](#getborders)|Возвращает ширину границы области.|  
|[CPane::GetClientHotSpot](#getclienthotspot)|Возвращает *гиперобъект* для области.|  
|[CPane::GetDockSiteRow](#getdocksiterow)|Возвращает по строке закрепления, в котором закрепленной панели.|  
|[CPane::GetExclusiveRowMode](#getexclusiverowmode)|Определяет, является ли панели в режиме монопольного строки.|  
|[CPane::GetHotSpot](#gethotspot)|Возвращает гиперобъект, хранятся в основной `CMFCDragFrameImpl` объекта.|  
|[CPane::GetMinSize](#getminsize)|Получает минимальный поддерживаемый размер для области.|  
|[CPane::GetPaneName](#getpanename)|Получает заголовок для панели.|  
|`CPane::GetResizeStep`|Для внутреннего использования.|  
|`CPane::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CPane::GetVirtualRect](#getvirtualrect)|Извлекает *виртуального прямоугольник* области.|  
|[CPane::IsChangeState](#ischangestate)|При перемещении области, этот метод анализирует позиции относительно других областей, закрепление строк и окна мини-фрейма панели и возвращает соответствующий `AFX_CS_STATUS` значение.|  
|[CPane::IsDragMode](#isdragmode)|Указывает, является, перетаскиваемый области.|  
|[CPane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Указывает, является ли область в окне фрейма с несколькими областями. (Переопределяет `CBasePane::IsInFloatingMultiPaneFrameWnd`.)|  
|[CPane::IsLeftOf](#isleftof)|Определяет, остается ли области (или выше) указанного прямоугольника.|  
|[CPane::IsResizable](#isresizable)|Определяет, возможно ли изменение размеров панели. (Переопределяет [CBasePane::IsResizable](../../mfc/reference/cbasepane-class.md#isresizable).)|  
|[CPane::IsTabbed](#istabbed)|Определяет, ввела ли области в элементе управления "Вкладка" окна с вкладками. (Переопределяет [CBasePane::IsTabbed](../../mfc/reference/cbasepane-class.md#istabbed).)|  
|[CPane::LoadState](#loadstate)|Загружает состояние области из реестра. (Переопределяет [CBasePane::LoadState](../../mfc/reference/cbasepane-class.md#loadstate).)|  
|[CPane::MoveByAlignment](#movebyalignment)|Перемещение области и прямоугольника, виртуальный на заданную величину.|  
|[CPane::MovePane](#movepane)|Перемещение области указанного прямоугольника.|  
|[CPane::OnAfterChangeParent](#onafterchangeparent)|Вызывается инфраструктурой при изменении родительской области.|  
|[CPane::OnBeforeChangeParent](#onbeforechangeparent)|Вызывается инфраструктурой при родительской области.|  
|[CPane::OnPressCloseButton](#onpressclosebutton)|Вызывается платформой, когда пользователь нажимает кнопку «Закрыть» на панели заголовка.|  
|`CPane::OnProcessDblClk`|Для внутреннего использования.|  
|[CPane::OnShowControlBarMenu](#onshowcontrolbarmenu)|Вызывается платформой непосредственно перед отображением меню особой панели.|  
|[CPane::OnShowControlBarMenu](#onshowcontrolbarmenu)|Вызывается платформой непосредственно перед отображением меню особой панели.|  
|`CPane::PrepareToDock`|Для внутреннего использования.|  
|[CPane::RecalcLayout](#recalclayout)|Обновление сведений о макете для области. (Переопределяет [CBasePane::RecalcLayout](../../mfc/reference/cbasepane-class.md#recalclayout).)|  
|[CPane::SaveState](#savestate)|Сохраняет состояние области реестра. (Переопределяет [CBasePane::SaveState](../../mfc/reference/cbasepane-class.md#savestate).)|  
|[CPane::SetActiveInGroup](#setactiveingroup)|Флаги панели как активный.|  
|[CPane::SetBorders](#setborders)|Задает значения границы области.|  
|[CPane::SetClientHotSpot](#setclienthotspot)|Задает гиперобъекты для области.|  
|[CPane::SetDockState](#setdockstate)|Восстанавливает сведения о состоянии для области закрепления.|  
|[CPane::SetExclusiveRowMode](#setexclusiverowmode)|Включает или отключает режим монопольного строк.|  
|[CPane::SetMiniFrameRTC](#setminiframertc)|Задает сведения о классе среды выполнения для окна области по умолчанию.|  
|[CPane::SetMinSize](#setminsize)|Задает минимальный допустимый размер панели.|  
|[CPane::SetVirtualRect](#setvirtualrect)|Наборы *виртуального прямоугольник* области.|  
|[CPane::StretchPaneDeferWndPos](#stretchpanedeferwndpos)|Увеличение области по вертикали или по горизонтали в зависимости от стиль закрепления.|  
|[CPane::ToggleAutoHide](#toggleautohide)|Переключение режима автоматического скрытия.|  
|[CPane::UndockPane](#undockpane)|Удаление области из сайта закрепления, по умолчанию ползунок или окна области, где он в настоящее время закреплен. (Переопределяет [CBasePane::UndockPane](../../mfc/reference/cbasepane-class.md#undockpane).)|  
|[CPane::UpdateVirtualRect](#updatevirtualrect)|Обновление виртуального прямоугольника.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPane::OnAfterDock](#onafterdock)|Вызывается платформой, если области были закреплены.|  
|[CPane::OnAfterFloat](#onafterfloat)|Вызывается инфраструктурой при ставшая область.|  
|[CPane::OnBeforeDock](#onbeforedock)|Вызывается инфраструктурой при Закрепить области.|  
|[CPane::OnBeforeFloat](#onbeforefloat)|Вызывается инфраструктурой при быть плавающий область.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPane::m_bHandleMinSize](#m_bhandleminsize)|Позволяет согласованно обрабатывать минимальный размер для областей.|  
|[CPane::m_recentDockInfo](#m_recentdockinfo)|Содержит последние сведения о закреплении.|  
  
## <a name="remarks"></a>Примечания  
 Как правило `CPane` объекты не создаются напрямую. Если требуется область, которая имеет функциональность, закрепления являются производными от объекта [CDockablePane](../../mfc/reference/cdockablepane-class.md). Если требуются функциональные возможности панели инструментов, являются производными объекта из [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).  
  
 При наследовании от класса `CPane`, его можно закрепить в [CDockSite](../../mfc/reference/cdocksite-class.md) и его можно перемещать в [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxPane.h  
  
##  <a name="adjustsizeimmediate"></a>CPane::AdjustSizeImmediate  
 Немедленно повторно вычисляет макет панели.  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bRecalcLayout`  
 `TRUE`автоматически пересчитать макет панели; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, когда динамически изменять макет панели. Например можно вызвать этот метод, если скрыть или Показать кнопки панели инструментов.  
  
##  <a name="allocelements"></a>CPane::AllocElements  
 Выделяет память для внутреннего использования.  
  
```  
BOOL AllocElements(
    int nElements,  
    int cbElement);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nElements`  
 Количество элементов, для которого необходимо выделить хранилище.  
  
 [in] `cbElement`  
 Размер в байтах элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `FALSE`Если происходит сбой выделения памяти; в противном случае — `TRUE`.  
  
##  <a name="allowshowonpanemenu"></a>CPane::AllowShowOnPaneMenu  
 Указывает, указан ли области в списке созданных средой выполнения панелей для приложения.  
  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область отображается в списке. в противном случае — `FALSE`. Базовая реализация всегда возвращает `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Приложение создается мастером приложений содержит пункт меню, в которой перечислены области, которые он содержит. Этот метод определяет, отображается ли область в списке.  
  
##  <a name="calcavailablesize"></a>CPane::CalcAvailableSize  
 Вычисляет разность размер текущего окна прямоугольника и указанного прямоугольника.  
  
```  
virtual CSize CalcAvailableSize(CRect rectRequired);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectRequired`  
 Требуется прямоугольник.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Разница в ширину и высоту между `rectRequired` и текущего прямоугольника окна.  
  
##  <a name="calcinsiderect"></a>CPane::CalcInsideRect  
 Вычисляет внутри прямоугольника, области, включая границы и захват.  
  
```  
void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rect`  
 Содержит размер и смещение клиентской области панели.  
  
 [in] `bHorz`  
 `TRUE`Если области ориентирован горизонтально. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, когда требуется повторно вычислить макет для области. `rect` Параметр заполняется размера и смещения клиентской области панели. Сюда входят границы и захват.  
  
##  <a name="calcrecentdockedrect"></a>CPane::CalcRecentDockedRect  
 Вычисляет недавно закрепленной прямоугольника.  
  
```  
void CalcRecentDockedRect();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод обновляет [CPane::m_recentDockInfo](#m_recentdockinfo).  
  
##  <a name="calcsize"></a>CPane::CalcSize  
 Вычисляет размер панели.  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bVertDock`  
 `TRUE`Если области расположенное, `FALSE` в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию этого метода возвращает размер (0, 0).  
  
### <a name="remarks"></a>Примечания  
 Производные классы должны переопределять этот метод.  
  
##  <a name="canbedocked"></a>CPane::CanBeDocked  
 Определяет, если область можно закрепить в области заданного базового.  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDockBar`  
 Указывает область, где закрепляться в этой области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если в этой области можно закрепить в указанной области закрепления. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод обычно вызывается платформой для определения ли область можно закрепить в указанной области закрепления. Определить можно закрепить области, метод области в настоящее время включена закрепления выравнивания.  
  
 Включить закрепление в различных сторон окна фрейма, вызвав [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="canbetabbeddocument"></a>CPane::CanBeTabbedDocument  
 Определяет, может ли преобразование области для документа с вкладками.  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области могут быть преобразованы в документ с вкладками. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе и возврата `FALSE` Если вы хотите запретить преобразование документа с вкладками в области. Документа с вкладками, не появится в меню «положение окна».  
  
##  <a name="converttotabbeddocument"></a>CPane::ConvertToTabbedDocument  
 Преобразует закрепляемой области документа с вкладками.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bActiveTabOnly`  
 Не используется в `CPane::ConvertToTabbedDocument`.  
  
### <a name="remarks"></a>Примечания  
 Можно преобразовать только закрепляемых областей для документов с вкладками. Сведения см. в разделе [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).  
  
##  <a name="copystate"></a>CPane::CopyState  
 Копирует состояние области.  
  
```  
virtual void CopyState(CPane* pOrgBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pOrgBar`  
 Указатель на область.  
  
### <a name="remarks"></a>Примечания  
 Этот метод копирует состояние `pOrgBar` в текущей области.  
  
##  <a name="create"></a>CPane::Create  
 Создает панель элементов управления и присоединяет его к [CPane](../../mfc/reference/cpane-class.md) объекта.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszClassName`  
 Задает имя класса Windows.  
  
 [in] `dwStyle`  
 Задает атрибуты стилей окна. Дополнительные сведения см. в разделе [стили окна](../../mfc/reference/window-styles.md).  
  
 [in] `rect`  
 Задает начальный размер и положение `pParentWnd` окна в координатах клиента.  
  
 [in] [out]`pParentWnd`  
 Указывает родительского окна в этой области.  
  
 [in] `nID`  
 Указывает идентификатор области.  
  
 [in] `dwControlBarStyle`  
 Задает стиль для области. Дополнительные сведения см. в разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 [in] [out]`pContext`  
 Указывает контекст Создание области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область создана успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает область Windows и присоединяет его к `CPane` объекта.  
  
 Если явно не инициализирован [CPane::m_recentDockInfo](#m_recentdockinfo) перед вызовом метода `Create`, параметр `rect` будет использоваться как прямоугольник с плавающей запятой или закрепления панели.  
  
##  <a name="createdefaultminiframe"></a>CPane::CreateDefaultMiniframe  
 Создает для плавающей панели окна области.  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectInitial`  
 Задает начальный размер и положение, в экранных координатах окна области для создания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Окна созданной области.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой для создания окна области, если область перемещается. Окна области может иметь тип [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) или типа [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md). Окна области нескольких создается в том случае, если область имеет `AFX_CBRS_FLOAT_MULTI` стиль.  
  
 Информация о классе среды выполнения для окна области хранится в `CPane::m_pMiniFrameRTC` член. Чтобы установить этот компонент, если вы решите создать настраиваемые области windows можно использовать производный класс.  
  
##  <a name="createex"></a>CPane::CreateEx  
 Создает панель элементов управления и присоединяет его к [CPane](../../mfc/reference/cpane-class.md) объекта.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwStyleEx`  
 Указывает атрибуты окна расширенного стиля. Дополнительные сведения см. в разделе [расширенные стили окна](../../mfc/reference/extended-window-styles.md).  
  
 [in] `lpszClassName`  
 Задает имя класса Windows.  
  
 [in] `dwStyle`  
 Задает атрибуты стилей окна. Дополнительные сведения см. в разделе [стили окна](../../mfc/reference/window-styles.md).  
  
 [in] `rect`  
 Задает начальный размер и положение `pParentWnd` окна в координатах клиента.  
  
 [in] [out]`pParentWnd`  
 Указывает родительского окна в этой области.  
  
 [in] `nID`  
 Указывает идентификатор области.  
  
 [in] `dwControlBarStyle`  
 Задает стиль для области. Дополнительные сведения см. в разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 [in] [out]`pContext`  
 Указывает контекст создать для области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область создана успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает область Windows и присоединяет его к `CPane` объекта.  
  
 Если явно не инициализирован [CPane::m_recentDockInfo](#m_recentdockinfo) перед вызовом метода `CreateEx`, параметр `rect` будет использоваться как прямоугольник с плавающей запятой или закрепления панели.  
  
##  <a name="dockbymouse"></a>CPane::DockByMouse  
 Закрепляет область с помощью мыши.  
  
```  
virtual BOOL DockByMouse(CBasePane* pDockBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDockBar`  
 Указывает базовый области, к которому закрепление этой панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области были закреплены успешно; в противном случае — `FALSE`.  
  
##  <a name="dockpane"></a>CPane::DockPane  
 Закрепляет плавающей панели базовой области.  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pDockBar`  
 Указывает базовый области закрепление этой панели.  
  
 [in] `lpRect`  
 Указывает прямоугольник в базовой области, где закрепляться в этой области.  
  
 [in] `dockMethod`  
 Указывает метод закрепления. Ниже приведены доступные параметры:  
  
|Параметр|Описание|  
|------------|-----------------|  
|`DM_UNKNOWN`|Платформа использует этот параметр, когда метод закрепления неизвестно. Области не хранить его последней позиции с плавающей запятой. Этот параметр также позволяет программно Закрепление панели при необходимости хранения последней позиции с плавающей запятой.|  
|`DM_MOUSE`|Для внутреннего использования.|  
|`DM_DBL_CLICK`|Этот параметр используется при двойном щелчке захвата. Области перемещен в последней позиции закрепления. Незакрепленного области, дважды щелкнув области перемещен в последней позиции с плавающей запятой.|  
|`DM_SHOW`|Этот параметр можно использовать, чтобы программно закрепить на панели. Области хранит его последней позиции с плавающей запятой.|  
|`DM_RECT`|Панель закреплена на регион, который задается параметром `lpRect`.|  
|`DM_STANDARD`|При использовании этого параметра платформа рисует области как кадр структуры при его перемещении.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области были закреплены успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод закрепляет область панели базовый, определяемый `pDockBar` параметр. Сначала необходимо включить закрепление путем вызова [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="dockpanestandard"></a>CPane::DockPaneStandard  
 Закрепляет область с помощью структуры (standard) закрепления.  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bWasDocked`  
 `TRUE`Если область была успешно закрепить; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод всегда возвращает `this` указателя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется только для тех областей, которые являются производными от [CDockablePane класса](../../mfc/reference/cdockablepane-class.md). Дополнительные сведения см. в разделе [CDockablePane::DockPaneStandard](../../mfc/reference/cdockablepane-class.md#dockpanestandard).  
  
##  <a name="docktoframewindow"></a>CPane::DockToFrameWindow  
 Закрепляет Закрепляемая область кадра.  
  
```  
virtual BOOL DockToFrameWindow(
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL,  
    DWORD dwDockFlags = DT_DOCK_LAST,  
    CBasePane* pRelativeBar = NULL,  
    int nRelativeIndex = -1,  
    BOOL bOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwAlignment`  
 Сторона, нужно закрепить области родительского фрейма.  
  
 [in] `lpRect`  
 Указанный размер.  
  
 [in] `dwDockFlags`  
 Не обрабатывается.  
  
 [in] `pRelativeBar`  
 Не обрабатывается.  
  
 [in] `nRelativeIndex`  
 Не обрабатывается.  
  
 [in] `bOuterEdge`  
 Если `TRUE` и других закрепляемых областей на стороне, которые задаются параметром `dwAlignment`, панель закреплена за пределами области, ближе к краю родительского фрейма. Если `FALSE`, области закреплена ближе к центру клиентской области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `FALSE`Если разделитель области ( [класса CPaneDivider](../../mfc/reference/cpanedivider-class.md)) не может быть создан; в противном случае — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="doesallowsiblingbars"></a>CPane::DoesAllowSiblingBars  
 Указывает ли можно закрепить другой области на той же строке, где закреплена текущей области.  
  
```  
virtual BOOL DoesAllowSiblingBars() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если в этой области можно закрепить в другую область на одной строке. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Можно включить или отключить это поведение, вызывая [CPane::SetExclusiveRowMode](#setexclusiverowmode).  
  
 По умолчанию отключен режим монопольного строки имеют панели инструментов и меню строки монопольный режим включен.  
  
##  <a name="floatpane"></a>CPane::FloatPane  
 Смещает области.  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod = DM_UNKNOWN,  
    bool bShow = true);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectFloat`  
 Указывает расположение, в экранных координатах для размещения области, когда она перемещается.  
  
 [in] `dockMethod`  
 Задает метод закрепления для использования при плавающий области. Список возможных значений см. в разделе [CPane::DockPane](#dockpane).  
  
 [in] `bShow`  
 `TRUE`для отображения области при плавающий; в противном случае — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области были успешно перемещается или области не перемещается, так как [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat) возвращает `FALSE`; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для float области в точке, которая определяется `rectFloat` параметр. Этот метод автоматически создает родительского окна области для области.  
  
##  <a name="getavailableexpandsize"></a>CPane::GetAvailableExpandSize  
 Возвращает сумму, в пикселях, которые могут быть развернуты в области.  
  
```  
virtual int GetAvailableExpandSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если панель закреплена горизонтально, возвращает значение ширины; в противном случае — возвращает значение высоты.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getavailablestretchsize"></a>CPane::GetAvailableStretchSize  
 Возвращает сумму, в пикселях, который можно сжать области.  
  
```  
virtual int GetAvailableStretchSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер в точках, можно сжать области. Если панель закреплена горизонтально, эта сумма представляет доступную ширину; в противном случае — это доступная высота.  
  
### <a name="remarks"></a>Примечания  
 Доступный размер распределения вычисляется путем вычитания минимально допустимого размера области ( [CPane::GetMinSize](#getminsize)) из текущего размера ( [CWnd::GetWindowRect](../../mfc/reference/cwnd-class.md#getwindowrect)).  
  
##  <a name="getborders"></a>CPane::GetBorders  
 Возвращает ширину границы области.  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CRect](../../atl-mfc-shared/reference/crect-class.md) , содержащий Текущая ширина в пикселях каждого края панели. Например, значение `left` членом `CRect` объект является Ширина левой границы.  
  
### <a name="remarks"></a>Примечания  
 Чтобы задать размер границы, вызовите [CPane::SetBorders](#setborders).  
  
##  <a name="getclienthotspot"></a>CPane::GetClientHotSpot  
 Возвращает *гиперобъект* для области.  
  
```  
CPoint GetClientHotSpot() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 *Гиперобъект* является точкой на области, в которой пользователь выбирает и удерживает перемещение области. Активная область используется для гладкой анимации области при перемещении из закрепленной позиции.  
  
##  <a name="getdocksiterow"></a>CPane::GetDockSiteRow  
 Возвращает строку dock ( [CDockingPanesRow класс](../../mfc/reference/cdockingpanesrow-class.md)) в закрепленной панели.  
  
```  
CDockingPanesRow* GetDockSiteRow() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CDockingPanesRow`*, указывающая на строку dock закреплено области, или `NULL` Если области не закрепляются.  
  
##  <a name="getexclusiverowmode"></a>CPane::GetExclusiveRowMode  
 Определяет, является ли панели в режиме монопольного строки.  
  
```  
virtual BOOL GetExclusiveRowMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель в режиме монопольного строк; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о режиме монопольного строки в разделе [CPane::SetExclusiveRowMode](#setexclusiverowmode).  
  
##  <a name="gethotspot"></a>CPane::GetHotSpot  
 Возвращает гиперобъект, хранятся в основной `CMFCDragFrameImpl` объекта.  
  
```  
CPoint GetHotSpot() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 `CPane` Класс содержит `CMFCDragFrameImpl` объекта, `m_dragFrameImpl`, который отвечает за рисование прямоугольник, который отображается, когда пользователь перемещает панель в стандартном режиме закрепления. Активная точка используется для отрисовки прямоугольника относительно текущего положения мыши при перемещении области.  
  
##  <a name="getminsize"></a>CPane::GetMinSize  
 Получает минимальный поддерживаемый размер для области.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `size`  
 Объект `CSize` объект, который заполняется минимально допустимого размера.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getpanename"></a>CPane::GetPaneName  
 Получает заголовок для панели.  
  
```  
virtual void GetPaneName(CString& strName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `strName`  
 Объект `CString` объект, который заполняется заголовка.  
  
### <a name="remarks"></a>Примечания  
 Заголовок панели отображается в области заголовка при области закрепленные или с плавающей запятой. Если область является частью группы с вкладками, заголовок отображается в области вкладки. Если в режиме автоматического скрытия панели, заголовок отображается на `CMFCAutoHideButton`.  
  
##  <a name="getvirtualrect"></a>CPane::GetVirtualRect  
 Извлекает *виртуального прямоугольник* области.  
  
```  
void GetVirtualRect(CRect& rectVirtual) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rectVirtual`  
 Объект `CRect` объект, который заполняется виртуального прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 При перемещении область платформа сохраняет исходное положение панели в виртуальный прямоугольника. Платформа можно использовать виртуальный прямоугольник для восстановления исходной позиции области.  
  
 Не следует вызывать методы, которые связаны с виртуального прямоугольники, если вы перемещаете панелей программным способом.  
  
##  <a name="ischangestate"></a>CPane::IsChangeState  
 При перемещении области, анализирует их положение относительно других областей, закрепление строк и окна мини-фрейма этот метод и возвращает соответствующий `AFX_CS_STATUS` значение.  
  
```  
virtual AFX_CS_STATUS IsChangeState(
    int nOffset,  
    CBasePane** ppTargetBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nOffset`  
 Указывает чувствительность закрепления. Например, область, в которой перемещается в пределах `nOffset` пикселов из строки dock закрепляется.  
  
 [in] `ppTargetBar`  
 При возвращении метода `ppTargetBar` содержит указатель на объект, к которому следует прикрепить текущей области, или `NULL` закрепление без необходимости выполнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из следующих `AFX_CS_STATUS` значения:  
  
|Значение|Описание|  
|-----------|-----------------|  
|`CS_NOTHING`|Область не рядом с сайта закрепления. Платформа не закрепление области.|  
|`CS_DOCK_IMMEDIATELY`|Области находится на сайте закрепления и `DT_IMMEDIATE` стиль включен. Платформа закрепляет область немедленно.|  
|`CS_DELAY_DOCK`|Область — через другой закрепляемую область или край фрейма главного сайта закрепления. Платформа закрепляет область, когда пользователь отпускает перемещения.|  
|`CS_DELAY_DOCK_TO_TAB`|Область находится на сайте закрепления, вызывающая панели для закрепления в окно с вкладками. Это происходит, когда область — заголовок другого закрепляемой области или в области вкладки область с вкладками. Платформа закрепляет область, когда пользователь отпускает перемещения.|  
  
##  <a name="isdragmode"></a>CPane::IsDragMode  
 Указывает, перемещается ли области.  
  
```  
virtual BOOL IsDragMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`При перемещении области; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isinfloatingmultipaneframewnd"></a>CPane::IsInFloatingMultiPaneFrameWnd  
 Указывает, является ли область в окне фрейма несколькими областями ( [CMultiPaneFrameWnd класса](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель в окне фрейма несколькими областями. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 В окне фрейма несколькими областями может перемещаться только закрепляемых областей. Таким образом `CPane::IsInFloatingMultiPaneFrameWnd` всегда возвращает `FALSE`.  
  
##  <a name="isleftof"></a>CPane::IsLeftOf  
 Определяет, остается ли области (или выше) указанного прямоугольника.  
  
```  
bool IsLeftOf(
    CRect rect,  
    bool bWindowRect = true) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Объект `CRect` объект, используемый для сравнения.  
  
 [in] `bWindowRect`  
 Если `TRUE`, `rect` предполагается, что содержат экранные координаты; Если `FALSE`, `rect` должна содержать координаты клиента.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Если панель закреплена горизонтально, этот метод проверяет, остается ли его расположение из `rect`. В противном случае, этот метод проверяет, является ли расположение выше `rect`.  
  
##  <a name="isresizable"></a>CPane::IsResizable  
 Указывает, является ли изменяться размеры области.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель можно изменять; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Базовый `CPane` объектов не изменяется.  
  
 Закрепления диспетчером изменяемые флаг для определения области макета. Не изменять размер панелей всегда можно найти в папке внешние края родительского фрейма.  
  
 Не изменяемые области не может находиться в закрепление контейнеры.  
  
##  <a name="istabbed"></a>CPane::IsTabbed  
 Определяет ли области был вставлен в элемент управления "Вкладка" окна с вкладками.  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области вкладок; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Состояние с вкладками обрабатывается отдельно от числа с плавающей закрепления и автоматического скрытия состояния.  
  
##  <a name="loadstate"></a>CPane::LoadState  
 Загружает состояние области из реестра.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Имя профиля.  
  
 [in] `nIndex`  
 Индекс профиля.  
  
 [in] `uiID`  
 Идентификатор области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель состояния был загружен успешно. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод для загрузки состояния панели из реестра. Его можно переопределить в производном классе загрузить дополнительные данные, сохраненные с [CPane::SaveState](#savestate).  
  
 При переопределении этого метода также вызывать базовый метод и вернуть `FALSE` возвращает базовый метод `FALSE`.  
  
##  <a name="m_bhandleminsize"></a>CPane::m_bHandleMinSize  
 Позволяет согласованно обрабатывать области минимальный размеры.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHandleMinSize;  
```  
  
### <a name="remarks"></a>Примечания  
 Если один или несколько закрепляемых областей приложения переопределяют `GetMinSize`, или если приложение вызывает `SetMinSize`, можно присвоить статический элемент `TRUE` Чтобы включить платформу согласованно обрабатывать способ изменения размеров панели.  
  
 Если это значение `TRUE`, все панели, размер которого следует сократить ниже их минимальный размер обрезаются не растягивается. Так как платформа использует области окон в целях изменения размера области, не изменяйте размер окна области закрепления панели, если это значение `TRUE`.  
  
##  <a name="m_recentdockinfo"></a>CPane::m_recentDockInfo  
 Содержит последние сведения о закреплении.  
  
```  
CRecentDockSiteInfo m_recentDockInfo;  
```  
  
### <a name="remarks"></a>Примечания  
 Платформа хранит закрепления последние сведения о состоянии для области в этом члене.  
  
##  <a name="movebyalignment"></a>CPane::MoveByAlignment  
 Перемещение области и прямоугольника, виртуальный на заданную величину.  
  
```  
BOOL MoveByAlignment(
    DWORD dwAlignment,  
    int nOffset);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwAlignment`  
 Задает выравнивание панели.  
  
 [in] `nOffset`  
 Размер в точках, в котором для перемещения области и прямоугольника, виртуальный.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 `dwAlignment`может быть одним из следующих значений:  
  
|Значение|Описание|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Позволяет области закреплено в верхней части клиентской области окна фрейма.|  
|`CBRS_ALIGN_BOTTOM`|Позволяет области закреплено в нижнюю часть клиентской области окна фрейма.|  
|`CBRS_ALIGN_LEFT`|Включает области, чтобы закрепить левого края клиентской области окна фрейма.|  
|`CBRS_ALIGN_RIGHT`|Включает области, чтобы прикрепить к правой части клиентской области окна фрейма.|  
|`CBRS_ALIGN_ANY`|Включает области, чтобы закрепить с любой стороны клиентской области окна фрейма.|  
  
 Если `dwAlignment` содержит `CBRS_ALIGN_LEFT` или `CBRS_ALIGN_RIGHT` флаг, области и прямоугольника виртуального перемещаются по горизонтали; в противном случае, если `dwAlignment` содержит `CBRS_ALIGN_TOP` или `CBRS_ALIGN_BOTTOM` флаг, области и прямоугольника виртуального перемещаются по вертикали.  
  
##  <a name="movepane"></a>CPane::MovePane  
 Перемещение области указанного прямоугольника.  
  
```  
virtual CSize MovePane(
    CRect rectNew,  
    BOOL bForceMove,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectNew`  
 Задает новый прямоугольник для области.  
  
 [in] `bForceMove`  
 Если `TRUE`, этот метод игнорирует области Минимальный допустимый размер ( [CPane::GetMinSize](#getminsize)); в противном случае, настраивается область, если необходимо, чтобы убедиться, что он не меньше минимально допустимого размера.  
  
 [in] `hdwp`  
 Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CSize` , содержащий различия в ширину и высоту прямоугольника старое и новое (старый прямоугольника — `rectNew`).  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется только для закрепляемых областей.  
  
##  <a name="onafterchangeparent"></a>CPane::OnAfterChangeParent  
 Вызывается инфраструктурой при изменении родительской области.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pWndOldParent`  
 Область предыдущего родительского окна.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается инфраструктурой при изменении родительской области из-за операции закрепления или с плавающей запятой.  
  
##  <a name="onafterdock"></a>CPane::OnAfterDock  
 Вызывается платформой, если области были закреплены.  
  
```  
virtual void OnAfterDock(
    CBasePane* pBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Этот параметр не используется.  
  
 [in] `lpRect`  
 Этот параметр не используется.  
  
 [in] `dockMethod`  
 Этот параметр не используется.  
  
##  <a name="onafterfloat"></a>CPane::OnAfterFloat  
 Вызывается платформой после перемещается в область.  
  
```  
virtual void OnAfterFloat();
```  
  
### <a name="remarks"></a>Примечания  
 Можно переопределить этот метод в производном классе, если вы хотите выполнить обработку после перемещается в область.  
  
##  <a name="onbeforechangeparent"></a>CPane::OnBeforeChangeParent  
 Вызывается инфраструктурой при родительской области.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pWndNewParent`  
 Указывает новый родительского окна.  
  
 [in] `bDelay`  
 `TRUE`Чтобы отложить глобальные настройки макета закрепления. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается инфраструктурой при намерении изменить вызванный области родительской области закрепления или оставить плавающим.  
  
 По умолчанию области не зарегистрирован закрепляемой области путем вызова `CDockSite::RemovePane`.  
  
##  <a name="onbeforedock"></a>CPane::OnBeforeDock  
 Вызывается инфраструктурой при Закрепить области.  
  
```  
virtual BOOL OnBeforeDock(
    CBasePane** ppDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`ppDockBar`  
 Задает область, в этой области, закрепление в.  
  
 [in] `lpRect`  
 Указывает прямоугольник закрепления.  
  
 [in] `dockMethod`  
 Задает метод закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если можно закрепить области. Если функция возвращает `FALSE`, закрепления операция будет прервана.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается инфраструктурой при Закрепить области. Если вы хотите выполнить обработку, прежде чем наконец закрепленной панели, можно переопределить этот метод в производном классе.  
  
##  <a name="onbeforefloat"></a>CPane::OnBeforeFloat  
 Вызывается инфраструктурой при область о число с плавающей запятой.  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectFloat`  
 Указывает положение и размер области, когда он находится в плавающем состоянии.  
  
 [in] `dockMethod`  
 Задает метод закрепления панели.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если можно перемещать области; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается инфраструктурой при посвящен область с плавающей запятой. Можно переопределить этот метод в производном классе, если вы хотите выполнить обработку перед области наконец перемещается.  
  
##  <a name="onpressclosebutton"></a>CPane::OnPressCloseButton  
 Вызывается платформой, когда пользователь нажимает кнопку Закрыть на панели заголовка.  
  
```  
virtual void OnPressCloseButton();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается инфраструктурой при нажатии клавиши **закрыть** кнопку на панели заголовка. Для получения уведомлений о **закрыть** события, можно переопределить этот метод в производном классе.  
  
##  <a name="onshowcontrolbarmenu"></a>CPane::OnShowControlBarMenu  
 Вызывается платформой непосредственно перед отображением меню особой панели.  
  
```  
virtual BOOL OnShowControlBarMenu(CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Указывает расположение меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если меню может отображаться; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Меню содержит несколько элементов, которые позволяют указать поведение панели, а именно: **плавающее**, **закрепления**, **Автоскрытие**, и **скрыть**. Это меню для всех панелей можно включить путем вызова [CDockingManager::EnableDockSiteMenu](../../mfc/reference/cdockingmanager-class.md#enabledocksitemenu).  
  
##  <a name="recalclayout"></a>CPane::RecalcLayout  
 Обновление сведений о макете для области.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Примечания  
 Если панель закреплена, этот метод обновляет виртуального прямоугольник для области, установив его размер текущий размер панели.  
  
 Если панель закреплена, этот метод уведомляет мини-родительского фрейма размер области до размера кадра мини. Платформа обеспечивает мини-кадра по крайней мере минимальный поддерживаемый размер для области ( [CPane::GetMinSize](#getminsize)) и при необходимости изменять размеры области.  
  
##  <a name="savestate"></a>CPane::SaveState  
 Сохраняет состояние области реестра.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Имя профиля.  
  
 [in] `nIndex`  
 Индекс профиля.  
  
 [in] `uiID`  
 Идентификатор области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если состояние была сохранена успешно. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда сохраняет состояние области в реестре. Переопределение `SaveState` в производном классе для хранения дополнительных сведений.  
  
 При переопределении этого метода также вызывать базовый метод и вернуть `FALSE` возвращает базовый метод `FALSE`.  
  
##  <a name="setactiveingroup"></a>CPane::SetActiveInGroup  
 Флаги панели как активный.  
  
```  
virtual void SetActiveInGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bActive`  
 Объект `BOOL` , указывающее, помечена ли области, как активные.  
  
### <a name="remarks"></a>Примечания  
 Когда показано закрепляемой области или выбрана кнопка автоматического скрытия, соответствующая область автоматического скрытия помечается как активный.  
  
 Внешний вид кнопка автоматического скрытия, связанный с панелью на основе двух факторов. Если область активна и `static``BOOL``CMFCAutoHideButton::m_bOverlappingTabs` — `TRUE`, платформа отображается кнопка автоматического скрытия значка и метки. Неактивные области платформа отображает значок автоматического скрытия.  
  
 Если `CMFCAutoHideButton::m_bOverlappingTabs` — `FALSE`, или если области не находится в группе, в качестве значка и метки платформа отображается кнопка автоматического скрытия.  
  
##  <a name="setborders"></a>CPane::SetBorders  
 Задает значения границы области.  
  
```  
void SetBorders(
    int cxLeft = 0,  
    int cyTop = 0,  
    int cxRight = 0,  
    int cyBottom = 0);  
  
void SetBorders(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `cxLeft`  
 Ширина в пикселях левой границы области.  
  
 [in] `cyTop`  
 Ширина в пикселях верхней границы области.  
  
 [in] `cxRight`  
 Ширина в пикселях правой границы области.  
  
 [in] `cyBottom`  
 Ширина в пикселях нижней границы области.  
  
 [in] `lpRect`  
 Объект [CRect](../../atl-mfc-shared/reference/crect-class.md) , содержащий ширину в пикселях каждого границы области.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для задается размер границы области.  
  
##  <a name="setclienthotspot"></a>CPane::SetClientHotSpot  
 Наборы *гиперобъект* для области.  
  
```  
void SetClientHotSpot(const CPoint& ptNew);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ptNew`  
 Объект `CPoint` объект, который указывает новый гиперобъект.  
  
### <a name="remarks"></a>Примечания  
 *Гиперобъект* является точкой на области, в которой пользователь выбирает и удерживает перемещение области. Активная область используется для гладкой анимации при перетаскивании из закрепленной позиции области.  
  
##  <a name="setdockstate"></a>CPane::SetDockState  
 Восстанавливает сведения о состоянии для области закрепления.  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDockManager`  
 Указатель на диспетчере закрепления для фрейма главного окна.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой для восстановления последних закрепления сведения о состоянии для области. Область сохраняет последние закрепления сведения о состоянии в [CPane::m_recentDockInfo](#m_recentdockinfo). Дополнительные сведения см. в разделе [CRecentDockSiteInfo класса](../../mfc/reference/crecentdocksiteinfo-class.md).  
  
 Можно также вызвать этот метод, чтобы задать состояние стыковки при загрузке панели информации из внешнего источника.  
  
##  <a name="setexclusiverowmode"></a>CPane::SetExclusiveRowMode  
 Включает или отключает режим монопольного строк.  
  
```  
virtual void SetExclusiveRowMode(BOOL bExclusive = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bExclusive`  
 `TRUE`Чтобы включить режим монопольного строк; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы включить или отключить режим монопольного строк. Когда панель находится в режиме монопольного строки, он не могут совместно использовать ту же строку с других панелей инструментов.  
  
 По умолчанию отключен режим монопольного строки имеют все панели инструментов и меню с включенным режимом exclusive строки.  
  
##  <a name="setminsize"></a>CPane::SetMinSize  
 Задает минимальный допустимый размер панели.  
  
```  
void SetMinSize(const CSize& size);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `size`  
 Объект `CSize` , содержащий минимальный поддерживаемый размер для области.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setvirtualrect"></a>CPane::SetVirtualRect  
 Наборы *виртуального прямоугольник* области.  
  
```  
void SetVirtualRect(
    const CRect& rect,  
    BOOL bMapToParent = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Объект `CRect` объект, который указывает на виртуальный прямоугольник, задаваемый.  
  
 [in] `bMapToParent`  
 Укажите `TRUE` Если `rect` содержит точки относительно родительского окна.  
  
### <a name="remarks"></a>Примечания  
 Объект *виртуального прямоугольник* сохраняет исходное положение панели при перемещении. Платформа можно использовать виртуальный прямоугольник для восстановления исходной позиции.  
  
 Не следует вызывать методы, которые связаны с виртуального прямоугольники, если вы перемещаете панелей программным способом.  
  
##  <a name="setminiframertc"></a>CPane::SetMiniFrameRTC  
 Задает сведения о классе среды выполнения для окна области по умолчанию.  
  
```  
void SetMiniFrameRTC(CRuntimeClass* pClass);
```  
  
### <a name="parameters"></a>Параметры  
 [in] [out]`pClass`  
 Указывает данные класса среды выполнения для окна области.  
  
### <a name="remarks"></a>Примечания  
 При плавающий область помещается [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) окна (области). Можно предоставить пользовательский `CPaneFrameWnd`-производный класс, который будет использоваться тогда, когда [CPane::CreateDefaultMiniframe](#createdefaultminiframe) вызывается.  
  
##  <a name="stretchpanedeferwndpos"></a>CPane::StretchPaneDeferWndPos  
 Увеличение области по вертикали или по горизонтали в зависимости от стиль закрепления.  
  
```  
virtual int StretchPaneDeferWndPos(
    int nStretchSize,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nStretchSize`  
 Размер в пикселях растянуть области. Отрицательное значение используйте для уменьшения области.  
  
 [in] `hdwp`  
 Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Фактический объем в пикселях, расширенная области.  
  
### <a name="remarks"></a>Примечания  
 При необходимости, этот метод изменяет `nStretchSize` чтобы убедиться, что области не превышает ограничения на размер. Эти ограничения создаются вызовом [CPane::GetAvailableStretchSize](#getavailablestretchsize) и [CPane::GetAvailableExpandSize](#getavailableexpandsize).  
  
##  <a name="toggleautohide"></a>CPane::ToggleAutoHide  
 Переключение режима автоматического скрытия.  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для переключения в режим автоматического скрытия. Для переключиться в режим автоматического скрытия области необходимо закрепить фрейма главного окна.  
  
##  <a name="undockpane"></a>CPane::UndockPane  
 Удаление области из сайта закрепления, по умолчанию ползунок или окна области, где он в настоящее время закреплен.  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bDelay`  
 Если `FALSE`, платформа вызывает функцию [CBasePane::AdjustDockingLayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout) для настройки макета закрепления.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы программно отменить закрепление панели.  
  
##  <a name="updatevirtualrect"></a>CPane::UpdateVirtualRect  
 Обновление виртуального прямоугольника.  
  
```  
void UpdateVirtualRect();  
void UpdateVirtualRect(CPoint ptOffset);  
  void UpdateVirtualRect(CSize sizeNew);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ptOffset`  
 Объект `CPoint` объект, который определяет смещение, который необходимо сдвинуть области.  
  
 [in] `sizeNew`  
 Объект `CSize` объект, который указывает новый размер для области.  
  
### <a name="remarks"></a>Примечания  
 Первая перегрузка задает виртуальный прямоугольник, используя текущее положение и размер области.  
  
 Вторая перегрузка сдвигает виртуального прямоугольник на величину, который задается параметром `ptOffset`.  
  
 Третья перегрузка задает виртуальный прямоугольник, используя текущую позицию и размер, который задается параметром `sizeNew`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CBasePane](../../mfc/reference/cbasepane-class.md)

