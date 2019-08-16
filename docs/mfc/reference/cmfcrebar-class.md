---
title: Класс Кмфкребар
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
ms.openlocfilehash: d348cf7aac57ce213e4d3f602501d12cee8e20d8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505443"
---
# <a name="cmfcrebar-class"></a>Класс Кмфкребар

`CMFCReBar` Объект — это панель элементов управления, которая предоставляет макет, сохраняемость и сведения о состоянии для элементов управления главной панели.
Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.
## <a name="syntax"></a>Синтаксис

```
class CMFCReBar : public CPane
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кмфкребар:: Аддбар](#addbar)|Добавляет полосу к главной панели.|
|[Кмфкребар:: Калкфикседлайаут](#calcfixedlayout)|(Переопределяет [CBasePane:: калкфикседлайаут](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[Кмфкребар:: Канфлоат](#canfloat)|(Переопределяет [CBasePane:: канфлоат](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[Кмфкребар:: Create](#create)|Создает элемент управления "Главная панель" и прикрепляет `CMFCReBar` его к объекту.|
|[Кмфкребар:: Енабледоккинг](#enabledocking)|(Переопределяет [CBasePane:: енабледоккинг](../../mfc/reference/cbasepane-class.md#enabledocking).)|
|[Кмфкребар:: Жетребарбандинфосизе](#getrebarbandinfosize)||
|[Кмфкребар:: Жетребарктрл](#getrebarctrl)|Предоставляет прямой доступ к базовому общему элементу управления [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) .|
|[Кмфкребар:: Оншовконтролбармену](#onshowcontrolbarmenu)|(Переопределяет [CPane:: оншовконтролбармену](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[Кмфкребар:: Онтулхиттест](#ontoolhittest)|(Переопределяет [CWnd:: онтулхиттест](../../mfc/reference/cwnd-class.md#ontoolhittest).)|
|[Кмфкребар:: Онупдатекмдуи](#onupdatecmdui)|(Переопределяет [CBasePane:: онупдатекмдуи](cbasepane-class.md).)|
|[Кмфкребар:: Сетпанеалигнмент](#setpanealignment)|(Переопределяет [CBasePane:: сетпанеалигнмент](../../mfc/reference/cbasepane-class.md#setpanealignment).)|

## <a name="remarks"></a>Примечания

`CMFCReBar` Объект может содержать различные дочерние окна. Сюда входят поля редактирования, панели инструментов и списки. Изменить размер главной панели можно программным способом, или пользователь может вручную изменить размер главной панели, перетащив ее панель захвата. Фон объекта главной панели также можно настроить на растровое изображение по своему усмотрению.

Объект главной панели ведет себя аналогично объекту ToolBar. Элемент управления "Главная панель" может содержать одну или несколько полос, а каждая полоса может содержать панель захвата, точечный рисунок, текстовую метку и дочернее окно.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCReBar` . В примере показано, как создать элемент управления "Главная панель" и добавить к нему полосу. Полоса функций выступает в качестве внутренней панели инструментов. Этот фрагмент кода является частью [примера тестирования главной панели](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[От CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CPane](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Кмфкребар](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксребар. h

##  <a name="addbar"></a>Кмфкребар:: Аддбар

Добавляет полосу к главной панели.

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

*пбар*<br/>
[вход, выход] Указатель на дочернее окно, которое должно быть вставлено в главную панель. Объект, на который указывает ссылка, должен иметь стиль окна **WS_CHILD** .

*псзтекст*<br/>
окне Задает текст, отображаемый в главной панели. Текст не является частью дочернего окна. Вместо этого он отображается в самой главной панели.

*pbmp*<br/>
[вход, выход] Указывает битовую карту, отображаемую в фоновом элементе главной панели.

*двстиле*<br/>
окне Содержит стиль, применяемый к полосе. Полный список стилей диапазонов см. в описании `fStyle` структуры [ребарбандинфо](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) в документации по Windows SDK.

*клрфоре*<br/>
окне Представляет цвет переднего плана главной панели.

*клрбакк*<br/>
окне Представляет цвет фона главной панели.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если полоса была успешно добавлена к главной панели; в противном случае — значение FALSE.

##  <a name="create"></a>Кмфкребар:: Create

Создает элемент управления "Главная панель" и присоединяет его к объекту [кмфкребар](../../mfc/reference/cmfcrebar-class.md) .

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Параметры

*ппарентвнд*<br/>
[вход, выход] Указатель на родительское окно этого элемента управления главной панели.

*двктрлстиле*<br/>
окне Задает стиль элемента управления главной панели. Значение стиля по умолчанию — **RBS_BANDBORDERS**, которое отображает узкие строки для разделения смежных полос в элементе управления главной панели. Список допустимых стилей см. в разделе [стили элементов управления главной](/windows/win32/Controls/rebar-control-styles) панели в документации по Windows SDK.

*двстиле*<br/>
окне Стиль окна элемента управления главной панели. Список допустимых стилей см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*nID*<br/>
окне Идентификатор дочернего окна главной панели.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если Главная панель успешно создана; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="getrebarctrl"></a>Кмфкребар:: Жетребарктрл

Предоставляет прямой доступ к `CReBarCtrl` базовому общему элементу управления для `CMFCReBar` объектов.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на базовый `CReBarCtrl` объект.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы воспользоваться преимуществами общих функциональных возможностей элемента управления "Главная панель Windows" при настройке главной панели.

##  <a name="calcfixedlayout"></a>Кмфкребар:: Калкфикседлайаут

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

##  <a name="canfloat"></a>Кмфкребар:: Канфлоат

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="enabledocking"></a>Кмфкребар:: Енабледоккинг

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Параметры

окне *двдоккстиле*<br/>

### <a name="remarks"></a>Примечания

##  <a name="getrebarbandinfosize"></a>Кмфкребар:: Жетребарбандинфосизе

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="onshowcontrolbarmenu"></a>Кмфкребар:: Оншовконтролбармену

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Параметры

[in] *CPoint*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ontoolhittest"></a>Кмфкребар:: Онтулхиттест

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>Параметры

окне *точка*<br/>
окне *Пти*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="onupdatecmdui"></a>Кмфкребар:: Онупдатекмдуи

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Параметры

окне *птаржет*<br/>
окне *бдисаблеифнохндлер*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setpanealignment"></a>Кмфкребар:: Сетпанеалигнмент

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>Параметры

окне *двалигнмент*<br/>

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CReBarCtrl](../../mfc/reference/crebarctrl-class.md)<br/>
[Класс CPane](../../mfc/reference/cpane-class.md)
