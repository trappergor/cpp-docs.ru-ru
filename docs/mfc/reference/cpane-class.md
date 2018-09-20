---
title: Класс CPane | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CPane [MFC], AdjustSizeImmediate
- CPane [MFC], AllocElements
- CPane [MFC], AllowShowOnPaneMenu
- CPane [MFC], CalcAvailableSize
- CPane [MFC], CalcInsideRect
- CPane [MFC], CalcRecentDockedRect
- CPane [MFC], CalcSize
- CPane [MFC], CanBeDocked
- CPane [MFC], CanBeTabbedDocument
- CPane [MFC], ConvertToTabbedDocument
- CPane [MFC], CopyState
- CPane [MFC], Create
- CPane [MFC], CreateDefaultMiniframe
- CPane [MFC], CreateEx
- CPane [MFC], DockByMouse
- CPane [MFC], DockPane
- CPane [MFC], DockPaneStandard
- CPane [MFC], DockToFrameWindow
- CPane [MFC], DoesAllowSiblingBars
- CPane [MFC], FloatPane
- CPane [MFC], GetAvailableExpandSize
- CPane [MFC], GetAvailableStretchSize
- CPane [MFC], GetBorders
- CPane [MFC], GetClientHotSpot
- CPane [MFC], GetDockSiteRow
- CPane [MFC], GetExclusiveRowMode
- CPane [MFC], GetHotSpot
- CPane [MFC], GetMinSize
- CPane [MFC], GetPaneName
- CPane [MFC], GetVirtualRect
- CPane [MFC], IsChangeState
- CPane [MFC], IsDragMode
- CPane [MFC], IsInFloatingMultiPaneFrameWnd
- CPane [MFC], IsLeftOf
- CPane [MFC], IsResizable
- CPane [MFC], IsTabbed
- CPane [MFC], LoadState
- CPane [MFC], MoveByAlignment
- CPane [MFC], MovePane
- CPane [MFC], OnAfterChangeParent
- CPane [MFC], OnBeforeChangeParent
- CPane [MFC], OnPressCloseButton
- CPane [MFC], OnShowControlBarMenu
- CPane [MFC], OnShowControlBarMenu
- CPane [MFC], RecalcLayout
- CPane [MFC], SaveState
- CPane [MFC], SetActiveInGroup
- CPane [MFC], SetBorders
- CPane [MFC], SetClientHotSpot
- CPane [MFC], SetDockState
- CPane [MFC], SetExclusiveRowMode
- CPane [MFC], SetMiniFrameRTC
- CPane [MFC], SetMinSize
- CPane [MFC], SetVirtualRect
- CPane [MFC], StretchPaneDeferWndPos
- CPane [MFC], ToggleAutoHide
- CPane [MFC], UndockPane
- CPane [MFC], UpdateVirtualRect
- CPane [MFC], OnAfterDock
- CPane [MFC], OnAfterFloat
- CPane [MFC], OnBeforeDock
- CPane [MFC], OnBeforeFloat
- CPane [MFC], m_bHandleMinSize
- CPane [MFC], m_recentDockInfo
ms.assetid: 5c651a64-3c79-4d94-9676-45f6402a6bc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 629e10d06a59b926604fad3b3a6e191fefcb71e7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384511"
---
# <a name="cpane-class"></a>CPane Class

`CPane` Класс — это расширение из [класс CControlBar](../../mfc/reference/ccontrolbar-class.md). При обновлении существующего проекта MFC, замените все вхождения `CControlBar` с `CPane`.

## <a name="syntax"></a>Синтаксис

```
class CPane : public CBasePane
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CPane::~CPane`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPane::AdjustSizeImmediate](#adjustsizeimmediate)|Сразу же повторно вычисляет макет области.|
|[CPane::AllocElements](#allocelements)|Выделяет память для внутреннего использования.|
|[CPane::AllowShowOnPaneMenu](#allowshowonpanemenu)|Указывает, отображается ли области в список областей для приложения созданных средой выполнения.|
|[CPane::CalcAvailableSize](#calcavailablesize)|Вычисляет разность размер текущего прямоугольника окна и указанного прямоугольника.|
|[CPane::CalcInsideRect](#calcinsiderect)|Вычисляет внутри прямоугольника, области, принимая во внимание границ и захват.|
|[CPane::CalcRecentDockedRect](#calcrecentdockedrect)|Вычисляет недавно закрепленной прямоугольника.|
|[CPane::CalcSize](#calcsize)|Вычисляет размер области.|
|[CPane::CanBeDocked](#canbedocked)|Определяет, ли области можно закрепить в области заданного базового.|
|[CPane::CanBeTabbedDocument](#canbetabbeddocument)|Определяет, может ли быть преобразован области документ с вкладками.|
|[CPane::ConvertToTabbedDocument](#converttotabbeddocument)|Преобразует закрепляемую панель документа с вкладками.|
|[CPane::CopyState](#copystate)|Копирует состояние области. (Переопределяет [CBasePane::CopyState](../../mfc/reference/cbasepane-class.md#copystate).)|
|[CPane::Create](#create)|Создает панель элементов управления и прикрепляет его к `CPane` объекта.|
|[CPane::CreateDefaultMiniframe](#createdefaultminiframe)|Создает для плавающую панель окна области.|
|[CPane::CreateEx](#createex)|Создает панель элементов управления и прикрепляет его к `CPane` объекта.|
|`CPane::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CPane::DockByMouse](#dockbymouse)|Закрепляет область с помощью мыши закрепление метод.|
|[CPane::DockPane](#dockpane)|Закрепляет область с плавающей запятой в базовый область.|
|[CPane::DockPaneStandard](#dockpanestandard)|Закрепляет область с помощью структуры (standard) закрепления.|
|[CPane::DockToFrameWindow](#docktoframewindow)|Закрепляет закрепляемую панель кадр. (Переопределяет `CBasePane::DockToFrameWindow`.)|
|[CPane::DoesAllowSiblingBars](#doesallowsiblingbars)|Указывает, можно закрепить ли другой области той же строке, место закрепления текущей области.|
|[CPane::FloatPane](#floatpane)|Смещает области.|
|[CPane::GetAvailableExpandSize](#getavailableexpandsize)|Возвращает сумму, в пикселях, которые могут расширить области.|
|[CPane::GetAvailableStretchSize](#getavailablestretchsize)|Возвращает сумму, в пикселях, которые можно сжать области.|
|[CPane::GetBorders](#getborders)|Возвращает ширину границы для области.|
|[CPane::GetClientHotSpot](#getclienthotspot)|Возвращает *гиперобъект* для области.|
|[CPane::GetDockSiteRow](#getdocksiterow)|Возвращает по строке закрепления, в котором закрепленной панели.|
|[CPane::GetExclusiveRowMode](#getexclusiverowmode)|Определяет, является ли область в режиме монопольного строки.|
|[CPane::GetHotSpot](#gethotspot)|Возвращает активную точку, которые хранятся в базовом `CMFCDragFrameImpl` объекта.|
|[CPane::GetMinSize](#getminsize)|Получает минимальный поддерживаемый размер для области.|
|[CPane::GetPaneName](#getpanename)|Извлекает заголовок области.|
|`CPane::GetResizeStep`|Используется внутренним образом.|
|`CPane::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CPane::GetVirtualRect](#getvirtualrect)|Извлекает *виртуального прямоугольник* области.|
|[CPane::IsChangeState](#ischangestate)|Области переместить, этот метод анализирует положение панели относительно других областей закрепление строк и окна и возвращает соответствующее значение AFX_CS_STATUS.|
|[CPane::IsDragMode](#isdragmode)|Указывает, перетаскиваемый ли области.|
|[CPane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Указывает, является ли область в окне фрейма несколькими областями. (Переопределяет `CBasePane::IsInFloatingMultiPaneFrameWnd`.)|
|[CPane::IsLeftOf](#isleftof)|Определяет, остается ли области объекта (или более поздней версии) заданного прямоугольника.|
|[CPane::IsResizable](#isresizable)|Определяет, возможно ли изменение размеров области. (Переопределяет [CBasePane::IsResizable](../../mfc/reference/cbasepane-class.md#isresizable).)|
|[CPane::IsTabbed](#istabbed)|Определяет, ли области был вставлен в элементе управления "Вкладка" окна с вкладками. (Переопределяет [CBasePane::IsTabbed](../../mfc/reference/cbasepane-class.md#istabbed).)|
|[CPane::LoadState](#loadstate)|Загружает состояние панели из реестра. (Переопределяет [CBasePane::LoadState](../../mfc/reference/cbasepane-class.md#loadstate).)|
|[CPane::MoveByAlignment](#movebyalignment)|Перемещение области и прямоугольника, виртуальный на заданную величину.|
|[CPane::MovePane](#movepane)|Перемещает область заданного прямоугольника.|
|[CPane::OnAfterChangeParent](#onafterchangeparent)|Вызывается платформой при изменении родительского элемента области.|
|[CPane::OnBeforeChangeParent](#onbeforechangeparent)|Вызывается платформой, когда родительской области.|
|[CPane::OnPressCloseButton](#onpressclosebutton)|Вызывается платформой, когда пользователь выбирает "Закрыть" в заголовке для области.|
|`CPane::OnProcessDblClk`|Используется внутренним образом.|
|[CPane::OnShowControlBarMenu](#onshowcontrolbarmenu)|Вызывается платформой непосредственно перед отображением меню особой панели.|
|[CPane::OnShowControlBarMenu](#onshowcontrolbarmenu)|Вызывается платформой непосредственно перед отображением меню особой панели.|
|`CPane::PrepareToDock`|Используется внутренним образом.|
|[CPane::RecalcLayout](#recalclayout)|Повторно вычисляет сведения о структуре для области. (Переопределяет [CBasePane::RecalcLayout](../../mfc/reference/cbasepane-class.md#recalclayout).)|
|[CPane::SaveState](#savestate)|Сохраняет состояние панели в реестр. (Переопределяет [CBasePane::SaveState](../../mfc/reference/cbasepane-class.md#savestate).)|
|[CPane::SetActiveInGroup](#setactiveingroup)|Флаги панели как активные.|
|[CPane::SetBorders](#setborders)|Задает значения границы области.|
|[CPane::SetClientHotSpot](#setclienthotspot)|Задает для области гиперобъекта.|
|[CPane::SetDockState](#setdockstate)|Восстанавливает сведения о состоянии для панели закрепления.|
|[CPane::SetExclusiveRowMode](#setexclusiverowmode)|Включает или отключает режим монопольного строки.|
|[CPane::SetMiniFrameRTC](#setminiframertc)|Задает сведения о классе среды выполнения для окна области по умолчанию.|
|[CPane::SetMinSize](#setminsize)|Задает минимальный поддерживаемый размер для области.|
|[CPane::SetVirtualRect](#setvirtualrect)|Наборы *виртуального прямоугольник* области.|
|[CPane::StretchPaneDeferWndPos](#stretchpanedeferwndpos)|Растягивает панель по вертикали или по горизонтали в зависимости от стиль закрепления.|
|[CPane::ToggleAutoHide](#toggleautohide)|Переключает режим автоматического скрытия.|
|[CPane::UndockPane](#undockpane)|Удаляет области из сайта закрепления, по умолчанию ползунок или окна области, где она в настоящее время закреплена. (Переопределяет [CBasePane::UndockPane](../../mfc/reference/cbasepane-class.md#undockpane).)|
|[CPane::UpdateVirtualRect](#updatevirtualrect)|Обновляет виртуального прямоугольника.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CPane::OnAfterDock](#onafterdock)|Вызывается платформой при область был закреплен.|
|[CPane::OnAfterFloat](#onafterfloat)|Вызывается платформой при стала плавающей панели.|
|[CPane::OnBeforeDock](#onbeforedock)|Вызывается платформой при области быть закреплено.|
|[CPane::OnBeforeFloat](#onbeforefloat)|Вызывается платформой при область быть оставить плавающим.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[CPane::m_bHandleMinSize](#m_bhandleminsize)|Позволяет согласованно обрабатывать минимальный размер для области.|
|[CPane::m_recentDockInfo](#m_recentdockinfo)|Содержит сведения о последней закрепления.|

## <a name="remarks"></a>Примечания

Как правило `CPane` не создаются экземпляры объектов напрямую. Если требуется область, которая имеет возможности закрепления, создайте производный объект от [CDockablePane](../../mfc/reference/cdockablepane-class.md). Если требуются функциональные возможности панели инструментов, создайте производный объект от [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).

При наследовании от класса `CPane`, его можно закрепить в [CDockSite](../../mfc/reference/cdocksite-class.md) и его можно оставить плавающим в [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxPane.h

##  <a name="adjustsizeimmediate"></a>  CPane::AdjustSizeImmediate

Сразу же повторно вычисляет макет области.

```
virtual void AdjustSizeImmediate(BOOL bRecalcLayout = TRUE);
```

### <a name="parameters"></a>Параметры

*bRecalcLayout*<br/>
[in] Значение TRUE, чтобы автоматически повторно рассчитать макет области; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод следует вызывайте при изменении макета области динамически. Например можно вызвать этот метод при можно скрывать или отображать кнопки на панели инструментов.

##  <a name="allocelements"></a>  CPane::AllocElements

Выделяет память для внутреннего использования.

```
BOOL AllocElements(
    int nElements,
    int cbElement);
```

### <a name="parameters"></a>Параметры

*nElements*<br/>
[in] Число элементов, для которого будут выделены ресурсы хранилища.

*cbElement*<br/>
[in] Размер в байтах, элемента.

### <a name="return-value"></a>Возвращаемое значение

Значение FALSE, если выделение памяти завершается сбоем; в противном случае — значение TRUE.

##  <a name="allowshowonpanemenu"></a>  CPane::AllowShowOnPaneMenu

Указывает, отображается ли области в список областей для приложения созданных средой выполнения.

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если область отображается в списке. в противном случае — значение FALSE. Базовая реализация всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Приложения, созданные с помощью мастера содержит пункт меню, в которой перечислены области, которые она содержит. Этот метод определяет, отображается ли область в списке.

##  <a name="calcavailablesize"></a>  CPane::CalcAvailableSize

Вычисляет разность размер текущего прямоугольника окна и указанного прямоугольника.

```
virtual CSize CalcAvailableSize(CRect rectRequired);
```

### <a name="parameters"></a>Параметры

*rectRequired*<br/>
[in] Прямоугольник, который требуется.

### <a name="return-value"></a>Возвращаемое значение

Разница в ширине и высоте между *rectRequired* и текущий прямоугольник окна.

##  <a name="calcinsiderect"></a>  CPane::CalcInsideRect

Вычисляет внутри прямоугольника, области, включая границы и захват.

```
void CalcInsideRect(
    CRect& rect,
    BOOL bHorz) const;
```

### <a name="parameters"></a>Параметры

*Rect*<br/>
[out] Содержит размер и смещение клиентской области панели.

*bHorz*<br/>
[in] Значение TRUE, если области его компонент ориентирован горизонтально. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой, когда ее нужно повторно рассчитать макет для панели. *Rect* параметр заполняется с размером и смещением клиентской области панели. Сюда входят, границы и захват.

##  <a name="calcrecentdockedrect"></a>  CPane::CalcRecentDockedRect

Вычисляет недавно закрепленной прямоугольника.

```
void CalcRecentDockedRect();
```

### <a name="remarks"></a>Примечания

Этот метод обновляет [CPane::m_recentDockInfo](#m_recentdockinfo).

##  <a name="calcsize"></a>  CPane::CalcSize

Вычисляет размер области.

```
virtual CSize CalcSize(BOOL bVertDock);
```

### <a name="parameters"></a>Параметры

*bVertDock*<br/>
[in] Значение TRUE, если области закрепляется по вертикали, и значение FALSE в противном случае.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию этот метод возвращает размер (0, 0).

### <a name="remarks"></a>Примечания

Производные классы должны переопределить этот метод.

##  <a name="canbedocked"></a>  CPane::CanBeDocked

Определяет, если области можно закрепить в области заданного базового.

```
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;
```

### <a name="parameters"></a>Параметры

*pDockBar*<br/>
[in] Указывает области, где в этой области быть закреплено.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если в этой области можно закрепить в указанной области закрепления. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод обычно вызывается платформой для определения ли панель можно закрепить в указанной области закрепления. Определить области могут быть закреплены, метод панели в настоящее время включить выравнивание закрепления.

Включить закрепление в различных сторон окна фрейма, вызвав [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).

##  <a name="canbetabbeddocument"></a>  CPane::CanBeTabbedDocument

Определяет, если область может быть преобразован в документ с вкладками.

```
virtual BOOL CanBeTabbedDocument() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если область может быть преобразован в документ с вкладками; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе и возвращает значение FALSE, если вы хотите запретить, преобразуемые в документ с вкладками в области. В меню положение окна будет отсутствовать документа с вкладками.

##  <a name="converttotabbeddocument"></a>  CPane::ConvertToTabbedDocument

Преобразует закрепляемую панель документа с вкладками.

```
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```

### <a name="parameters"></a>Параметры

*bActiveTabOnly*<br/>
[in] Не используется в `CPane::ConvertToTabbedDocument`.

### <a name="remarks"></a>Примечания

Документы с вкладками можно преобразовать только закрепляемых областей. Сведения см. в разделе [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).

##  <a name="copystate"></a>  CPane::CopyState

Копирует состояние области.

```
virtual void CopyState(CPane* pOrgBar);
```

### <a name="parameters"></a>Параметры

*pOrgBar*<br/>
[in] Указатель на область.

### <a name="remarks"></a>Примечания

Этот метод копирует состояние *pOrgBar* для текущей области.

##  <a name="create"></a>  CPane::Create

Создает панель элементов управления и прикрепляет его к [CPane](../../mfc/reference/cpane-class.md) объекта.

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

*lpszClassName*<br/>
[in] Задает имя класса Windows.

*dwStyle*<br/>
[in] Указывает атрибуты стиля окна. Дополнительные сведения см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*Rect*<br/>
[in] Задает первоначальный размер и положение *pParentWnd* окна в координатах клиентской области окна.

[in] [out] *pParentWnd* указывает родительское окно данной области.

*nID*<br/>
[in] Указывает идентификатор области.

*dwControlBarStyle*<br/>
[in] Задает стиль для области. Дополнительные сведения см. в разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).

[in] [out] *pContext* указывает контекст создания области.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если область создана успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод создает область Windows и присоединяет его к `CPane` объекта.

Если явно не инициализирован [CPane::m_recentDockInfo](#m_recentdockinfo) перед вызовом метода `Create`, параметр *rect* будет использоваться как прямоугольник, когда с плавающей запятой или закрепления панели.

##  <a name="createdefaultminiframe"></a>  CPane::CreateDefaultMiniframe

Создает для плавающую панель окна области.

```
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```

### <a name="parameters"></a>Параметры

*rectInitial*<br/>
[in] Задает первоначальный размер и положение окна минифрейма для создания, в экранных координатах.

### <a name="return-value"></a>Возвращаемое значение

Только что созданный окне.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой для создания окна области при плавающий область. Окно области может иметь тип [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) или типа [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md). Окна области с несколькими создается в том случае, если область имеет стиль AFX_CBRS_FLOAT_MULTI.

Сведения о классе среды выполнения для окна области хранится в `CPane::m_pMiniFrameRTC` член. Производный класс можно использовать для установки этого элемента в том случае, если вы решите создать настроенный окна.

##  <a name="createex"></a>  CPane::CreateEx

Создает панель элементов управления и прикрепляет его к [CPane](../../mfc/reference/cpane-class.md) объекта.

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

*dwStyleEx*<br/>
[in] Указывает атрибуты окно расширенного стиля. Дополнительные сведения см. в разделе [расширенные стили окна](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).

*lpszClassName*<br/>
[in] Задает имя класса Windows.

*dwStyle*<br/>
[in] Указывает атрибуты стиля окна. Дополнительные сведения см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*Rect*<br/>
[in] Задает первоначальный размер и положение *pParentWnd* окна в координатах клиентской области окна.

[in] [out] *pParentWnd* указывает родительское окно данной области.

*nID*<br/>
[in] Указывает идентификатор области.

*dwControlBarStyle*<br/>
[in] Задает стиль для области. Дополнительные сведения см. в разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).

[in] [out] *pContext* указывает создать контекст для области.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если область создана успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод создает область Windows и присоединяет его к `CPane` объекта.

Если явно не инициализирован [CPane::m_recentDockInfo](#m_recentdockinfo) перед вызовом метода `CreateEx`, параметр *rect* будет использоваться как прямоугольник, когда с плавающей запятой или закрепления панели.

##  <a name="dockbymouse"></a>  CPane::DockByMouse

Закрепляет область с помощью мыши.

```
virtual BOOL DockByMouse(CBasePane* pDockBar);
```

### <a name="parameters"></a>Параметры

*pDockBar*<br/>
[in] Указывает базовый панели, к которому закрепление этой панели.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если области была закреплена успешно; в противном случае — значение FALSE.

##  <a name="dockpane"></a>  CPane::DockPane

Закрепляет область с плавающей запятой в базовый область.

```
virtual BOOL DockPane(
    CBasePane* pDockBar,
    LPCRECT lpRect,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Параметры

[in] [out] *pDockBar* указывает панель, базовый закрепление этой панели на.

*lpRect*<br/>
[in] Указывает прямоугольник в базовый области, где в этой области быть закреплено.

*dockMethod*<br/>
[in] Задает метод закрепления для использования. Возможными значениями являются следующим образом:

|Параметр|Описание|
|------------|-----------------|
|DM_UNKNOWN|Инфраструктура использует этот параметр, если метод закрепления неизвестно. Области не хранит его последней позиции с плавающей запятой. Этот параметр позволяет программно закрепить в области, когда у вас нет для хранения последней позиции с плавающей запятой.|
|DM_MOUSE|Используется внутренним образом.|
|DM_DBL_CLICK|Этот параметр используется при двойном щелчке захвата. Области перемещен в его последней позиции закрепления. Незакрепленного области, дважды щелкнув области перемещен в его последней позиции с плавающей запятой.|
|DM_SHOW|Этот параметр можно использовать, чтобы программно закрепить на панели. Области хранит его последней позиции с плавающей запятой.|
|DM_RECT|Области, расположенной в регионе, который задается параметром *lpRect*.|
|DM_STANDARD|При использовании этого параметра, платформа рисует области как кадре структуры при ее перемещении.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если области была закреплена успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод закрепляет область области базовый, который задается параметром *pDockBar* параметра. Сначала необходимо включить закрепление путем вызова [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).

##  <a name="dockpanestandard"></a>  CPane::DockPaneStandard

Закрепляет область с помощью структуры (standard) закрепления.

```
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```

### <a name="parameters"></a>Параметры

*bWasDocked*<br/>
[in] Значение TRUE, если области был успешно закреплено; в противном случае — значение FALSE.

### <a name="return-value"></a>Возвращаемое значение

Этот метод всегда возвращает **это** указатель.

### <a name="remarks"></a>Примечания

Этот метод используется только для областей, которые являются производными от [класс CDockablePane](../../mfc/reference/cdockablepane-class.md). Дополнительные сведения см. в разделе [CDockablePane::DockPaneStandard](../../mfc/reference/cdockablepane-class.md#dockpanestandard).

##  <a name="docktoframewindow"></a>  CPane::DockToFrameWindow

Закрепляет закрепляемую панель кадр.

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

*dwAlignment*<br/>
[in] В части, которую требуется закрепить на панели, чтобы родительского фрейма.

*lpRect*<br/>
[in] Указанный размер.

*dwDockFlags*<br/>
[in] Игнорируется.

*pRelativeBar*<br/>
[in] Игнорируется.

*nRelativeIndex*<br/>
[in] Игнорируется.

*bOuterEdge*<br/>
[in] Если значение TRUE и существует являются другие закрепляемые панели на стороне, которые задаются параметром *dwAlignment*, области, расположенной за пределами области, ближе к краем родительского фрейма. Если значение равно FALSE, области закрепляется ближе относительно центральной части клиентской области.

### <a name="return-value"></a>Возвращаемое значение

Значение FALSE, если разделитель панели ( [класс CPaneDivider](../../mfc/reference/cpanedivider-class.md)) не может быть создан; в противном случае — значение TRUE.

### <a name="remarks"></a>Примечания

##  <a name="doesallowsiblingbars"></a>  CPane::DoesAllowSiblingBars

Указывает, можно закрепить ли другой области той же строке, место закрепления текущей области.

```
virtual BOOL DoesAllowSiblingBars() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если в этой области можно закрепить на другую панель, на той же строке само по себе; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Можно включить или отключить это поведение, вызвав [CPane::SetExclusiveRowMode](#setexclusiverowmode).

По умолчанию панелях инструментов находятся отключен режим монопольную и в строке меню был включен режим монопольную.

##  <a name="floatpane"></a>  CPane::FloatPane

Смещает области.

```
virtual BOOL FloatPane(
    CRect rectFloat,
    AFX_DOCK_METHOD dockMethod = DM_UNKNOWN,
    bool bShow = true);
```

### <a name="parameters"></a>Параметры

*rectFloat*<br/>
[in] Указывает расположение, в экранных координатах, для размещения области, когда она перемещается.

*dockMethod*<br/>
[in] Задает метод закрепления для использования при плавающий области. Список возможных значений см. в разделе [CPane::DockPane](#dockpane).

*bShow*<br/>
[in] Значение TRUE для отображения области при перемещенное; в противном случае — значение FALSE.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно было плавающий области или области невозможно оставить плавающим, так как [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat) возвращает FALSE, в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Вызовите этот метод для плавающей панели в позиции, который задается параметром *rectFloat* параметра. Этот метод автоматически создает родительского окна области для области.

##  <a name="getavailableexpandsize"></a>  CPane::GetAvailableExpandSize

Возвращает сумму, в пикселях, которые могут расширить области.

```
virtual int GetAvailableExpandSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если панель закреплена горизонтально, возвращаемое значение является доступную ширину; в противном случае возвращает значение высоты.

### <a name="remarks"></a>Примечания

##  <a name="getavailablestretchsize"></a>  CPane::GetAvailableStretchSize

Возвращает сумму, в пикселях, которые можно сжать области.

```
virtual int GetAvailableStretchSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер в пикселях, которые можно сжать области. Если панель закреплена горизонтально, эта сумма представляет доступную ширину; в противном случае это доступной высоте.

### <a name="remarks"></a>Примечания

Доступный размер stretch вычисляется путем вычитания минимально допустимого размера для панели ( [CPane::GetMinSize](#getminsize)) из текущего размера ( [CWnd::GetWindowRect](../../mfc/reference/cwnd-class.md#getwindowrect)).

##  <a name="getborders"></a>  CPane::GetBorders

Возвращает ширину границы для области.

```
CRect GetBorders() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CRect](../../atl-mfc-shared/reference/crect-class.md) , содержащий Текущая ширина в пикселях каждой части панели. Например, значение `left` членом `CRect` объект является Ширина левой границы.

### <a name="remarks"></a>Примечания

Чтобы задать размер границы, вызовите [CPane::SetBorders](#setborders).

##  <a name="getclienthotspot"></a>  CPane::GetClientHotSpot

Возвращает *гиперобъект* для области.

```
CPoint GetClientHotSpot() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

*Гиперобъект* — это точка в области, пользователь выбирает и удерживает чтобы поместить область. Активная область используется для создавать плавную анимацию при перемещении области из закрепленной позиции.

##  <a name="getdocksiterow"></a>  CPane::GetDockSiteRow

Возвращает строку, dock ( [класс CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)) в закрепленной панели.

```
CDockingPanesRow* GetDockSiteRow() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CDockingPanesRow`*, указывающий строку закрепления, в котором закрепленной панели, или значение NULL, если области не закреплено.

##  <a name="getexclusiverowmode"></a>  CPane::GetExclusiveRowMode

Определяет, является ли в режиме монопольного строки.

```
virtual BOOL GetExclusiveRowMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если области находится в режиме монопольного строки; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Дополнительные сведения о режиме монопольного строки, см. в разделе [CPane::SetExclusiveRowMode](#setexclusiverowmode).

##  <a name="gethotspot"></a>  CPane::GetHotSpot

Возвращает активную точку, которые хранятся в базовом `CMFCDragFrameImpl` объекта.

```
CPoint GetHotSpot() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

`CPane` Класс содержит `CMFCDragFrameImpl` объекта, `m_dragFrameImpl`, который отвечает за рисование прямоугольника, который отображается, когда пользователь перемещает панель в стандартном режиме закрепления. Активная точка используется для рисования прямоугольника по отношению к текущей позиции мыши при перемещении области.

##  <a name="getminsize"></a>  CPane::GetMinSize

Получает минимальный поддерживаемый размер для области.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Параметры

*size*<br/>
[out] Объект `CSize` объект, который заполняется минимально допустимого размера.

### <a name="remarks"></a>Примечания

##  <a name="getpanename"></a>  CPane::GetPaneName

Извлекает заголовок области.

```
virtual void GetPaneName(CString& strName) const;
```

### <a name="parameters"></a>Параметры

*strName*<br/>
[out] Объект `CString` объект, который заполняется имя заголовка.

### <a name="remarks"></a>Примечания

Заголовок панели отображается в области заголовка при области закрепленными или с плавающей запятой. Если область является частью группы с вкладками, заголовок отображается в области вкладок. Если панель в режиме автоматического скрытия, название будет отображаться на `CMFCAutoHideButton`.

##  <a name="getvirtualrect"></a>  CPane::GetVirtualRect

Извлекает *виртуального прямоугольник* области.

```
void GetVirtualRect(CRect& rectVirtual) const;
```

### <a name="parameters"></a>Параметры

*rectVirtual*<br/>
[out] Объект `CRect` объект, который заполняется виртуального прямоугольника.

### <a name="remarks"></a>Примечания

При перемещении области framework хранит исходной позиции области в виртуальный прямоугольник. Виртуальный прямоугольник может использоваться платформой для восстановления исходной позиции области.

Не следует вызывать методы, которые связаны с виртуального прямоугольники, если при перемещении области программным образом.

##  <a name="ischangestate"></a>  CPane::IsChangeState

Области переместить, этот метод анализирует их положение относительно других областей закрепление строк и окна и возвращает соответствующее значение AFX_CS_STATUS.

```
virtual AFX_CS_STATUS IsChangeState(
    int nOffset,
    CBasePane** ppTargetBar) const;
```

### <a name="parameters"></a>Параметры

*nOffset*<br/>
[in] Задает чувствительность закрепления. Например, область, в которой перемещается в *nOffset* закрепляется пикселов из строки закрепления.

*ppTargetBar*<br/>
[in] При возвращении метода *ppTargetBar* содержит указатель на объект, к которому должно быть закреплено текущей области или значение NULL, если закрепление не происходит.

### <a name="return-value"></a>Возвращаемое значение

Одно из следующих значений AFX_CS_STATUS:

|Значение|Описание|
|-----------|-----------------|
|CS_NOTHING|Область не рядом с сайта закрепления. Платформа не закрепление области.|
|CS_DOCK_IMMEDIATELY|Области находится на сайте закрепления и стиль DT_IMMEDIATE включен. Платформа немедленно закрепляет область.|
|CS_DELAY_DOCK|Область — на сайте закрепления, края главного фрейма или другую панель закрепления. Платформа закрепляет область, когда пользователь отпускает перемещения.|
|CS_DELAY_DOCK_TO_TAB|Область — на сайте закрепления, в которой эта панель быть закреплено в окно с вкладками. Это происходит, когда область — заголовок другого закрепляемой области или по области вкладок области с вкладками. Платформа закрепляет область, когда пользователь отпускает перемещения.|

##  <a name="isdragmode"></a>  CPane::IsDragMode

Определяет, перемещается ли области.

```
virtual BOOL IsDragMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если перемещается области; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="isinfloatingmultipaneframewnd"></a>  CPane::IsInFloatingMultiPaneFrameWnd

Указывает, является ли область в окне фрейма несколькими областями ( [класс CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md)).

```
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если панель в окне фрейма несколькими областями; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

В окне фрейма несколькими областями может перемещаться только закрепляемых областей. Таким образом `CPane::IsInFloatingMultiPaneFrameWnd` всегда возвращает значение FALSE.

##  <a name="isleftof"></a>  CPane::IsLeftOf

Определяет, остается ли области объекта (или более поздней версии) заданного прямоугольника.

```
bool IsLeftOf(
    CRect rect,
    bool bWindowRect = true) const;
```

### <a name="parameters"></a>Параметры

*Rect*<br/>
[in] Объект `CRect` объект, используемый для сравнения.

*bWindowRect*<br/>
[in] Если значение равно TRUE, *rect* предполагается, что содержит координаты экрана; Если значение равно FALSE, *rect* предполагается, что содержит в координатах клиентской области окна.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Если панель закреплена горизонтально, этот метод проверяет ли его расположение хорошо провести остаток *rect*. В противном случае этот метод проверяет, является ли расположение выше *rect*.

##  <a name="isresizable"></a>  CPane::IsResizable

Указывает, является ли области можно изменять.

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если области регулируемого размера; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Base `CPane` объектов не изменяется.

В диспетчере закрепления использует переменного размера флаг для определения области макета. Не изменять размер панелей всегда находятся в внешние края родительского фрейма.

Не изменять размер панелей не могут размещаться в закрепление контейнеры.

##  <a name="istabbed"></a>  CPane::IsTabbed

Определяет, ли области вставлен в элемент управления "Вкладка" окна с вкладками.

```
virtual BOOL IsTabbed() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если области представлено в форме вкладок; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Состояние с вкладками будет обрабатываться отдельно с плавающей запятой, закреплено и автоматического скрытия состояния.

##  <a name="loadstate"></a>  CPane::LoadState

Загружает состояние панели из реестра.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Имя профиля.

*nIndex*<br/>
[in] Индекс профиля.

*uiID*<br/>
[in] Идентификатор области.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если состояние панели был загружен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод, чтобы загрузить состояние панели из реестра. Переопределение в производном классе, чтобы загрузить дополнительные сведения, сохраненные с [CPane::SaveState](#savestate).

При переопределении этого метода также вызываться базовый метод и возвращает значение FALSE, если базовый метод возвращает значение FALSE.

##  <a name="m_bhandleminsize"></a>  CPane::m_bHandleMinSize

Позволяет согласованно обрабатывать размеры минимальное области.

```
AFX_IMPORT_DATA static BOOL m_bHandleMinSize;
```

### <a name="remarks"></a>Примечания

Если один или несколько закрепляемых панелей в приложении переопределить `GetMinSize`, или если приложение вызывает `SetMinSize`, может потребоваться присвоить статический элемент значение TRUE, чтобы включить платформу постоянно обрабатывать способ изменения размеров для панелей.

Если это значение имеет значение TRUE, обрезаются все панели, размер которого следует сократить ниже их минимальный размер, не растягивается. Так как инфраструктура использует области окон в целях изменения размера панели, не изменяйте размер области окна для закрепляемых панелей в том случае, если это значение имеет значение TRUE.

##  <a name="m_recentdockinfo"></a>  CPane::m_recentDockInfo

Содержит сведения о последней закрепления.

```
CRecentDockSiteInfo m_recentDockInfo;
```

### <a name="remarks"></a>Примечания

Framework хранит данные состояния последней закрепления для области в этом члене.

##  <a name="movebyalignment"></a>  CPane::MoveByAlignment

Перемещение области и прямоугольника, виртуальный на заданную величину.

```
BOOL MoveByAlignment(
    DWORD dwAlignment,
    int nOffset);
```

### <a name="parameters"></a>Параметры

*dwAlignment*<br/>
[in] Задает выравнивание панели.

*nOffset*<br/>
[in] Размер в пикселях, которую следует переместить области и прямоугольника, виртуальный.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

*dwAlignment* может быть любым из следующих значений:

|Значение|Описание|
|-----------|-----------------|
|CBRS_ALIGN_TOP|Позволяет области быть закреплено в верхнюю часть клиентской области окна фрейма.|
|CBRS_ALIGN_BOTTOM|Позволяет области быть закреплено в нижнюю часть клиентской области окна фрейма.|
|CBRS_ALIGN_LEFT|Позволяет области быть закреплено в левую часть клиентской области окна фрейма.|
|CBRS_ALIGN_RIGHT|Позволяет области быть закреплено правую часть клиентской области окна фрейма.|
|CBRS_ALIGN_ANY|Включает области, чтобы закрепить с любой стороны клиентской области окна фрейма.|

Если *dwAlignment* содержит флаг CBRS_ALIGN_LEFT или CBRS_ALIGN_RIGHT, области и прямоугольника виртуального перемещаются по горизонтали; в противном случае — значение *dwAlignment* содержит CBRS_ALIGN_TOP или CBRS_ALIGN Флаг ни_жние, области и прямоугольника виртуального перемещаются по вертикали.

##  <a name="movepane"></a>  CPane::MovePane

Перемещает область заданного прямоугольника.

```
virtual CSize MovePane(
    CRect rectNew,
    BOOL bForceMove,
    HDWP& hdwp);
```

### <a name="parameters"></a>Параметры

*rectNew*<br/>
[in] Указывает новый прямоугольник для области.

*bForceMove*<br/>
[in] Если значение равно TRUE, этот метод игнорирует Минимальный допустимый размер области ( [CPane::GetMinSize](#getminsize)); в противном случае настраивается области, при необходимости, чтобы убедиться, что он не меньше минимально допустимого размера.

*hdwp*<br/>
[in] Не используется.

### <a name="return-value"></a>Возвращаемое значение

Объект `CSize` , содержащий ширину и высоту в различия между новым и старым прямоугольников (старый прямоугольник - *rectNew*).

### <a name="remarks"></a>Примечания

Этот метод используется только для закрепляемых областей.

##  <a name="onafterchangeparent"></a>  CPane::OnAfterChangeParent

Вызывается платформой при изменении родительского элемента области.

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>Параметры

[in] [out] *pWndOldParent* предыдущего родительского окна области.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой при изменении родительской области из-за операции закрепления или с плавающей запятой.

##  <a name="onafterdock"></a>  CPane::OnAfterDock

Вызывается платформой при область был закреплен.

```
virtual void OnAfterDock(
    CBasePane* pBar,
    LPCRECT lpRect,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
[in] Этот параметр не используется.

*lpRect*<br/>
[in] Этот параметр не используется.

*dockMethod*<br/>
[in] Этот параметр не используется.

##  <a name="onafterfloat"></a>  CPane::OnAfterFloat

Вызвано структурой после отображается область.

```
virtual void OnAfterFloat();
```

### <a name="remarks"></a>Примечания

Если вы хотите выполнять любую обработку после отображается панель, можно переопределить этот метод в производном классе.

##  <a name="onbeforechangeparent"></a>  CPane::OnBeforeChangeParent

Вызывается платформой, когда родительской области.

```
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,
    BOOL bDelay = FALSE);
```

### <a name="parameters"></a>Параметры

[in] [out] *pWndNewParent* указывает нового родительского окна.

*bDelay*<br/>
[in] Значение TRUE, чтобы отложить глобальные настройки макета закрепления. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой при родительской области должно произойти изменение, так как производится области закрепления или перемещению к последующей.

По умолчанию области не зарегистрирован закрепляемой области, вызвав `CDockSite::RemovePane`.

##  <a name="onbeforedock"></a>  CPane::OnBeforeDock

Вызывается платформой при области закрепления.

```
virtual BOOL OnBeforeDock(
    CBasePane** ppDockBar,
    LPCRECT lpRect,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Параметры

[in] [out] *ppDockBar* указывает панель, на которой эта панель закрепление в.

*lpRect*<br/>
[in] Указывает прямоугольник закрепления.

*dockMethod*<br/>
[in] Задает метод закрепления.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если область может быть закреплено. Если функция возвращает значение FALSE, закрепления операция будет прервана.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой при области быть закреплено. Если вы хотите выполнять любую обработку, прежде чем панель закрепляется и, наконец, можно переопределить этот метод в производном классе.

##  <a name="onbeforefloat"></a>  CPane::OnBeforeFloat

Вызывается платформой, когда область будет о число с плавающей запятой.

```
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Параметры

*rectFloat*<br/>
[in] Указывает положение и размер области, когда он находится в плавающем состоянии.

*dockMethod*<br/>
[in] Задает метод закрепления панели.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если можно перемещать области; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой, когда область будет о число с плавающей запятой. Если вы хотите выполнять любую обработку, прежде чем наконец расположенном в области, можно переопределить этот метод в производном классе.

##  <a name="onpressclosebutton"></a>  CPane::OnPressCloseButton

Вызывается платформой, когда пользователь нажимает "Закрыть" в заголовке для области.

```
virtual void OnPressCloseButton();
```

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой, когда пользователь нажимает **закрыть** кнопку на панели заголовка. Для получения уведомлений о **закрыть** событий, можно переопределить этот метод в производном классе.

##  <a name="onshowcontrolbarmenu"></a>  CPane::OnShowControlBarMenu

Вызывается платформой непосредственно перед отображением меню особой панели.

```
virtual BOOL OnShowControlBarMenu(CPoint point);
```

### <a name="parameters"></a>Параметры

*точка*<br/>
[in] Указывает расположение меню.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если можно отобразить меню; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Меню содержит несколько элементов, которые позволяют указать поведение области, а именно: **плавающее**, **закрепления**, **Автоскрытие**, и **скрыть**. Вы можете включить это меню для всех панелей путем вызова [CDockingManager::EnableDockSiteMenu](../../mfc/reference/cdockingmanager-class.md#enabledocksitemenu).

##  <a name="recalclayout"></a>  CPane::RecalcLayout

Повторно вычисляет сведения о структуре для области.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Примечания

Если панель закреплена, этот метод обновляет виртуального прямоугольник для области, установив его размер текущий размер области.

Если область является перемещаемой, этот метод уведомляет мини-родительского фрейма изменяет размер панели, чтобы размер мини-рамки. Инфраструктура гарантирует, что области не меньше минимально допустимого размера для панели ( [CPane::GetMinSize](#getminsize)) и изменяет размер области, при необходимости.

##  <a name="savestate"></a>  CPane::SaveState

Сохраняет состояние панели в реестр.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Имя профиля.

*nIndex*<br/>
[in] Индекс профиля.

*uiID*<br/>
[in] Идентификатор области.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если состояние было сохранено успешно. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой при сохранении состояния области реестра. Переопределить `SaveState` в производном классе для хранения дополнительной информации.

При переопределении этого метода также вызываться базовый метод и возвращает значение FALSE, если базовый метод возвращает значение FALSE.

##  <a name="setactiveingroup"></a>  CPane::SetActiveInGroup

Флаги панели как активные.

```
virtual void SetActiveInGroup(BOOL bActive);
```

### <a name="parameters"></a>Параметры

*bActive*<br/>
[in] Логическое значение, указывающее ли области помечен как активный.

### <a name="remarks"></a>Примечания

Когда отображается закрепляемую панель или нажатия кнопки автоматического скрытия, соответствующую область автоматического скрытия помечается как активный.

Внешний вид кнопки автоматического скрытия, связанный с панелью зависит от двух факторов. Если область является активным и `static BOOL CMFCAutoHideButton::m_bOverlappingTabs` имеет значение TRUE, отображает framework, кнопку автоматического скрытия как значок и метку. Для неактивного области платформа отображает только значок автоматического скрытия.

Если `CMFCAutoHideButton::m_bOverlappingTabs` имеет значение FALSE, или если области не находится в группе, платформа отображает кнопку автоматического скрытия как значок и метку.

##  <a name="setborders"></a>  CPane::SetBorders

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

*cxLeft*<br/>
[in] Задает ширину в пикселях левой границы области.

*cyTop*<br/>
[in] Задает ширину в пикселях, верхней границы области.

*cxRight*<br/>
[in] Задает ширину в пикселях правой границы области.

*cyBottom*<br/>
[in] Задает ширину в пикселях, нижней границы области.

*lpRect*<br/>
[in] Объект [CRect](../../atl-mfc-shared/reference/crect-class.md) , содержащий ширину в пикселях каждого границы области.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы задать размеры границы области.

##  <a name="setclienthotspot"></a>  CPane::SetClientHotSpot

Наборы *гиперобъект* для области.

```
void SetClientHotSpot(const CPoint& ptNew);
```

### <a name="parameters"></a>Параметры

*ptNew*<br/>
[in] Объект `CPoint` , указывающий новую активную зону.

### <a name="remarks"></a>Примечания

*Гиперобъект* — это точка в области, пользователь выбирает и удерживает чтобы поместить область. Активная область используется для создавать плавную анимацию при перетаскивании из закрепленного положения области.

##  <a name="setdockstate"></a>  CPane::SetDockState

Восстанавливает сведения о состоянии для панели закрепления.

```
virtual void SetDockState(CDockingManager* pDockManager);
```

### <a name="parameters"></a>Параметры

*pDockManager*<br/>
[in] Указатель на диспетчере закрепления для окна главного фрейма.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой для восстановления последних закрепления сведения о состоянии для панели. Область хранит актуальные сведения состоянии закрепления в [CPane::m_recentDockInfo](#m_recentdockinfo). Дополнительные сведения см. в разделе [класс CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md).

Можно также вызвать этот метод для задания состояние закрепления при загрузке панели сведения из внешнего источника.

##  <a name="setexclusiverowmode"></a>  CPane::SetExclusiveRowMode

Включает или отключает режим монопольного строки.

```
virtual void SetExclusiveRowMode(BOOL bExclusive = TRUE);
```

### <a name="parameters"></a>Параметры

*bExclusive*<br/>
[in] Значение TRUE, чтобы включить режим монопольную; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод используется для включения или отключения режима монопольного строки. Если панель находится в режиме монопольного строки, он не могут совместно использовать ту же строку с панели инструментов.

По умолчанию отключен режим монопольную имеют все панели инструментов и меню был включен режим монопольную.

##  <a name="setminsize"></a>  CPane::SetMinSize

Задает минимальный поддерживаемый размер для области.

```
void SetMinSize(const CSize& size);
```

### <a name="parameters"></a>Параметры

*size*<br/>
[in] Объект `CSize` , содержащий минимальный поддерживаемый размер для области.

### <a name="remarks"></a>Примечания

##  <a name="setvirtualrect"></a>  CPane::SetVirtualRect

Наборы *виртуального прямоугольник* области.

```
void SetVirtualRect(
    const CRect& rect,
    BOOL bMapToParent = TRUE);
```

### <a name="parameters"></a>Параметры

*Rect*<br/>
[in] Объект `CRect` объект, который указывает на виртуальный прямоугольник, задаваемый.

*bMapToParent*<br/>
[in] Укажите значение TRUE, если *rect* содержит точки относительно родительского окна.

### <a name="remarks"></a>Примечания

Объект *виртуального прямоугольник* сохраняет исходное положение области, при перемещении. Виртуальный прямоугольник может использоваться платформой для восстановления исходной позиции.

Не следует вызывать методы, которые связаны с виртуального прямоугольники, если при перемещении области программным образом.

##  <a name="setminiframertc"></a>  CPane::SetMiniFrameRTC

Задает сведения о классе среды выполнения для окна области по умолчанию.

```
void SetMiniFrameRTC(CRuntimeClass* pClass);
```

### <a name="parameters"></a>Параметры

[in] [out] *pClass* указывает сведения о классе среды выполнения для окна области.

### <a name="remarks"></a>Примечания

При область перемещается, он помещается [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) окна (области). Можно указать пользовательское `CPaneFrameWnd`-производный класс, который будет использовать, когда [CPane::CreateDefaultMiniframe](#createdefaultminiframe) вызывается.

##  <a name="stretchpanedeferwndpos"></a>  CPane::StretchPaneDeferWndPos

Растягивает панель по вертикали или по горизонтали в зависимости от стиль закрепления.

```
virtual int StretchPaneDeferWndPos(
    int nStretchSize,
    HDWP& hdwp);
```

### <a name="parameters"></a>Параметры

*nStretchSize*<br/>
[in] Размер в пикселях для растяжения области. Уменьшение размера области, используйте отрицательное значение.

*hdwp*<br/>
[in] Не используется.

### <a name="return-value"></a>Возвращаемое значение

Фактический объем в пикселях, что области была перенесена.

### <a name="remarks"></a>Примечания

При необходимости, этот метод изменяет *nStretchSize* чтобы убедиться, что области не превышает ограничения размера. Эти ограничения можно получить путем вызова [CPane::GetAvailableStretchSize](#getavailablestretchsize) и [CPane::GetAvailableExpandSize](#getavailableexpandsize).

##  <a name="toggleautohide"></a>  CPane::ToggleAutoHide

Переключает режим автоматического скрытия.

```
virtual void ToggleAutoHide();
```

### <a name="remarks"></a>Примечания

Вызовите этот метод для переключения в режим автоматического скрытия. Для переключения в режим автоматического скрытия необходимо закрепить панель фрейма главного окна.

##  <a name="undockpane"></a>  CPane::UndockPane

Удаляет области из сайта закрепления, по умолчанию ползунок или окна области, где она в настоящее время закреплена.

```
virtual void UndockPane(BOOL bDelay = FALSE);
```

### <a name="parameters"></a>Параметры

*bDelay*<br/>
[in] Если значение равно FALSE, платформа вызывает [CBasePane::AdjustDockingLayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout) для настройки макета закрепления.

### <a name="remarks"></a>Примечания

Этот метод позволяет программно открепить панель.

##  <a name="updatevirtualrect"></a>  CPane::UpdateVirtualRect

Обновляет виртуального прямоугольника.

```
void UpdateVirtualRect();
void UpdateVirtualRect(CPoint ptOffset);
  void UpdateVirtualRect(CSize sizeNew);
```

### <a name="parameters"></a>Параметры

*ptOffset*<br/>
[in] Объект `CPoint` , указывающий смещение, на который необходимо сдвинуть области.

*sizeNew*<br/>
[in] Объект `CSize` объект, который указывает новый размер для области.

### <a name="remarks"></a>Примечания

Первая перегрузка задает прямоугольник, виртуальной, используя текущее положение и размер области.

Вторая перегрузка сдвигает виртуального прямоугольник на величину, который задается параметром *ptOffset*.

Третья перегрузка задает виртуальный прямоугольника с помощью текущей позиции и размера, который задается параметром *sizeNew*.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CBasePane](../../mfc/reference/cbasepane-class.md)
