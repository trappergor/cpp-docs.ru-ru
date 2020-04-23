---
title: Класс CAutoHideDockSite
ms.date: 11/04/2016
f1_keywords:
- CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::CanAcceptPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::DockPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::GetAlignRect
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::RepositionPanes
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetLeft
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetRight
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::UnSetAutoHideMode
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::m_nExtraSpace
helpviewer_keywords:
- CAutoHideDockSite [MFC], CanAcceptPane
- CAutoHideDockSite [MFC], DockPane
- CAutoHideDockSite [MFC], GetAlignRect
- CAutoHideDockSite [MFC], RepositionPanes
- CAutoHideDockSite [MFC], SetOffsetLeft
- CAutoHideDockSite [MFC], SetOffsetRight
- CAutoHideDockSite [MFC], UnSetAutoHideMode
- CAutoHideDockSite [MFC], m_nExtraSpace
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
ms.openlocfilehash: 1f23729ced02a151c6186bdcc72cb8938416be46
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752995"
---
# <a name="cautohidedocksite-class"></a>Класс CAutoHideDockSite

Расширяет `CAutoHideDockSite` класс [CDockSite](../../mfc/reference/cdocksite-class.md) для реализации автоматического скрытия док-панели.

## <a name="syntax"></a>Синтаксис

```
class CAutoHideDockSite : public CDockSite
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|`CAutoHideDockSite::CAutoHideDockSite`|Формирует объект `CAutoHideDockSite`.|
|`CAutoHideDockSite::~CAutoHideDockSite`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|`CAutoHideDockSite::AllowShowOnPaneMenu`|Указывает, `CAutoHideDockSite` отображается ли меню панели.|
|[CAutoHideDockSite:CanAcceptPane](#canacceptpane)|Определяет, является ли объект базового панели производным от [класса CMFCAutoHideBar.](../../mfc/reference/cmfcautohidebar-class.md)|
|[CAutoHideDockSite::DockPane](#dockpane)|Пристыкуется к `CAuotHideDockSite` этому объекту.|
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|Извлекает размер док-станции в координатах экрана.|
|[CAutoHidedockSite::RepositionPanes](#repositionpanes)|Перерисовывает панель `CAutoHideDockSite` с глобальными полями и интервалом кнопок.|
|[CAutoHideDockSite:SetOffsetLeft](#setoffsetleft)|Устанавливает маржу на левой стороне стыковки.|
|[CAutoHideDockSite::SetOffsetRight](#setoffsetright)|Устанавливает маржу на правой стороне стыковки.|
|[CAutoHidedockSite::UnsetAutoHideMode](#unsetautohidemode)|Вызовы [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) для `CAutoHideDockSite`объектов на .|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|Имя|Описание|
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|Определяет размер пространства между панели инструментов и краем стыковочного бара. Это пространство измеряется либо с левого или верхнего края, в зависимости от выравнивания для док-станции.|

## <a name="remarks"></a>Remarks

При вызове [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes)— фреймворк `CAutoHideDockSite` автоматически создает объект. В большинстве случаев вам не следует мгновенно или использовать этот класс напрямую.

Стыковка бар разрыв между левой стороны док-станции и левой стороны [CMFCAutoHideButton класса.](../../mfc/reference/cmfcautohidebutton-class.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="example"></a>Пример

В следующем примере показано, `CAutoHideDockSite` как извлечь `CMFCAutoHideBar` объект из объекта, и как установить левую и правую края стыковки.

[!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** afxautohidedocksite.h

## <a name="cautohidedocksitecanacceptpane"></a><a name="canacceptpane"></a>CAutoHideDockSite:CanAcceptPane

Определяет, является ли базовое стекло объектом [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) или получено из. `CMFCAutoHideBar`

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pBar*|(в) Базовое панель, которую тестирует фреймворк.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если *pBar* `CMFCAutoHideBar`является производным от ; FALSE в противном случае.

### <a name="remarks"></a>Remarks

Если объект базового панели получен `CMFCAutoHideBar`из, он `CAutoHideDockSite`может содержать .

## <a name="cautohidedocksitedockpane"></a><a name="dockpane"></a>CAutoHideDockSite::DockPane

Пристыкуется к панели к этому объекту [CAutoHideDockSite.](../../mfc/reference/cautohidedocksite-class.md)

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pWnd*|(в) Панель, которую пристыковивает рамка.|
|*dockMethod*|(в) Варианты стыковки для панели.|
|*lpRect*|(в) Прямоугольник, который определяет границы для пристыкованного стекла.|

### <a name="remarks"></a>Remarks

Реализация по умолчанию не использует параметр *dockMethod*, который предусмотрен для будущего использования.

Если *lpRect* является NULL, фреймворк помещает панель в место по умолчанию на сайте док-станции. Если участок док-станции горизонтальный, местоположение по умолчанию находится в крайнем левом направлении док-станции. В противном случае местоположение по умолчанию находится в верхней части док-станции.

## <a name="cautohidedocksitegetalignrect"></a><a name="getalignrect"></a>CAutoHideDockSite::GetAlignRect

Извлекает размер док-станции в координатах экрана.

```cpp
void GetAlignRect(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*rect*|(в) Ссылка на прямоугольник. Метод хранит размер док-станции в этом прямоугольнике.|

### <a name="remarks"></a>Remarks

Прямоугольник корректируется для смещенных полей таким образом, чтобы они не были включены.

## <a name="cautohidedocksitem_nextraspace"></a><a name="m_nextraspace"></a>CAutoHideDockSite::m_nExtraSpace

Размер пространства между краями класса [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) и объектами [класса CMFCAutoHideBar.](../../mfc/reference/cmfcautohidebar-class.md)

```
static int m_nExtraSpace;
```

### <a name="remarks"></a>Remarks

Когда `CMFCAutoHideBar` стыковка `CAutoHideDockSite`на, он не должен занимать весь сайт док. Эта глобальная переменная контролирует дополнительное пространство `CMFCAutoHideBar` между левой `CAutoHideDockSite` или верхней границей и соответствующим краем. Используется ли верхний или левый край, зависит от текущего выравнивания.

## <a name="cautohidedocksitesetoffsetleft"></a><a name="setoffsetleft"></a>CAutoHideDockSite:SetOffsetLeft

Устанавливает маржу на левой стороне стыковки.

```cpp
void SetOffsetLeft(int nOffset);
```

### <a name="parameters"></a>Параметры

*nOffset*<br/>
(в) Новое смещение.

### <a name="remarks"></a>Remarks

[Объекты CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) позиционируются `CAutoHideDockSite` статически на объекте. Это означает, что пользователь не может `CMFCAutoHideBar` вручную изменить местоположение объектов. Метод `SetOffsetLeft` контролирует расстояние между левой стороной левой `CMFCAutoHideBar` и левой стороной `CAutoHideDockSite`.

## <a name="cautohidedocksitesetoffsetright"></a><a name="setoffsetright"></a>CAutoHideDockSite::SetOffsetRight

Устанавливает маржу на правой стороне стыковки.

```cpp
void SetOffsetRight(int nOffset);
```

### <a name="parameters"></a>Параметры

*nOffset*<br/>
(в) Новое смещение.

### <a name="remarks"></a>Remarks

[Объекты CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) позиционируются `CAutoHideDockSite` статически на объекте. Это означает, что пользователь не может `CMFCAutoHideBar` вручную изменить местоположение объектов. Метод `SetOffsetRight` контролирует расстояние между правой стороной правой `CMFCAutoHideBar` и правой `CAutoHideDockSite`стороны.

## <a name="cautohidedocksiterepositionpanes"></a><a name="repositionpanes"></a>CAutoHidedockSite::RepositionPanes

Перерисовывает стекла на [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md).

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*rectNewClientArea*|(в) Зарезервированное значение.|

### <a name="remarks"></a>Remarks

Реализация по умолчанию не использует *rectNewClientArea*. Он перерисовывает панели с глобальными полями панели инструментов и интервалом между кнопками.

## <a name="cautohidedocksiteunsetautohidemode"></a><a name="unsetautohidemode"></a>CAutoHidedockSite::UnsetAutoHideMode

Вызывает [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) для объектов на сайте док-станции.

```cpp
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pAutoHideToolbar*|(в) Указатель на панель объекта [CMFCAutoHideBar,](../../mfc/reference/cmfcautohidebar-class.md) `CAutoHideDockSite`расположенную на панели .|

### <a name="remarks"></a>Remarks

Этот метод ищет строку, содержащую *pAutoHideToolbar.* Он `CMFCAutoHideBar.UnSetAutoHideMode` требует для `CMFCAutoHideBar` всех объектов в этом ряду. Если *pAutoHideToolbar* не найден или он NULL, этот `CMFCAutoHideBar` метод `CAutoHideDockSite`требует `CMFCAutoHideBar.UnSetAutoHideMode` для всех объектов на .

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite Class](../../mfc/reference/cdocksite-class.md)
