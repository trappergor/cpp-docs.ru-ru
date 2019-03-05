---
title: Класс CMFCColorPopupMenu
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
ms.openlocfilehash: 0c2fed4aa239faa96abf692a46a27102ce9820a1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283401"
---
# <a name="cmfccolorpopupmenu-class"></a>Класс CMFCColorPopupMenu

Представляет контекстное меню, который используется пользователями для выбора цветов в документ или приложение.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorPopupMenu : public CMFCPopupMenu
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|Создает объект `CMFCColorPopupMenu`.|
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание:|
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|Создает фиксируемого перемещаемой цветовую шкалу. (Переопределяет [CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|Возвращает [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , внедренные во всплывающем меню. (Переопределяет [CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|
|`CMFCColorPopupMenu::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCColorPopupMenu::SetPropList](#setproplist)|Задает свойство объекта элемента управления grid внедренной `CMFCColorBar` объекта.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|name|Описание:|
|`m_bEnabledInCustomizeMode`|Логическое значение, определяющее, следует ли отображать цветовую шкалу.|
|`m_wndColorBar`|`CMFCColorBar` Объект, предоставляющий выбранный цвет.|

### <a name="remarks"></a>Примечания

Этот класс наследует функциональные возможности всплывающего меню `CMFCPopupMenu` класса и управляет `CMFCColorBar` объект, предоставляющий выбранный цвет. Когда платформа панель инструментов находится в режим настройки и `m_bEnabledInCustomizeMode` члена имеет значение FALSE, цветовая панель объекта не отображается. Дополнительные сведения о режиме настройки, см. в разделе [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)

Дополнительные сведения о `CMFCColorBar`, см. в разделе [класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md).

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

##  <a name="cmfccolorpopupmenu"></a>  CMFCColorPopupMenu::CMFCColorPopupMenu

Создает объект `CMFCColorPopupMenu`.

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
[in] Массив цветов, отображаемых структурой всплывающего меню.

*color*<br/>
[in] Значение по умолчанию выбранный цвет.

*lpszAutoColor*<br/>
[in] Текстовая метка *автоматического* кнопка цвета (по умолчанию), или значение NULL.

Стандартную метку для автоматической кнопки — **автоматического**.

*lpszOtherColor*<br/>
[in] Текстовая метка *других* кнопка, отображающая более цвета, или значение NULL.

Стандартный метки другие кнопки **Дополнительные цвета...** .

*lpszDocColors*<br/>
[in] Текстовая подпись кнопки цветов документа. Палитра цветов документе перечислены все цвета, которые в настоящее время использует документ.

*lstDocColors*<br/>
[in] Список цветов, которые в настоящее время использует документ.

*nColumns*<br/>
[in] Число столбцов, к которым имеет массив цветов.

*nHorzDockRows*<br/>
[in] Число строк, к которым имеет цветовой панели, когда она закреплена горизонтально.

*nVertDockColumns*<br/>
[in] Число столбцов, которые цветовой полосы при их закреплении по вертикали.

*colorAutomatic*<br/>
[in] Цвет по умолчанию, платформа применяется при нажатии кнопки автоматического.

*uiCommandID*<br/>
[in] ИД команды управления цветовой полосы.

*bStdColorDlg*<br/>
[in] Логическое значение, указывающее, следует ли отображать диалоговое окно стандартный системный цвет или [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) диалоговое окно.

*pParentBtn*<br/>
[in] Указатель на родительский кнопки.

*nID*<br/>
[in] Идентификатор команды.

### <a name="remarks"></a>Примечания

Каждая перегрузка конструктора задает `m_bEnabledInCustomizeMode` член значение false.

### <a name="example"></a>Пример

В следующем примере демонстрируется создание `CMFCColorPopupMenu` объекта.

[!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]

##  <a name="createtearoffbar"></a>  CMFCColorPopupMenu::CreateTearOffBar

Создает фиксируемого перемещаемой цветовую шкалу.

```
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,
    UINT uiID,
    LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание:|
|*pWndMain*|[in] Указатель на родительское окно перемещаемой панелью.|
|*uiID*|[in] Идентификатор команды перемещаемой панелью.|
|*lpszName*|[in] Текст окна перемещаемой панелью.|

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый объект панели управления перемещаемой.

### <a name="remarks"></a>Примечания

Этот метод создает [класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) объекта и приводит его к [класс CPane](../../mfc/reference/cpane-class.md) указатель. Можно привести это значение к [класс CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) указатель с помощью одного из макросы приведения, описанные в [тип-приведения для объектов классов MFC](../../mfc/reference/type-casting-of-mfc-class-objects.md).

##  <a name="getmenubar"></a>  CMFCColorPopupMenu::GetMenuBar

Возвращает [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , внедренные во всплывающем меню.

```
virtual CMFCPopupMenuBar* GetMenuBar();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на внедренном `CMFCPopupMenuBar`.

### <a name="remarks"></a>Примечания

Всплывающее меню цвета имеет встроенный [класс CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) объекта. Переопределите этот метод в производном классе, если приложение использует различные внедренного типа.

##  <a name="setproplist"></a>  CMFCColorPopupMenu::SetPropList

Задает свойство объекта элемента управления grid внедренной `CMFCColorBar` объекта.

```
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>Параметры

*pWndList*<br/>
[in] Указатель на объект элемента управления сетки свойств.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
