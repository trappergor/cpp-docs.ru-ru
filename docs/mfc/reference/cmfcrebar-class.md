---
title: Класс CMFCReBar
ms.date: 11/04/2016
f1_keywords:
- CMFCReBar
- AFXREBAR/CMFCReBar
- AFXREBAR/CMFCReBar::AddBar
- AFXREBAR/CMFCReBar::CalcFixedLayout
- AFXREBAR/CMFCReBar::CanFloat
- AFXREBAR/CMFCReBar::Create
- AFXREBAR/CMFCReBar::EnableDocking
- AFXREBAR/CMFCReBar::GetReBarBandInfoSize
- AFXREBAR/CMFCReBar::GetReBarCtrl
- AFXREBAR/CMFCReBar::OnShowControlBarMenu
- AFXREBAR/CMFCReBar::OnToolHitTest
- AFXREBAR/CMFCReBar::OnUpdateCmdUI
- AFXREBAR/CMFCReBar::SetPaneAlignment
helpviewer_keywords:
- CMFCReBar [MFC], AddBar
- CMFCReBar [MFC], CalcFixedLayout
- CMFCReBar [MFC], CanFloat
- CMFCReBar [MFC], Create
- CMFCReBar [MFC], EnableDocking
- CMFCReBar [MFC], GetReBarBandInfoSize
- CMFCReBar [MFC], GetReBarCtrl
- CMFCReBar [MFC], OnShowControlBarMenu
- CMFCReBar [MFC], OnToolHitTest
- CMFCReBar [MFC], OnUpdateCmdUI
- CMFCReBar [MFC], SetPaneAlignment
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
ms.openlocfilehash: b221abf772df06541ecde247a9db9401c0ed3c3a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278019"
---
# <a name="cmfcrebar-class"></a>Класс CMFCReBar

Объект `CMFCReBar` объект является панель элементов управления, которая предоставляет макет, сохраняемость и сведения о состоянии для элементов управления "Главная панель".
Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.
## <a name="syntax"></a>Синтаксис

```
class CMFCReBar : public CPane
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CMFCReBar::AddBar](#addbar)|Добавляет полосу элемент управления главной панели.|
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|(Переопределяет [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCReBar::CanFloat](#canfloat)|(Переопределяет [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[CMFCReBar::Create](#create)|Создает элемент управления "Главная панель" и присоединяет его к `CMFCReBar` объекта.|
|[CMFCReBar::EnableDocking](#enabledocking)|(Переопределяет [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).)|
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|Предоставляет прямой доступ к базовому объекту [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) общего элемента управления.|
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|(Переопределяет [CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|(Переопределяет [CWnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(Переопределяет [CBasePane::OnUpdateCmdUI](cbasepane-class.md).)|
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(Переопределяет [CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment).)|

## <a name="remarks"></a>Примечания

Объект `CMFCReBar` объект может содержать множество дочерних окон. Это включает в себя поля ввода, панелей инструментов и списки. Вы можете изменить размер главной панели программным способом или пользователя можно вручную изменить размер главной панели, перетаскивая его полосы захвата. Можно также задать фон объекта "Главная панель" точечного рисунка по своему усмотрению.

Объект "Главная панель" ведет себя аналогично объект панели инструментов. Элемент управления "Главная панель" может содержать один или несколько делений и каждой зоны может содержать полосу захвата, битовая карта, текстовую метку и дочернего окна.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCReBar` . В примере показано создание элемента управления "Главная панель" и добавьте к нему полосе. Функции использования аппаратного контроллера, в качестве внутренних инструментов. Этот фрагмент кода является частью [пример главной панели теста](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxRebar.h

##  <a name="addbar"></a>  CMFCReBar::AddBar

Добавляет полосу элемент управления главной панели.

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
[in, out] Указатель на дочернему окну, которое должен быть вставлен в главной панели. Упоминаемый объект должен иметь **WS_CHILD** стиль окна.

*pszText*<br/>
[in] Задает текст, появляющийся на главной панели. Текст не является частью дочернего окна. Вместо этого он отображается на главной панели, сам.

*pbmp*<br/>
[in, out] Указывает битовую карту для отображения на заднем плане главной панели.

*dwStyle*<br/>
[in] Содержит стиль, применяемый к полосе. Полный список стилей аппаратного контроллера управления, см. в описании для `fStyle` в [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) структуры в документации по Windows SDK.

*clrFore*<br/>
[in] Представляет цвет переднего плана для главной панели.

*clrBack*<br/>
[in] Представляет цвет фона элемента главной панели.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если диапазон успешно добавлен в главной панели; в противном случае — значение FALSE.

##  <a name="create"></a>  CMFCReBar::Create

Создает элемент управления "Главная панель" и присоединяет его к [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) объекта.

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
[in, out] Указатель на родительское окно элемента управления "Главная панель".

*dwCtrlStyle*<br/>
[in] Задает стиль для элемента управления "Главная панель". Значение по умолчанию стиль — **RBS_BANDBORDERS**, который отображает ограничить строки для разделения смежные полосами в элементе управления "Главная панель". Список допустимых стили, см. в разделе [стили элемента управления главной панели](/windows/desktop/Controls/rebar-control-styles) в документации по Windows SDK.

*dwStyle*<br/>
[in] Стиль окна элемента управления "Главная панель". Список допустимых стили, см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*nID*<br/>
[in] Идентификатор элемента главной панели дочернего окна.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если "Главная панель" создан успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="getrebarctrl"></a>  CMFCReBar::GetReBarCtrl

Предоставляет прямой доступ к `CReBarCtrl` базового элемента управления, общие для `CMFCReBar` объектов.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылку на базовый `CReBarCtrl` объекта.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы воспользоваться преимуществами общие функции управления Windows "Главная панель", при настройке вашего главной панели.

##  <a name="calcfixedlayout"></a>  CMFCReBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Параметры

[in] *bStretch*<br/>
[in] *bHorz*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="canfloat"></a>  CMFCReBar::CanFloat

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="enabledocking"></a>  CMFCReBar::EnableDocking

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Параметры

[in] *dwDockStyle*<br/>

### <a name="remarks"></a>Примечания

##  <a name="getrebarbandinfosize"></a>  CMFCReBar::GetReBarBandInfoSize

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="onshowcontrolbarmenu"></a>  CMFCReBar::OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Параметры

[in] *CPoint*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ontoolhittest"></a>  CMFCReBar::OnToolHitTest

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>Параметры

[in] *точки*<br/>
[in] *pTI*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="onupdatecmdui"></a>  CMFCReBar::OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Параметры

[in] *pTarget*<br/>
[in] *bDisableIfNoHndler*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setpanealignment"></a>  CMFCReBar::SetPaneAlignment

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>Параметры

[in] *dwAlignment*<br/>

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CReBarCtrl](../../mfc/reference/crebarctrl-class.md)<br/>
[Класс CPane](../../mfc/reference/cpane-class.md)
