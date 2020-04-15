---
title: CmFCColorPopupMenu класс
ms.date: 11/04/2016
f1_keywords:
- CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CreateTearOffBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::GetMenuBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::SetPropList
helpviewer_keywords:
- CMFCColorPopupMenu [MFC], CMFCColorPopupMenu
- CMFCColorPopupMenu [MFC], CreateTearOffBar
- CMFCColorPopupMenu [MFC], GetMenuBar
- CMFCColorPopupMenu [MFC], SetPropList
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
ms.openlocfilehash: bcdf60c974ecdc437b90891d2b46a5eec94859d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367681"
---
# <a name="cmfccolorpopupmenu-class"></a>CmFCColorPopupMenu класс

Представляет всплывающее меню, которое пользователи используют для выбора цветов в документе или приложении.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorPopupMenu : public CMFCPopupMenu
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|Формирует объект `CMFCColorPopupMenu`.|
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCColorPopupМеню::CreateTearOffBar](#createtearoffbar)|Создает док-станцию разрыва цвета бар. (Перекрывает [CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|
|[CMFCColorPopupМеню::GetMenuBar](#getmenubar)|Возвращает [CMFCPopupMenuBar,](../../mfc/reference/cmfcpopupmenubar-class.md) встроенный в всплывающее меню. (Переопределяет [CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|
|`CMFCColorPopupMenu::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCColorPopupМеню::SetPropList](#setproplist)|Устанавливает объект управления сеткой `CMFCColorBar` свойства встроенного объекта.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|Имя|Описание|
|`m_bEnabledInCustomizeMode`|Значение Boolean, определяющее, показывать ли цветовую панель.|
|`m_wndColorBar`|Объект, `CMFCColorBar` обеспечивающий выбор цвета.|

### <a name="remarks"></a>Remarks

Этот класс наследует функциональность всплывающее `CMFCPopupMenu` меню класса и `CMFCColorBar` управляет объектом, обеспечивающим выбор цвета. Когда платформа панели инструментов находится в `m_bEnabledInCustomizeMode` режиме настройки и участник настроен на FALSE, объект цветовой панели не отображается. Для получения дополнительной информации о режиме настройки см. [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)

Для получения `CMFCColorBar`дополнительной информации о, см. [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

[CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxcolorpopupmenu.h

## <a name="cmfccolorpopupmenucmfccolorpopupmenu"></a><a name="cmfccolorpopupmenu"></a>CMFCColorPopupMenu::CMFCColorPopupMenu

Формирует объект `CMFCColorPopupMenu`.

```
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    int nHorzDockRows,
    int nVertDockColumns,
    COLORREF colorAutomatic,
    UINT uiCommandID,
    BOOL bStdColorDlg = FALSE);

CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic);

CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*Цвета*<br/>
(в) Массив цветов, отображаемый фреймворками в всплывающем меню.

*Цвет*<br/>
(в) Выбранный по умолчанию цвет.

*lpszAutoColor*<br/>
(в) Текстовая метка *автоматической* (по умолчанию) цветной кнопки, или NULL.

Стандартная метка для автоматической кнопки **автоматическая**.

*lpszOtherColor*<br/>
(в) Текстовая метка *другой* кнопки, которая отображает больше цветов, или NULL.

Стандартная метка для другой кнопки **больше цветов ...**.

*lpszDocColors*<br/>
(в) Текстовая метка кнопки цветов документа. В документе цветовая палитра перечисляет все цвета, которые документ использует в настоящее время.

*lstDocColors*<br/>
(в) Список цветов, которые в настоящее время используется документом.

*nColumns*<br/>
(в) Количество столбцов, которые есть у массива цветов.

*nHorzDockRows*<br/>
(в) Количество строк, которые имеет цветовая панель, когда она состыкована горизонтально.

*nVertDockКолонки*<br/>
(в) Количество столбцов, которые имеет цветовая панель, когда она состыкована вертикально.

*colorAutomatic*<br/>
(в) Цвет по умолчанию, который применяется при нажатии кнопки автоматической.

*uiCommandID*<br/>
(в) Идентификатор команды управления цветовой панелью.

*bStdColorDlg*<br/>
(в) Boolean, который указывает, следует ли показывать стандартную систему цвет диалоговую коробку или диалоговое окно [CMFCColorDialog.](../../mfc/reference/cmfccolordialog-class.md)

*pParentBtn*<br/>
(в) Указатель на кнопку родительской кнопки.

*nID*<br/>
(в) Идентификатор команды.

### <a name="remarks"></a>Remarks

Каждый перегруженный конструктор `m_bEnabledInCustomizeMode` устанавливает член FALSE.

### <a name="example"></a>Пример

В следующем примере показано, `CMFCColorPopupMenu` как построить объект.

[!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]

## <a name="cmfccolorpopupmenucreatetearoffbar"></a><a name="createtearoffbar"></a>CMFCColorPopupМеню::CreateTearOffBar

Создает док-станцию разрыва цвета бар.

```
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,
    UINT uiID,
    LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pWndMain*|(в) Указатель на родительское окно барной стойки.|
|*uiID*|(в) Идентификатор команды бар отрыва.|
|*lpszName*|(в) Текст окна отрыва бара.|

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый объект панели управления разрывом.

### <a name="remarks"></a>Remarks

Этот метод создает объект [класса CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) и отбрасывает его на указатель [класса CPane.](../../mfc/reference/cpane-class.md) Вы можете отбросить это значение обратно в указатель [класса CMFCColorBar,](../../mfc/reference/cmfccolorbar-class.md) используя один из макросов литья, описанных в [типе литья объектов класса MFC.](../../mfc/reference/type-casting-of-mfc-class-objects.md)

## <a name="cmfccolorpopupmenugetmenubar"></a><a name="getmenubar"></a>CMFCColorPopupМеню::GetMenuBar

Возвращает [CMFCPopupMenuBar,](../../mfc/reference/cmfcpopupmenubar-class.md) встроенный в всплывающее меню.

```
virtual CMFCPopupMenuBar* GetMenuBar();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на встроенный `CMFCPopupMenuBar`.

### <a name="remarks"></a>Remarks

Цветное всплывающее меню имеет встроенный объект [класса CMFCPopupMenuBar.](../../mfc/reference/cmfcpopupmenubar-class.md) Переопределить этот метод в производном классе, если приложение использует другой встроенный тип.

## <a name="cmfccolorpopupmenusetproplist"></a><a name="setproplist"></a>CMFCColorPopupМеню::SetPropList

Устанавливает объект управления сеткой `CMFCColorBar` свойства встроенного объекта.

```
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>Параметры

*pWndList*<br/>
(в) Указатель на объект управления сеткой свойств.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
