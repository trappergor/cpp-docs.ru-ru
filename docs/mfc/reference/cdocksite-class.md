---
title: CDockSite Class
ms.date: 10/18/2018
f1_keywords:
- CDockSite
- AFXDOCKSITE/CDockSite
- AFXDOCKSITE/CDockSite::AddRow
- AFXDOCKSITE/CDockSite::AdjustDockingLayout
- AFXDOCKSITE/CDockSite::AdjustLayout
- AFXDOCKSITE/CDockSite::AlignDockSite
- AFXDOCKSITE/CDockSite::CalcFixedLayout
- AFXDOCKSITE/CDockSite::CanAcceptPane
- AFXDOCKSITE/CDockSite::CreateEx
- AFXDOCKSITE/CDockSite::CreateRow
- AFXDOCKSITE/CDockSite::DockPane
- AFXDOCKSITE/CDockSite::DoesAllowDynInsertBefore
- AFXDOCKSITE/CDockSite::FindRowIndex
- AFXDOCKSITE/CDockSite::FixupVirtualRects
- AFXDOCKSITE/CDockSite::GetDockSiteID
- AFXDOCKSITE/CDockSite::GetDockSiteRowsList
- AFXDOCKSITE/CDockSite::IsAccessibilityCompatible
- AFXDOCKSITE/CDockSite::IsDragMode
- AFXDOCKSITE/CDockSite::IsLastRow
- AFXDOCKSITE/CDockSite::IsRectWithinDockSite
- AFXDOCKSITE/CDockSite::IsResizable
- AFXDOCKSITE/CDockSite::MovePane
- AFXDOCKSITE/CDockSite::OnInsertRow
- AFXDOCKSITE/CDockSite::OnRemoveRow
- AFXDOCKSITE/CDockSite::OnResizeRow
- AFXDOCKSITE/CDockSite::OnSetWindowPos
- AFXDOCKSITE/CDockSite::OnShowRow
- AFXDOCKSITE/CDockSite::OnSizeParent
- AFXDOCKSITE/CDockSite::PaneFromPoint
- AFXDOCKSITE/CDockSite::DockPaneLeftOf
- AFXDOCKSITE/CDockSite::FindPaneByID
- AFXDOCKSITE/CDockSite::GetPaneList
- AFXDOCKSITE/CDockSite::RectSideFromPoint
- AFXDOCKSITE/CDockSite::RemovePane
- AFXDOCKSITE/CDockSite::RemoveRow
- AFXDOCKSITE/CDockSite::ReplacePane
- AFXDOCKSITE/CDockSite::RepositionPanes
- AFXDOCKSITE/CDockSite::ResizeDockSite
- AFXDOCKSITE/CDockSite::ResizeRow
- AFXDOCKSITE/CDockSite::ShowPane
- AFXDOCKSITE/CDockSite::ShowRow
- AFXDOCKSITE/CDockSite::SwapRows
helpviewer_keywords:
- CDockSite [MFC], AddRow
- CDockSite [MFC], AdjustDockingLayout
- CDockSite [MFC], AdjustLayout
- CDockSite [MFC], AlignDockSite
- CDockSite [MFC], CalcFixedLayout
- CDockSite [MFC], CanAcceptPane
- CDockSite [MFC], CreateEx
- CDockSite [MFC], CreateRow
- CDockSite [MFC], DockPane
- CDockSite [MFC], DoesAllowDynInsertBefore
- CDockSite [MFC], FindRowIndex
- CDockSite [MFC], FixupVirtualRects
- CDockSite [MFC], GetDockSiteID
- CDockSite [MFC], GetDockSiteRowsList
- CDockSite [MFC], IsAccessibilityCompatible
- CDockSite [MFC], IsDragMode
- CDockSite [MFC], IsLastRow
- CDockSite [MFC], IsRectWithinDockSite
- CDockSite [MFC], IsResizable
- CDockSite [MFC], MovePane
- CDockSite [MFC], OnInsertRow
- CDockSite [MFC], OnRemoveRow
- CDockSite [MFC], OnResizeRow
- CDockSite [MFC], OnSetWindowPos
- CDockSite [MFC], OnShowRow
- CDockSite [MFC], OnSizeParent
- CDockSite [MFC], PaneFromPoint
- CDockSite [MFC], DockPaneLeftOf
- CDockSite [MFC], FindPaneByID
- CDockSite [MFC], GetPaneList
- CDockSite [MFC], RectSideFromPoint
- CDockSite [MFC], RemovePane
- CDockSite [MFC], RemoveRow
- CDockSite [MFC], ReplacePane
- CDockSite [MFC], RepositionPanes
- CDockSite [MFC], ResizeDockSite
- CDockSite [MFC], ResizeRow
- CDockSite [MFC], ShowPane
- CDockSite [MFC], ShowRow
- CDockSite [MFC], SwapRows
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
ms.openlocfilehash: 9c154fe621fb88a6dc96a9835fae95c4b86763de
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866197"
---
# <a name="cdocksite-class"></a>CDockSite Class

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

Предоставляет функциональные возможности для упорядочения областей, которые являются производными от [CPane Class](../../mfc/reference/cpane-class.md) , в наборы строк.

## <a name="syntax"></a>Синтаксис

```
class CDockSite: public CBasePane
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CDockSite:: AddRow](#addrow)||
|[CDockSite:: Аджустдоккинглайаут](#adjustdockinglayout)|(Переопределяет [CBasePane:: аджустдоккинглайаут](../../mfc/reference/cbasepane-class.md#adjustdockinglayout).)|
|[CDockSite:: Аджустлайаут](#adjustlayout)|(Переопределяет [CBasePane:: аджустлайаут](../../mfc/reference/cbasepane-class.md#adjustlayout).)|
|[CDockSite::AlignDockSite](#aligndocksite)||
|[CDockSite:: Калкфикседлайаут](#calcfixedlayout)|(Переопределяет [CBasePane:: калкфикседлайаут](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CDockSite:: Канакцептпане](#canacceptpane)|(Переопределяет [CBasePane:: канакцептпане](../../mfc/reference/cbasepane-class.md#canacceptpane).)|
|[CDockSite:: Креатикс](#createex)|(Переопределяет [CBasePane:: креатикс](../../mfc/reference/cbasepane-class.md#createex).)|
|[CDockSite:: Креатеров](#createrow)||
|[CDockSite::D Оккпане](#dockpane)|(Переопределяет [CBasePane::D оккпане](../../mfc/reference/cbasepane-class.md#dockpane).)|
|[CDockSite::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(Переопределяет [CBasePane::D оесалловдининсертбефоре](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CDockSite:: Финдровиндекс](#findrowindex)||
|[CDockSite:: Фиксупвиртуалректс](#fixupvirtualrects)||
|[CDockSite::GetDockSiteID](#getdocksiteid)||
|[CDockSite:: Жетдоккситеровслист](#getdocksiterowslist)||
|[CDockSite:: Исакцессибилитикомпатибле](#isaccessibilitycompatible)|(Переопределяет `CBasePane::IsAccessibilityCompatible`.)|
|[CDockSite:: Исдрагмоде](#isdragmode)||
|[CDockSite:: Исластров](#islastrow)||
|[CDockSite:: Исректвисиндокксите](#isrectwithindocksite)||
|[CDockSite:: Исресизабле](#isresizable)|(Переопределяет [CBasePane:: исресизабле](../../mfc/reference/cbasepane-class.md#isresizable).)|
|[CDockSite:: Мовепане](#movepane)||
|[CDockSite:: Онинсертров](#oninsertrow)||
|[CDockSite:: Онремоверов](#onremoverow)||
|[CDockSite:: Онресизеров](#onresizerow)||
|[CDockSite:: Онсетвиндовпос](#onsetwindowpos)||
|[CDockSite:: Оншовров](#onshowrow)||
|[CDockSite:: Онсизепарент](#onsizeparent)||
|[CDockSite::P Анефромпоинт](#panefrompoint)|Возвращает область, закрепленную на сайте закрепления в точке, указанной данным параметром.|
|[CDockSite::D Оккпанелефтоф](#dockpaneleftof)|Закрепляет область слева от другой области.|
|[CDockSite:: Финдпанебид](#findpanebyid)|Возвращает область, определенную по заданному идентификатору.|
|[CDockSite:: копанель](#getpanelist)|Возвращает список областей, которые закреплены на сайте закрепления.|
|[CDockSite:: Ректсидефромпоинт](#rectsidefrompoint)||
|[CDockSite:: Ремовепане](#removepane)||
|[CDockSite:: RemoveRow](#removerow)||
|[CDockSite:: Реплацепане](#replacepane)||
|[CDockSite:: Репоситионпанес](#repositionpanes)||
|[CDockSite:: Ресизедокксите](#resizedocksite)||
|[CDockSite:: Ресизеров](#resizerow)||
|[CDockSite:: Шовпане](#showpane)|Отображает область.|
|[CDockSite:: Шовров](#showrow)||
|[CDockSite:: Свапровс](#swaprows)||

## <a name="remarks"></a>Примечания

Платформа автоматически создает `CDockSite` объекты при вызове [CFrameWndEx:: енабледоккинг](../../mfc/reference/cframewndex-class.md#enabledocking). Окна сайта закрепления располагаются на границе области клиента в главном окне фрейма.

Обычно нет необходимости вызывать службы, предоставляемые сайтом DOCKER, так как [Класс CFrameWndEx](../../mfc/reference/cframewndex-class.md) обрабатывает эти службы.

## <a name="example"></a>Пример

В следующем примере показывается, как создать объект класса `CDockSite`.

[!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/cpp/cdocksite-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[От CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксдокксите. h

##  <a name="addrow"></a>CDockSite:: AddRow

```
CDockingPanesRow* AddRow(
    POSITION pos,
    int nHeight);
```

### <a name="parameters"></a>Параметры

окне *POS-терминал*<br/>

окне *нхеигхт*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="adjustdockinglayout"></a>CDockSite:: Аджустдоккинглайаут

```
virtual void AdjustDockingLayout();
```

### <a name="remarks"></a>Примечания

##  <a name="adjustlayout"></a>CDockSite:: Аджустлайаут

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>Примечания

##  <a name="aligndocksite"></a>CDockSite:: Алигндокксите

```
void AlignDockSite(
    const CRect& rectToAlignBy,
    CRect& rectResult,
    BOOL bMoveImmediately);
```

### <a name="parameters"></a>Параметры

окне *ректтоалигнби*<br/>

окне *ректресулт*<br/>

окне *бмовеиммедиатели*<br/>

### <a name="remarks"></a>Примечания

##  <a name="calcfixedlayout"></a>CDockSite:: Калкфикседлайаут

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Параметры

окне *бстретч*<br/>

окне *бхорз*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="canacceptpane"></a>CDockSite:: Канакцептпане

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Параметры

окне *пбар*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="createex"></a>CDockSite:: Креатикс

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    DWORD dwControlBarStyle,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

окне *двстиликс*<br/>

окне *двстиле*<br/>

[in] *rect*<br/>

окне *ппарентвнд*<br/>

окне *двконтролбарстиле*<br/>

окне *пконтекст*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="createrow"></a>CDockSite:: Креатеров

```
virtual CDockingPanesRow* CreateRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nRowHeight);
```

### <a name="parameters"></a>Параметры

окне *ппарентдоккбар*<br/>

окне *ноффсет*<br/>

окне *нровхеигхт*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="dockpane"></a>CDockSite::D Оккпане

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Параметры

окне *приводится*<br/>

окне *доккмесод*<br/>

окне *лпрект*<br/>

### <a name="remarks"></a>Примечания

##  <a name="dockpaneleftof"></a>CDockSite::D Оккпанелефтоф

Закрепляет область слева от другой области.

```
virtual BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>Параметры

*пбартодокк*<br/>
[вход, выход] Указатель на область, которая должна быть закреплена слева от *птаржетбар*.

*птаржетбар*<br/>
[вход, выход] Указатель на целевую область.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если панель закреплена успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="doesallowdyninsertbefore"></a>  CDockSite::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="findpanebyid"></a>CDockSite:: Финдпанебид

Возвращает панель с заданным ИДЕНТИФИКАТОРом.

```
CPane* FindPaneByID(UINT nID);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
окне Идентификатор команды для поиска.

### <a name="return-value"></a>Возвращаемое значение

Указатель на область с указанным ИДЕНТИФИКАТОРом команды или значение NULL, если панель не найдена.

### <a name="remarks"></a>Примечания

##  <a name="findrowindex"></a>CDockSite:: Финдровиндекс

```
int FindRowIndex(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>Параметры

окне *пров*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="fixupvirtualrects"></a>CDockSite:: Фиксупвиртуалректс

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>Примечания

##  <a name="getdocksiteid"></a>CDockSite:: Жетдоккситеид

```
virtual UINT GetDockSiteID() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getdocksiterowslist"></a>CDockSite:: Жетдоккситеровслист

```
const CObList& GetDockSiteRowsList() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getpanelist"></a>CDockSite:: копанель

Возвращает список панелей, закрепленных на сайте закрепления.

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Доступная только для чтения ссылка на список панелей, которые в данный момент закреплены на закрепленной панели.

##  <a name="isaccessibilitycompatible"></a>CDockSite:: Исакцессибилитикомпатибле

```
virtual BOOL IsAccessibilityCompatible();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="isdragmode"></a>CDockSite:: Исдрагмоде

```
virtual BOOL IsDragMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="islastrow"></a>CDockSite:: Исластров

```
bool IsLastRow(CDockingPanesRow* pRow) const;
```

### <a name="parameters"></a>Параметры

окне *пров*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="isrectwithindocksite"></a>CDockSite:: Исректвисиндокксите

```
BOOL IsRectWithinDockSite(
    CRect rect,
    CPoint& ptDelta);
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

окне *птделта*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="isresizable"></a>CDockSite:: Исресизабле

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="movepane"></a>CDockSite:: Мовепане

```
virtual BOOL MovePane(
    CPane* pWnd,
    UINT nFlags,
    CPoint ptOffset);
```

### <a name="parameters"></a>Параметры

окне *приводится*<br/>

окне *нфлагс*<br/>

окне *птоффсет*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="oninsertrow"></a>CDockSite:: Онинсертров

```
virtual void OnInsertRow(POSITION pos);
```

### <a name="parameters"></a>Параметры

окне *POS-терминал*<br/>

### <a name="remarks"></a>Примечания

##  <a name="onremoverow"></a>CDockSite:: Онремоверов

```
virtual void OnRemoveRow(
    POSITION pos,
    BOOL bByShow = FALSE);
```

### <a name="parameters"></a>Параметры

окне *POS-терминал*<br/>

окне *ббишов*<br/>

### <a name="remarks"></a>Примечания

##  <a name="onresizerow"></a>CDockSite:: Онресизеров

```
virtual int OnResizeRow(
    CDockingPanesRow* pRowToResize,
    int nOffset);
```

### <a name="parameters"></a>Параметры

окне *провторесизе*<br/>

окне *ноффсет*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="onsizeparent"></a>CDockSite:: Онсизепарент

```
virtual void OnSizeParent(
    CRect& rectAvailable,
    UINT nSide,
    BOOL bExpand,
    int nOffset);
```

### <a name="parameters"></a>Параметры

окне *ректаваилабле*<br/>

окне *нсиде*<br/>

окне *бекспанд*<br/>

окне *ноффсет*<br/>

### <a name="remarks"></a>Примечания

##  <a name="onsetwindowpos"></a>CDockSite:: Онсетвиндовпос

```
virtual BOOL OnSetWindowPos(
    const CWnd* pWndInsertAfter,
    const CRect& rectWnd,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

окне *пвндинсертафтер*<br/>

окне *ректвнд*<br/>

окне *нфлагс*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="onshowrow"></a>CDockSite:: Оншовров

```
virtual void OnShowRow(
    POSITION pos,
    BOOL bShow);
```

### <a name="parameters"></a>Параметры

окне *POS-терминал*<br/>

окне *бшов*<br/>

### <a name="remarks"></a>Примечания

##  <a name="panefrompoint"></a>CDockSite::P Анефромпоинт

Возвращает область, закрепленную на сайте закрепления в точке, указанной данным параметром.

```
virtual CPane* PaneFromPoint(CPoint pt);
```

### <a name="parameters"></a>Параметры

*pt*<br/>
окне Точка, в координатах экрана, для извлекаемой области.

### <a name="return-value"></a>Возвращаемое значение

Указатель на область, расположенную в указанной точке, или значение NULL, если в указанной точке отсутствует область.

### <a name="remarks"></a>Примечания

##  <a name="rectsidefrompoint"></a>CDockSite:: Ректсидефромпоинт

```
static int __stdcall RectSideFromPoint(
    const CRect& rect,
    const CPoint& point);
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

окне *точка*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="removepane"></a>CDockSite:: Ремовепане

```
virtual void RemovePane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Параметры

окне *приводится*<br/>

окне *доккмесод*<br/>

### <a name="remarks"></a>Примечания

##  <a name="removerow"></a>CDockSite:: RemoveRow

```
void RemoveRow(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>Параметры

окне *пров*<br/>

### <a name="remarks"></a>Примечания

##  <a name="replacepane"></a>CDockSite:: Реплацепане

```
BOOL ReplacePane(
    CPane* pOldBar,
    CPane* pNewBar);
```

### <a name="parameters"></a>Параметры

окне *полдбар*<br/>

окне *пневбар*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="repositionpanes"></a>CDockSite:: Репоситионпанес

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>Параметры

окне *ректневклиентареа*<br/>

### <a name="remarks"></a>Примечания

##  <a name="resizedocksite"></a>CDockSite:: Ресизедокксите

```
void ResizeDockSite(
    int nNewWidth,
    int nNewHeight);
```

### <a name="parameters"></a>Параметры

окне *нневвидс*<br/>

окне *нневхеигхт*<br/>

### <a name="remarks"></a>Примечания

##  <a name="resizerow"></a>CDockSite:: Ресизеров

```
int ResizeRow(
    CDockingPanesRow* pRow,
    int nNewSize,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>Параметры

окне *пров*<br/>

окне *нневсизе*<br/>

окне *баджустлайаут*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="showpane"></a>CDockSite:: Шовпане

Отображает область.

```
virtual BOOL ShowPane(
    CBasePane* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>Параметры

*пбар*<br/>
[вход, выход] Указатель на панель, которую необходимо отобразить или скрыть.

*bShow*<br/>
окне Значение TRUE, чтобы указать, что область должна отображаться; Значение FALSE, чтобы указать, что панель должна быть скрыта.

*бделай*<br/>
окне Значение TRUE, чтобы указать, что макет области должен быть отложен до отображения панели. в противном случае — значение FALSE.

*bActivate*<br/>
окне Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если панель была успешно отображена или скрыта. Значение FALSE, если указанная панель не принадлежит этому сайту закрепления.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы показать или скрыть закрепленные панели. Как правило, необязательно вызывать `CDockSite::ShowPane` напрямую, так как он вызывается родительским окном фрейма или базовой панелью.

##  <a name="showrow"></a>CDockSite:: Шовров

```
void ShowRow(
    CDockingPanesRow* pRow,
    BOOL bShow,
    BOOL bAdjustLayout);
```

### <a name="parameters"></a>Параметры

окне *пров*<br/>

окне *бшов*<br/>

окне *баджустлайаут*<br/>

### <a name="remarks"></a>Примечания

##  <a name="swaprows"></a>CDockSite:: Свапровс

```
void SwapRows(
    CDockingPanesRow* pFirstRow,
    CDockingPanesRow* pSecondRow);
```

### <a name="parameters"></a>Параметры

окне *пфирстров*<br/>

окне *псекондров*<br/>

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CBasePane](../../mfc/reference/cbasepane-class.md)
