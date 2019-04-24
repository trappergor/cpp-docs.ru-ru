---
title: Класс CMFCVisualManagerVS2005
ms.date: 11/04/2016
f1_keywords:
- CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetDockingTabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetMDITabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetPropertyGridGroupColor
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetTabFrameColors
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawCaptionButton
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawPaneCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawSeparator
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawTab
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawToolBoxFrame
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnEraseTabsArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillHighlightedArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillMiniFrameCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnUpdateSystemColors
helpviewer_keywords:
- CMFCVisualManagerVS2005 [MFC], GetDockingTabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetMDITabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetPropertyGridGroupColor
- CMFCVisualManagerVS2005 [MFC], GetTabFrameColors
- CMFCVisualManagerVS2005 [MFC], HasOverlappedAutoHideButtons
- CMFCVisualManagerVS2005 [MFC], OnDrawAutoHideButtonBorder
- CMFCVisualManagerVS2005 [MFC], OnDrawCaptionButton
- CMFCVisualManagerVS2005 [MFC], OnDrawPaneCaption
- CMFCVisualManagerVS2005 [MFC], OnDrawSeparator
- CMFCVisualManagerVS2005 [MFC], OnDrawTab
- CMFCVisualManagerVS2005 [MFC], OnDrawToolBoxFrame
- CMFCVisualManagerVS2005 [MFC], OnEraseTabsArea
- CMFCVisualManagerVS2005 [MFC], OnFillAutoHideButtonBackground
- CMFCVisualManagerVS2005 [MFC], OnFillHighlightedArea
- CMFCVisualManagerVS2005 [MFC], OnFillMiniFrameCaption
- CMFCVisualManagerVS2005 [MFC], OnUpdateSystemColors
ms.assetid: ea39b9ae-327e-4a51-bce7-dc84c78f005b
ms.openlocfilehash: 4d1ef0c9087e876f3e8f43430b58fc80f3923ba6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58773467"
---
# <a name="cmfcvisualmanagervs2005-class"></a>Класс CMFCVisualManagerVS2005

`CMFCVisualManagerVS2005` Придает приложению внешний вид Microsoft Visual Studio 2005.

## <a name="syntax"></a>Синтаксис

```
class CMFCVisualManagerVS2005 : public CMFCVisualManagerOffice2003
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCVisualManagerVS2005::GetDockingTabsBordersSize](#getdockingtabsborderssize)|Этот метод вызывается платформой при рисовании область, в которой будет закреплен и с вкладками. (Переопределяет [CMFCVisualManager::GetDockingTabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getdockingtabsborderssize).)|
|[CMFCVisualManagerVS2005::GetMDITabsBordersSize](#getmditabsborderssize)|Платформа вызывает этот метод, чтобы определить размер границы окна MDITabs, прежде чем выполняется рисование окна. (Переопределяет [CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize).)|
|[CMFCVisualManagerVS2005::GetPropertyGridGroupColor](#getpropertygridgroupcolor)|(Переопределяет [CMFCVisualManagerOffice2003::GetPropertyGridGroupColor](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#getpropertygridgroupcolor).)|
|[CMFCVisualManagerVS2005::GetTabFrameColors](#gettabframecolors)|(Переопределяет [CMFCVisualManagerOffice2003::GetTabFrameColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#gettabframecolors).)|
|[CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons](#hasoverlappedautohidebuttons)|Возвращает, перекрываются ли кнопки автоматического скрытия в текущем наглядный диспетчер. (Переопределяет [CMFCVisualManager::HasOverlappedAutoHideButtons](../../mfc/reference/cmfcvisualmanager-class.md#hasoverlappedautohidebuttons).)|
|[CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder](#ondrawautohidebuttonborder)|(Переопределяет [CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawautohidebuttonborder).)|
|[CMFCVisualManagerVS2005::OnDrawCaptionButton](#ondrawcaptionbutton)|(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawCaptionButton`.)|
|[CMFCVisualManagerVS2005::OnDrawPaneCaption](#ondrawpanecaption)|(Переопределяет [CMFCVisualManagerOffice2003::OnDrawPaneCaption](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawpanecaption).)|
|[CMFCVisualManagerVS2005::OnDrawSeparator](#ondrawseparator)|(Переопределяет [CMFCVisualManagerOffice2003::OnDrawSeparator](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawseparator).)|
|[CMFCVisualManagerVS2005::OnDrawTab](#ondrawtab)|(Переопределяет [CMFCVisualManagerOffice2003::OnDrawTab](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawtab).)|
|[CMFCVisualManagerVS2005::OnDrawToolBoxFrame](#ondrawtoolboxframe)|(Переопределяет [CMFCVisualManager::OnDrawToolBoxFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawtoolboxframe).)|
|[CMFCVisualManagerVS2005::OnEraseTabsArea](#onerasetabsarea)|(Переопределяет [CMFCVisualManagerOffice2003::OnEraseTabsArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onerasetabsarea).)|
|[CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground](#onfillautohidebuttonbackground)|(Переопределяет [CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillautohidebuttonbackground).)|
|[CMFCVisualManagerVS2005::OnFillHighlightedArea](#onfillhighlightedarea)|(Переопределяет [CMFCVisualManagerOffice2003::OnFillHighlightedArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillhighlightedarea).)|
|[CMFCVisualManagerVS2005::OnFillMiniFrameCaption](#onfillminiframecaption)|(Переопределяет `CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`.)|
|[CMFCVisualManagerVS2005::OnUpdateSystemColors](#onupdatesystemcolors)|(Переопределяет [CMFCVisualManagerOffice2003::OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onupdatesystemcolors).)|

## <a name="remarks"></a>Примечания

Класс CMFCVisualManagerVS2005 используется для изменения внешнего вида приложения, аналогично Microsoft Visual Studio 2005.

Все члены этого класса являются виртуальных функций, которые являются производными от предка этого класса [класс CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md).

## <a name="example"></a>Пример

В следующем примере демонстрируется использование наглядный диспетчер VS 2005. Этот фрагмент кода является частью [Desktop оповещения демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DesktopAlertDemo#9](../../mfc/reference/codesnippet/cpp/cmfcvisualmanagervs2005-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

[CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

[CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

[CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)

[CMFCVisualManagerVS2005](../../mfc/reference/cmfcvisualmanagervs2005-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxvisualmanagervs2005.h

##  <a name="getdockingtabsborderssize"></a>  CMFCVisualManagerVS2005::GetDockingTabsBordersSize

```
virtual int GetDockingTabsBordersSize();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getmditabsborderssize"></a>  CMFCVisualManagerVS2005::GetMDITabsBordersSize

```
virtual int GetMDITabsBordersSize();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getpropertygridgroupcolor"></a>  CMFCVisualManagerVS2005::GetPropertyGridGroupColor

```
virtual COLORREF GetPropertyGridGroupColor(CMFCPropertyGridCtrl* pPropList);
```

### <a name="parameters"></a>Параметры

[in] *pPropList*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="gettabframecolors"></a>  CMFCVisualManagerVS2005::GetTabFrameColors

```
virtual void GetTabFrameColors(
    const CMFCBaseTabCtrl* pTabWnd,
    COLORREF& clrDark,
    COLORREF& clrBlack,
    COLORREF& clrHighlight,
    COLORREF& clrFace,
    COLORREF& clrDarkShadow,
    COLORREF& clrLight,
    CBrush*& pbrFace,
    CBrush*& pbrBlack);
```

### <a name="parameters"></a>Параметры

[in] *pTabWnd*<br/>
[in] *clrDark*<br/>
[in] *clrBlack*<br/>
[in] *clrHighlight*<br/>
[in] *clrFace*<br/>
[in] *clrDarkShadow*<br/>
[in] *clrLight*<br/>
[in] *pbrFace*<br/>
[in] *pbrBlack*<br/>

### <a name="remarks"></a>Примечания

##  <a name="hasoverlappedautohidebuttons"></a>  CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons

```
virtual BOOL HasOverlappedAutoHideButtons() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ondrawautohidebuttonborder"></a>  CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder

```
virtual void OnDrawAutoHideButtonBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize,
    CMFCAutoHideButton* pButton);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>
[in] *rectBounds*<br/>
[in] *rectBorderSize*<br/>
[in] *pButton*<br/>

### <a name="remarks"></a>Примечания

##  <a name="ondrawcaptionbutton"></a>  CMFCVisualManagerVS2005::OnDrawCaptionButton

```
virtual void OnDrawCaptionButton(
    CDC* pDC,
    CMFCCaptionButton* pButton,
    BOOL bActive,
    BOOL bHorz,
    BOOL bMaximized,
    BOOL bDisabled,
    int nImageID = -1);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>
[in] *pButton*<br/>
[in] *bActive*<br/>
[in] *bHorz*<br/>
[in] *bMaximized*<br/>
[in] *bDisabled*<br/>
[in] *nImageID*<br/>

### <a name="remarks"></a>Примечания

##  <a name="ondrawpanecaption"></a>  CMFCVisualManagerVS2005::OnDrawPaneCaption

```
virtual COLORREF OnDrawPaneCaption(
    CDC* pDC,
    CDockablePane* pBar,
    BOOL bActive,
    CRect rectCaption,
    CRect rectButtons);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>
[in] *pBar*<br/>
[in] *bActive*<br/>
[in] *rectCaption*<br/>
[in] *rectButtons*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ondrawseparator"></a>  CMFCVisualManagerVS2005::OnDrawSeparator

```
virtual void OnDrawSeparator(
    CDC* pDC,
    CBasePane* pBar,
    CRect rect,
    BOOL bIsHoriz);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>
[in] *pBar*<br/>
[in] *rect*<br/>
[in] *bIsHoriz*<br/>

### <a name="remarks"></a>Примечания

##  <a name="ondrawtab"></a>  CMFCVisualManagerVS2005::OnDrawTab

```
virtual void OnDrawTab(
    CDC* pDC,
    CRect rectTab,
    int iTab,
    BOOL bIsActive,
    const CMFCBaseTabCtrl* pTabWnd);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>
[in] *rectTab*<br/>
[in] *iTab*<br/>
[in] *bIsActive*<br/>
[in] *pTabWnd*<br/>

### <a name="remarks"></a>Примечания

##  <a name="ondrawtoolboxframe"></a>  CMFCVisualManagerVS2005::OnDrawToolBoxFrame

```
virtual void OnDrawToolBoxFrame(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>
[in] *rect*<br/>

### <a name="remarks"></a>Примечания

##  <a name="onerasetabsarea"></a>  CMFCVisualManagerVS2005::OnEraseTabsArea

```
virtual void OnEraseTabsArea(
    CDC* pDC,
    CRect rect,
    const CMFCBaseTabCtrl* pTabWnd);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>
[in] *rect*<br/>
[in] *pTabWnd*<br/>

### <a name="remarks"></a>Примечания

##  <a name="onfillautohidebuttonbackground"></a>  CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground

```
virtual void OnFillAutoHideButtonBackground(
    CDC* pDC,
    CRect rect,
    CMFCAutoHideButton* pButton);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>
[in] *rect*<br/>
[in] *pButton*<br/>

### <a name="remarks"></a>Примечания

##  <a name="onfillhighlightedarea"></a>  CMFCVisualManagerVS2005::OnFillHighlightedArea

```
virtual void OnFillHighlightedArea(
    CDC* pDC,
    CRect rect,
    CBrush* pBrush,
    CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>
[in] *rect*<br/>
[in] *pBrush*<br/>
[in] *pButton*<br/>

### <a name="remarks"></a>Примечания

##  <a name="onfillminiframecaption"></a>  CMFCVisualManagerVS2005::OnFillMiniFrameCaption

```
virtual COLORREF OnFillMiniFrameCaption(
    CDC* pDC,
    CRect rectCaption,
    CPaneFrameWnd* pFrameWnd,
    BOOL bActive);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>
[in] *rectCaption*<br/>
[in] *pFrameWnd*<br/>
[in] *bActive*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="onupdatesystemcolors"></a>  CMFCVisualManagerVS2005::OnUpdateSystemColors

```
virtual void OnUpdateSystemColors();
```

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)<br/>
[Класс CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)<br/>
[Класс CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)<br/>
[Класс CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)
