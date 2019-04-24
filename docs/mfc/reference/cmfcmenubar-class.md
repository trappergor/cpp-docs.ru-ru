---
title: Класс CMFCMenuBar
ms.date: 10/18/2018
f1_keywords:
- CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar::AdjustLocations
- AFXMENUBAR/CMFCMenuBar::AllowChangeTextLabels
- AFXMENUBAR/CMFCMenuBar::AllowShowOnPaneMenu
- AFXMENUBAR/CMFCMenuBar::CalcFixedLayout
- AFXMENUBAR/CMFCMenuBar::CalcLayout
- AFXMENUBAR/CMFCMenuBar::CalcMaxButtonHeight
- AFXMENUBAR/CMFCMenuBar::CanBeClosed
- AFXMENUBAR/CMFCMenuBar::CanBeRestored
- AFXMENUBAR/CMFCMenuBar::Create
- AFXMENUBAR/CMFCMenuBar::CreateEx
- AFXMENUBAR/CMFCMenuBar::CreateFromMenu
- AFXMENUBAR/CMFCMenuBar::EnableHelpCombobox
- AFXMENUBAR/CMFCMenuBar::EnableMenuShadows
- AFXMENUBAR/CMFCMenuBar::GetAvailableExpandSize
- AFXMENUBAR/CMFCMenuBar::GetColumnWidth
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenu
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::GetFloatPopupDirection
- AFXMENUBAR/CMFCMenuBar::GetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::GetHelpCombobox
- AFXMENUBAR/CMFCMenuBar::GetHMenu
- AFXMENUBAR/CMFCMenuBar::GetMenuFont
- AFXMENUBAR/CMFCMenuBar::GetMenuItem
- AFXMENUBAR/CMFCMenuBar::GetRowHeight
- AFXMENUBAR/CMFCMenuBar::GetSystemButton
- AFXMENUBAR/CMFCMenuBar::GetSystemButtonsCount
- AFXMENUBAR/CMFCMenuBar::GetSystemMenu
- AFXMENUBAR/CMFCMenuBar::HighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsButtonExtraSizeAvailable
- AFXMENUBAR/CMFCMenuBar::IsHighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsMenuShadows
- AFXMENUBAR/CMFCMenuBar::IsRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommands
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommandsDelay
- AFXMENUBAR/CMFCMenuBar::LoadState
- AFXMENUBAR/CMFCMenuBar::OnChangeHot
- AFXMENUBAR/CMFCMenuBar::OnDefaultMenuLoaded
- AFXMENUBAR/CMFCMenuBar::OnSendCommand
- AFXMENUBAR/CMFCMenuBar::OnSetDefaultButtonText
- AFXMENUBAR/CMFCMenuBar::OnToolHitTest
- AFXMENUBAR/CMFCMenuBar::PreTranslateMessage
- AFXMENUBAR/CMFCMenuBar::RestoreOriginalstate
- AFXMENUBAR/CMFCMenuBar::SaveState
- AFXMENUBAR/CMFCMenuBar::SetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::SetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::SetMaximizeMode
- AFXMENUBAR/CMFCMenuBar::SetMenuButtonRTC
- AFXMENUBAR/CMFCMenuBar::SetMenuFont
- AFXMENUBAR/CMFCMenuBar::SetRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::SetShowAllCommands
helpviewer_keywords:
- CMFCMenuBar [MFC], AdjustLocations
- CMFCMenuBar [MFC], AllowChangeTextLabels
- CMFCMenuBar [MFC], AllowShowOnPaneMenu
- CMFCMenuBar [MFC], CalcFixedLayout
- CMFCMenuBar [MFC], CalcLayout
- CMFCMenuBar [MFC], CalcMaxButtonHeight
- CMFCMenuBar [MFC], CanBeClosed
- CMFCMenuBar [MFC], CanBeRestored
- CMFCMenuBar [MFC], Create
- CMFCMenuBar [MFC], CreateEx
- CMFCMenuBar [MFC], CreateFromMenu
- CMFCMenuBar [MFC], EnableHelpCombobox
- CMFCMenuBar [MFC], EnableMenuShadows
- CMFCMenuBar [MFC], GetAvailableExpandSize
- CMFCMenuBar [MFC], GetColumnWidth
- CMFCMenuBar [MFC], GetDefaultMenu
- CMFCMenuBar [MFC], GetDefaultMenuResId
- CMFCMenuBar [MFC], GetFloatPopupDirection
- CMFCMenuBar [MFC], GetForceDownArrows
- CMFCMenuBar [MFC], GetHelpCombobox
- CMFCMenuBar [MFC], GetHMenu
- CMFCMenuBar [MFC], GetMenuFont
- CMFCMenuBar [MFC], GetMenuItem
- CMFCMenuBar [MFC], GetRowHeight
- CMFCMenuBar [MFC], GetSystemButton
- CMFCMenuBar [MFC], GetSystemButtonsCount
- CMFCMenuBar [MFC], GetSystemMenu
- CMFCMenuBar [MFC], HighlightDisabledItems
- CMFCMenuBar [MFC], IsButtonExtraSizeAvailable
- CMFCMenuBar [MFC], IsHighlightDisabledItems
- CMFCMenuBar [MFC], IsMenuShadows
- CMFCMenuBar [MFC], IsRecentlyUsedMenus
- CMFCMenuBar [MFC], IsShowAllCommands
- CMFCMenuBar [MFC], IsShowAllCommandsDelay
- CMFCMenuBar [MFC], LoadState
- CMFCMenuBar [MFC], OnChangeHot
- CMFCMenuBar [MFC], OnDefaultMenuLoaded
- CMFCMenuBar [MFC], OnSendCommand
- CMFCMenuBar [MFC], OnSetDefaultButtonText
- CMFCMenuBar [MFC], OnToolHitTest
- CMFCMenuBar [MFC], PreTranslateMessage
- CMFCMenuBar [MFC], RestoreOriginalstate
- CMFCMenuBar [MFC], SaveState
- CMFCMenuBar [MFC], SetDefaultMenuResId
- CMFCMenuBar [MFC], SetForceDownArrows
- CMFCMenuBar [MFC], SetMaximizeMode
- CMFCMenuBar [MFC], SetMenuButtonRTC
- CMFCMenuBar [MFC], SetMenuFont
- CMFCMenuBar [MFC], SetRecentlyUsedMenus
- CMFCMenuBar [MFC], SetShowAllCommands
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
ms.openlocfilehash: 87844e843057bb295c904b5f1b3d7dd03fa4d797
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58775898"
---
# <a name="cmfcmenubar-class"></a>Класс CMFCMenuBar

Строка меню, которая реализует закрепление.
Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCMenuBar : public CMFCToolbar
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCMenuBar::AdjustLocations](#adjustlocations)|(Переопределяет `CMFCToolBar::AdjustLocations`.)|
|[CMFCMenuBar::AllowChangeTextLabels](#allowchangetextlabels)|Указывает, может ли отображаться текстовые метки в списке изображений на кнопках панели инструментов. (Переопределяет [CMFCToolBar::AllowChangeTextLabels](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels).)|
|[CMFCMenuBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Переопределяет `CPane::AllowShowOnPaneMenu`.)|
|[CMFCMenuBar::CalcFixedLayout](#calcfixedlayout)|Вычисляет горизонтальный размер окна панели инструментов. (Переопределяет [CMFCToolBar::CalcFixedLayout](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout).)|
|[CMFCMenuBar::CalcLayout](#calclayout)|(Переопределяет `CMFCToolBar::CalcLayout`.)|
|[CMFCMenuBar::CalcMaxButtonHeight](#calcmaxbuttonheight)|Вычисляет максимальную высоту кнопок на панели инструментов. (Переопределяет [CMFCToolBar::CalcMaxButtonHeight](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight).)|
|[CMFCMenuBar::CanBeClosed](#canbeclosed)|Указывает, может ли пользователь закрыть панели инструментов. (Переопределяет [CMFCToolBar::CanBeClosed](../../mfc/reference/cmfctoolbar-class.md#canbeclosed).)|
|[CMFCMenuBar::CanBeRestored](#canberestored)|Определяет, будет ли система может восстановиться панель инструментов в исходное состояние после настройки. (Переопределяет [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|
|[CMFCMenuBar::Create](#create)|Создает элемент управления меню и присоединяет его к `CMFCMenuBar` объекта.|
|[CMFCMenuBar::CreateEx](#createex)|Создает `CMFCMenuBar` объекта с параметрами дополнительного стиля.|
|[CMFCMenuBar::CreateFromMenu](#createfrommenu)|Инициализирует `CMFCMenuBar` объекта. Принимает параметр дескриптора HMENU, который выступает в качестве шаблона для заполненного `CMFCMenuBar`.|
|[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)|Позволяет **помочь** поле со списком, расположенный в правой части строки меню.|
|[CMFCMenuBar::EnableMenuShadows](#enablemenushadows)|Указывает, следует ли отображать shadows контекстных меню.|
|[CMFCMenuBar::GetAvailableExpandSize](#getavailableexpandsize)|(Переопределяет [CPane::GetAvailableExpandSize](../../mfc/reference/cpane-class.md#getavailableexpandsize).)|
|[CMFCMenuBar::GetColumnWidth](#getcolumnwidth)|Возвращает ширину кнопки панели инструментов. (Переопределяет [CMFCToolBar::GetColumnWidth](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth).)|
|[CMFCMenuBar::GetDefaultMenu](#getdefaultmenu)|Возвращает дескриптор в исходное меню в файле ресурсов.|
|[CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)|Возвращает идентификатор ресурса для исходного меню в файле ресурсов.|
|[CMFCMenuBar::GetFloatPopupDirection](#getfloatpopupdirection)||
|[CMFCMenuBar::GetForceDownArrows](#getforcedownarrows)||
|[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox)|Возвращает указатель на **помочь** поле со списком.|
|[CMFCMenuBar::GetHMenu](#gethmenu)|Возвращает дескриптор для меню, к которой подключен `CMFCMenuBar` объекта.|
|[CMFCMenuBar::GetMenuFont](#getmenufont)|Возвращает глобальный текущий шрифт для меню объектов.|
|[CMFCMenuBar::GetMenuItem](#getmenuitem)|Возвращает кнопки панели инструментов, связанной с индекс указанного элемента.|
|[CMFCMenuBar::GetRowHeight](#getrowheight)|Возвращает высоту кнопки панели инструментов. (Переопределяет [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[CMFCMenuBar::GetSystemButton](#getsystembutton)||
|[CMFCMenuBar::GetSystemButtonsCount](#getsystembuttonscount)||
|[CMFCMenuBar::GetSystemMenu](#getsystemmenu)||
|[CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)|Указывает, выделяются ли отключенных пунктов меню.|
|[CMFCMenuBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Определяет, может ли отображать кнопки, которые имеют дополнительные границы панели инструментов. (Переопределяет [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|
|[CMFCMenuBar::IsHighlightDisabledItems](#ishighlightdisableditems)|Указывает, выделяются ли отключенных элементов.|
|[CMFCMenuBar::IsMenuShadows](#ismenushadows)|Указывает, рисуются ли shadows контекстных меню.|
|[CMFCMenuBar::IsRecentlyUsedMenus](#isrecentlyusedmenus)|Указывает, отображаются ли недавно использованных команд в строке меню.|
|[CMFCMenuBar::IsShowAllCommands](#isshowallcommands)|Указывает, отображаются ли всплывающие меню всех команд.|
|[CMFCMenuBar::IsShowAllCommandsDelay](#isshowallcommandsdelay)|Указывает, отображать ли меню все команды, после короткой задержки.|
|[CMFCMenuBar::LoadState](#loadstate)|Загружает состояние `CMFCMenuBar` объекта из реестра.|
|[CMFCMenuBar::OnChangeHot](#onchangehot)|Вызывается платформой, когда пользователь выбирает кнопку на панели инструментов. (Переопределяет [CMFCToolBar::OnChangeHot](../../mfc/reference/cmfctoolbar-class.md#onchangehot).)|
|[CMFCMenuBar::OnDefaultMenuLoaded](#ondefaultmenuloaded)|Вызывается платформой при загрузке окна фрейма меню по умолчанию из файла ресурсов.|
|[CMFCMenuBar::OnSendCommand](#onsendcommand)|(Переопределяет `CMFCToolBar::OnSendCommand`.)|
|[CMFCMenuBar::OnSetDefaultButtonText](#onsetdefaultbuttontext)|Вызывается платформой, когда меню находится в режиме настройки, и пользователь изменяет текст пункта меню.|
|[CMFCMenuBar::OnToolHitTest](#ontoolhittest)|(Переопределяет `CMFCToolBar::OnToolHitTest`.)|
|[CMFCMenuBar::PreTranslateMessage](#pretranslatemessage)|(Переопределяет `CMFCToolBar::PreTranslateMessage`.)|
|[CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate)|Вызывается платформой, когда меню находится в режиме настройки, а пользователь выбирает **Сброс** для строки меню.|
|[CMFCMenuBar::SaveState](#savestate)|Сохраняет состояние `CMFCMenuBar` объекта в реестр.|
|[CMFCMenuBar::SetDefaultMenuResId](#setdefaultmenuresid)|Задает исходное меню в файле ресурсов.|
|[CMFCMenuBar::SetForceDownArrows](#setforcedownarrows)||
|[CMFCMenuBar::SetMaximizeMode](#setmaximizemode)|Вызывается платформой при его режим отображения дочернего окна MDI. Если больше не находящегося в развернутом состоянии дочернего окна интерфейса MDI вновь находящегося в развернутом состоянии, этот метод обновляет меню.|
|[CMFCMenuBar::SetMenuButtonRTC](#setmenubuttonrtc)|Задает сведения о классе среды выполнения создается, когда пользователь создает динамически кнопки меню.|
|[CMFCMenuBar::SetMenuFont](#setmenufont)|Задает шрифт для всех меню в приложении.|
|[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)|Указывает, отображается ли строка меню недавно использованных меню команд.|
|[CMFCMenuBar::SetShowAllCommands](#setshowallcommands)|Указывает, отображает ли меню все команды.|

## <a name="remarks"></a>Примечания

`CMFCMenuBar` Класс является строка меню, которая реализует возможности закрепления. Оно похоже на панель инструментов, несмотря на то, что он не может быть закрыт — всегда отображается.

`CMFCMenuBar` поддерживает возможность отображения объектов меню недавно использовавшихся элементов. Если этот параметр включен, `CMFCMenuBar` отображается только подмножество доступных команд на первом просмотре. После этого отображаются последние использованные команды вместе с исходной часть команд. Кроме того пользователь всегда может развернуть меню, чтобы просмотреть все доступные команды. Таким образом каждая команда доступных настраивается для отображения постоянно или для отображения только в том случае, если недавно был выбран.

Чтобы использовать `CMFCMenuBar` объекта, внедрить в объект фрейма главного окна. При обработке `WM_CREATE` сообщений, вызовите `CMFCMenuBar::Create` или `CMFCMenuBar::CreateEx`. Независимо от того, что создание функции использовать, передавать в указатель фрейма главного окна. Затем включите закрепления, вызвав [CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking). Закрепить это меню путем вызова [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane).

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCMenuBar` . Пример показано, как задать стиль области, включить "настроить", окно справки, включить shadows контекстных меню и обновление строки меню. Этот фрагмент кода является частью [IE демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]
[!code-cpp[NVC_MFC_IEDemo#3](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

`CMFCMenuBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxmenubar.h

##  <a name="adjustlocations"></a>  CMFCMenuBar::AdjustLocations

Регулирует положение пунктов меню в строке меню.

```
virtual void AdjustLocations();
```

### <a name="remarks"></a>Примечания

##  <a name="allowchangetextlabels"></a>  CMFCMenuBar::AllowChangeTextLabels

Определяет, разрешены ли текстовые метки в образы в строке меню.

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если пользователь может выбрать для отображения текстовых меток в списке изображений.

### <a name="remarks"></a>Примечания

##  <a name="allowshowonpanemenu"></a>  CMFCMenuBar::AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="calcfixedlayout"></a>  CMFCMenuBar::CalcFixedLayout

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

##  <a name="calclayout"></a>  CMFCMenuBar::CalcLayout

```
virtual CSize CalcLayout(
    DWORD dwMode,
    int nLength = -1);
```

### <a name="parameters"></a>Параметры

[in] *dwMode*<br/>

[in] *nLength*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="calcmaxbuttonheight"></a>  CMFCMenuBar::CalcMaxButtonHeight

```
virtual int CalcMaxButtonHeight();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="canbeclosed"></a>  CMFCMenuBar::CanBeClosed

```
virtual BOOL CanBeClosed() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="canberestored"></a>  CMFCMenuBar::CanBeRestored

```
virtual BOOL CanBeRestored() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="create"></a>  CMFCMenuBar::Create

Создает элемент управления меню и присоединяет его к [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,
    UINT nID = AFX_IDW_MENUBAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
[in] Указатель на родительское окно для нового `CMFCMenuBar` объекта.

*dwStyle*<br/>
[in] Стиль новая строка меню.

*nID*<br/>
[in] Идентификатор дочернего окна панели меню.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

После создания `CMFCMenuBar` объекта, необходимо вызвать `Create`. Этот метод создает `CMFCMenuBar` управления и прикрепляет его к `CMFCMenuBar` объекта.

Дополнительные сведения о стилях инструментов см. в разделе [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).

##  <a name="createex"></a>  CMFCMenuBar::CreateEx

Создает [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объект с указанным расширенные стили.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = TBSTYLE_FLAT,
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,
    CRect rcBorders = CRect(1,
    1,
    1,
    1),
    UINT nID =AFX_IDW_MENUBAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
[in] Указатель на родительское окно нового `CMFCMenuBar` объекта.

*dwCtrlStyle*<br/>
[in] Дополнительные стили для новой панели меню.

*dwStyle*<br/>
[in] Основной стиль новая строка меню.

*rcBorders*<br/>
[in] Объект `CRect` параметр, который указывает размеры для границ `CMFCMenuBar` объекта.

*nID*<br/>
[in] Идентификатор дочернего окна панели меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод выполнен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Следует использовать эту функцию вместо [CMFCMenuBar::Create](#create) при необходимости указать стили, кроме стиль панели инструментов. Некоторые часто используемые дополнительные стили: TBSTYLE_TRANSPARENT и CBRS_TOP.

Список дополнительные стили, см. в разделе [панели инструментов и стили кнопок](/windows/desktop/Controls/toolbar-control-and-button-styles), [общие стили элемента управления](/windows/desktop/Controls/common-control-styles), и [общие стили окна](/windows/desktop/winmsg/window-styles).

### <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать `CreateEx` метод `CMFCMenuBar` класса. Этот фрагмент кода является частью [IE демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]
[!code-cpp[NVC_MFC_IEDemo#2](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]

##  <a name="createfrommenu"></a>  CMFCMenuBar::CreateFromMenu

Инициализирует [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта. Этот метод моделей `CMFCMenuBar` объект после параметра дескриптора HMENU.

```
virtual void CreateFromMenu(
    HMENU hMenu,
    BOOL bDefaultMenu = FALSE,
    BOOL bForceUpdate = FALSE);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
[in] Дескриптор для ресурса меню. `CreateFromMenu` использует этот ресурс в качестве шаблона для `CMFCMenuBar`.

*bDefaultMenu*<br/>
[in] Логическое значение, указывающее, является ли новое меню меню по умолчанию.

*bForceUpdate*<br/>
[in] Логическое значение, указывающее, является ли этот метод вызывает обновление меню.

### <a name="remarks"></a>Примечания

Этот метод следует используйте, если элемент управления меню, чтобы иметь те же элементы меню, как ресурс меню. Этот метод вызывается после вызова либо [CMFCMenuBar::Create](#create) или [CMFCMenuBar::CreateEx](#createex).

##  <a name="enablehelpcombobox"></a>  CMFCMenuBar::EnableHelpCombobox

Позволяет **помочь** поле со списком, расположенный в правой части строки меню.

```
void EnableHelpCombobox(
    UINT uiID,
    LPCTSTR lpszPrompt = NULL,
    int nComboBoxWidth = 150);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
[in] Идентификатор команды для кнопки **помочь** поле со списком.

*lpszPrompt*<br/>
[in] Строка, содержащая текст, платформа отображает в поле со списком, если это пустой и не активен. Например «введите здесь текст».

*nComboBoxWidth*<br/>
[in] Ширина кнопки для поля со списком в пикселях.

### <a name="remarks"></a>Примечания

**Помочь** похож на поле со списком **помочь** списком в строке меню Microsoft Word.

При вызове этого метода с *uiID* значение 0, этот метод скрывает поле со списком. В противном случае этот метод поле со списком автоматически отображается в правой части панели меню. После вызова этого метода вызовите [CMFCMenuBar::GetHelpCombobox](#gethelpcombobox) получить указатель на вставленный [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) объекта.

##  <a name="enablemenushadows"></a>  CMFCMenuBar::EnableMenuShadows

Позволяет shadows контекстных меню.

```
static void EnableMenuShadows(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
[in] Логический параметр, который указывает, следует ли включить shadows контекстных меню.

### <a name="remarks"></a>Примечания

Алгоритм, который использует этот метод сложен и может привести к снижению производительности приложения в медленных системах.

##  <a name="getavailableexpandsize"></a>  CMFCMenuBar::GetAvailableExpandSize

```
virtual int GetAvailableExpandSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getcolumnwidth"></a>  CMFCMenuBar::GetColumnWidth

```
virtual int GetColumnWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getdefaultmenu"></a>  CMFCMenuBar::GetDefaultMenu

Извлекает дескриптор в исходное меню. Платформа загружает исходное меню из файла ресурсов.

```
HMENU GetDefaultMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор для ресурса меню.

### <a name="remarks"></a>Примечания

Если приложение настраивает меню, этот метод можно использовать для получения дескриптора в исходное меню.

##  <a name="getdefaultmenuresid"></a>  CMFCMenuBar::GetDefaultMenuResId

Получает идентификатор ресурса для меню по умолчанию.

```
UINT GetDefaultMenuResId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса меню.

### <a name="remarks"></a>Примечания

Платформа загружает меню по умолчанию для `CMFCMenuBar` объект из файла ресурсов.

##  <a name="getfloatpopupdirection"></a>  CMFCMenuBar::GetFloatPopupDirection

```
int GetFloatPopupDirection(CMFCToolBarMenuButton* pButton);
```

### <a name="parameters"></a>Параметры

[in] *pButton*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getforcedownarrows"></a>  CMFCMenuBar::GetForceDownArrows

```
BOOL GetForceDownArrows();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="gethelpcombobox"></a>  CMFCMenuBar::GetHelpCombobox

Возвращает указатель на **помочь** поле со списком.

```
CMFCToolBarComboBoxButton* GetHelpCombobox();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на **помочь** поле со списком. Значение NULL, если **помочь** поле со списком скрыт или не включен.

### <a name="remarks"></a>Примечания

**Помочь** поле со списком находится в правой части строки меню. Вызовите метод [CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox) для включения этого поле со списком.

##  <a name="gethmenu"></a>  CMFCMenuBar::GetHMenu

Получает дескриптор меню, подключенное к [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта.

```
HMENU GetHMenu() const;
```

##  <a name="getmenufont"></a>  CMFCMenuBar::GetMenuFont

Извлекает текущий шрифт меню.

```
static const CFont& GetMenuFont(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Параметры

*bHorz*<br/>
[in] Логический параметр, который указывает, следует ли возвращать шрифт горизонтальную или вертикальную. Значение TRUE указывает шрифт по горизонтали.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CFont](../../mfc/reference/cfont-class.md) параметр, который содержит текущий шрифт панели меню.

### <a name="remarks"></a>Примечания

Возвращаемый шрифт является глобальных параметров для приложения. Глобальные шрифты сохраняются для всех `CMFCMenuBar` объектов. Эти отдельные шрифты используются для меню горизонтальных и вертикальных полос.

##  <a name="getmenuitem"></a>  CMFCMenuBar::GetMenuItem

Извлекает [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) в строке меню на основе индекс элемента.

```
CMFCToolBarButton* GetMenuItem(int iItem) const;
```

### <a name="parameters"></a>Параметры

*iItem*<br/>
[in] Индекс возвращаемого элемента меню.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CMFCToolBarButton` , соответствующий индекс, заданный *iItem*. Значение NULL, если индекс недопустим.

##  <a name="getrowheight"></a>  CMFCMenuBar::GetRowHeight

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getsystembutton"></a>  CMFCMenuBar::GetSystemButton

```
CMFCToolBarMenuButtonsButton* GetSystemButton(
    UINT uiBtn,
    BOOL bByCommand = TRUE) const;
```

### <a name="parameters"></a>Параметры

[in] *uiBtn*<br/>

[in] *bByCommand*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getsystembuttonscount"></a>  CMFCMenuBar::GetSystemButtonsCount

```
int GetSystemButtonsCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getsystemmenu"></a>  CMFCMenuBar::GetSystemMenu

```
CMFCToolBarSystemMenuButton* GetSystemMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="highlightdisableditems"></a>  CMFCMenuBar::HighlightDisabledItems

Определяет, выделяет ли платформа отключенных пунктов меню.

```
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```

### <a name="parameters"></a>Параметры

*bHighlight*<br/>
[in] Логический параметр, указывает ли платформа выделение элементов меню недоступен.

### <a name="remarks"></a>Примечания

По умолчанию платформа не выделения пунктов меню недоступны, при наведении указателя мыши над ними.

##  <a name="isbuttonextrasizeavailable"></a>  CMFCMenuBar::IsButtonExtraSizeAvailable

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ishighlightdisableditems"></a>  CMFCMenuBar::IsHighlightDisabledItems

Указывает, выделяет ли платформа пунктов меню недоступен.

```
static BOOL IsHighlightDisabledItems();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если выделены элементы меню недоступны; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

По умолчанию платформа не выделения пунктов меню недоступны, при наведении указателя мыши над ними. Используйте [CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems) метод, чтобы включить эту функцию.

##  <a name="ismenushadows"></a>  CMFCMenuBar::IsMenuShadows

Указывает ли платформа Рисование с тенями контекстных меню.

```
static BOOL IsMenuShadows();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если платформа допускает Рисование теней меню; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Используйте [CMFCMenuBar::EnableMenuShadows](#enablemenushadows) метод, чтобы включить или отключить эту функцию.

##  <a name="isrecentlyusedmenus"></a>  CMFCMenuBar::IsRecentlyUsedMenus

Указывает, отображаются ли недавно использованных команд в строке меню.

```
static BOOL IsRecentlyUsedMenus();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение `CMFCMenuBar` объект показано недавно использованных команд меню; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Используйте функцию [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus) для управления ли в строке меню отображается недавно использованные команды меню.

##  <a name="isshowallcommands"></a>  CMFCMenuBar::IsShowAllCommands

Указывает, отображать ли меню все команды.

```
static BOOL IsShowAllCommands();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение `CMFCMenuBar` отображает все команды; в противном случае 0.

### <a name="remarks"></a>Примечания

Объект `CMFCMenuBar` объект можно настроить отображение всех команд, или Показать только подмножество команд. Дополнительные сведения об этой функции см. в разделе [класс CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md).

`IsShowAllCommands` Вы узнаете, как этот компонент настроен для `CMFCMenuBar` объекта. Чтобы контролировать, какие команды меню отображаются, используйте методы [CMFCMenuBar::SetShowAllCommands](#setshowallcommands) и [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus).

##  <a name="isshowallcommandsdelay"></a>  CMFCMenuBar::IsShowAllCommandsDelay

Указывает, является ли [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта отображаются все команды, после короткой задержки.

```
static BOOL IsShowAllCommandsDelay();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если в строке меню отображается полные меню после короткой задержки; в противном случае 0.

### <a name="remarks"></a>Примечания

При настройке строке меню, чтобы отображать недавно использовавшиеся элементы меню отображает полное меню одним из двух способов:

- Отображение полного меню после бывает программной задержки из при наведении курсора на стрелку в нижней части меню.

- Отображение полного меню при нажатии стрелки в нижней части меню.

По умолчанию все `CMFCMenuBar` объектов используйте параметр для отображения полного меню после короткой задержки. Этот параметр нельзя изменить в обработчике `CMFCMenuBar` класса. Тем не менее, пользователь может изменить поведение во время настройки панели инструментов с помощью **Настройка** диалоговое окно...

##  <a name="loadstate"></a>  CMFCMenuBar::LoadState

Загружает состояние панели меню из реестра Windows.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT)-1);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Строка, содержащая путь к разделу реестра Windows.

*nIndex*<br/>
[in] Идентификатор элемента управления для меню.

*uiID*<br/>
[in] Зарезервированное значение.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод был выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Используйте [CMFCMenuBar::SaveState](#savestate) метод для сохранения состояния в строке меню в реестр. Сохраняется следующая информация: пункты меню, состояние закрепления и положение в строке меню.

В большинстве случаев приложение не вызывает `LoadState`. Этот метод вызывается платформой при инициализации рабочей области.

##  <a name="onchangehot"></a>  CMFCMenuBar::OnChangeHot

```
virtual void OnChangeHot(int iHot);
```

### <a name="parameters"></a>Параметры

[in] *iHot*<br/>

### <a name="remarks"></a>Примечания

##  <a name="ondefaultmenuloaded"></a>  CMFCMenuBar::OnDefaultMenuLoaded

Этот метод вызывается платформой при загрузке ресурса меню из файла ресурсов.

```
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
[in] Дескриптор для меню подключен к `CMFCMenuBar` объекта.

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию для выполнения пользовательского кода, после framework загружает ресурс меню из файла ресурсов.

##  <a name="onsendcommand"></a>  CMFCMenuBar::OnSendCommand

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Параметры

[in] *pButton*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="onsetdefaultbuttontext"></a>  CMFCMenuBar::OnSetDefaultButtonText

Этот метод вызывается платформой при изменении пользователем текста элемента в строке меню.

```
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Параметры

*pButton*<br/>
[in] Указатель на [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) объект, который требуется настроить.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если платформа применяет изменения, внесенные пользователем в строку меню; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Реализация по умолчанию для этого метода изменения текста кнопки, предоставленными пользователем текста.

##  <a name="ontoolhittest"></a>  CMFCMenuBar::OnToolHitTest

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

##  <a name="pretranslatemessage"></a>  CMFCMenuBar::PreTranslateMessage

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

[in] *pMsg*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="restoreoriginalstate"></a>  CMFCMenuBar::RestoreOriginalstate

Вызывается платформой, когда пользователь выбирает **Сброс** из **Настройка** диалоговое окно.

```
virtual BOOL RestoreOriginalstate();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод выполнен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод вызывается, когда пользователь выбирает **Сброс** из меню настройки. Можно также вручную вызвать этот метод для программного сброса состояния строки меню. Этот метод загружает исходное состояние из файла ресурсов.

Переопределите этот метод, если вы хотите сделать какой-либо обработки, когда пользователь выбирает **Сброс** параметр.

##  <a name="savestate"></a>  CMFCMenuBar::SaveState

Сохраняет состояние [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта в реестр Windows.

```
virtual BOOL SaveState (
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT)-1);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
[in] Строка, содержащая путь к разделу реестра Windows.

*nIndex*<br/>
[in] Идентификатор элемента управления для меню.

*uiID*<br/>
[in] Зарезервированное значение.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если выполнение прошло успешно; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Как правило, приложение не вызывает `SaveState`. Этот метод вызывается платформой при сериализации рабочей области. Дополнительные сведения см. в разделе [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).

Сохраняется следующая информация: пункты меню, состояние закрепления и положение в строке меню.

##  <a name="setdefaultmenuresid"></a>  CMFCMenuBar::SetDefaultMenuResId

Задает меню по умолчанию для [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта на основании ресурсов.

```
void SetDefaultMenuResId(UINT uiResId);
```

### <a name="parameters"></a>Параметры

*uiResId*<br/>
[in] Идентификатор ресурса для нового меню по умолчанию.

### <a name="remarks"></a>Примечания

[CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate) метод восстанавливает меню по умолчанию из файла ресурсов.

Используйте [CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid) метод для извлечения меню по умолчанию без восстановления.

##  <a name="setforcedownarrows"></a>  CMFCMenuBar::SetForceDownArrows

```
void SetForceDownArrows(BOOL bValue);
```

### <a name="parameters"></a>Параметры

[in] *bValue*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setmaximizemode"></a>  CMFCMenuBar::SetMaximizeMode

Платформа вызывает этот метод при MDI изменяет его режим отображения, ее необходимо обновить строки меню.

```
void SetMaximizeMode(
    BOOL bMax,
    CWnd* pWnd = NULL,
    BOOL bRecalcLayout = TRUE);
```

### <a name="parameters"></a>Параметры

*bMax*<br/>
[in] Логическое значение, указывающее режим. Дополнительные сведения см. в разделе "Примечания".

*pWnd*<br/>
[in] Указатель на дочернего окна интерфейса MDI, меняется.

*bRecalcLayout*<br/>
[in] Логическое значение, указывающее, должны быть пересчитаны макет меню немедленно.

### <a name="remarks"></a>Примечания

Если развернуто дочернего окна MDI, строка меню, присоединенный к окну основного фрейма MDI отображает системное меню и **свернуть**, **развернуть** и **закрыть** кнопки. Если *bMax* имеет значение TRUE и *pWnd* не равно NULL, было максимальным дочернего окна интерфейса MDI, а в строке меню необходимо включить дополнительные элементы управления. В противном случае в строке меню возвращает регулярных состояние.

##  <a name="setmenubuttonrtc"></a>  CMFCMenuBar::SetMenuButtonRTC

Задает сведения о классе среды выполнения, платформа использует при создании пользователем кнопки меню.

```
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```

### <a name="parameters"></a>Параметры

*pMenuButtonRTC*<br/>
[in] [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) сведения для класса, производным от [класс CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md).

### <a name="remarks"></a>Примечания

Когда пользователь добавляет новые кнопки в строке меню, платформа создает кнопки динамически. По умолчанию, он создает `CMFCMenuButton` объектов. Переопределите этот метод, чтобы изменить тип объектов button, создаваемые платформой.

##  <a name="setmenufont"></a>  CMFCMenuBar::SetMenuFont

Задает шрифт для всех меню в приложении.

```
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Параметры

*lpLogFont*<br/>
[in] Указатель на [LOGFONT](/windows/desktop/api/dimm/ns-dimm-__midl___midl_itf_dimm_0000_0000_0003) структура, определяющая шрифт для задания.

*bHorz*<br/>
[in] Значение TRUE, если вы хотите *lpLogFont* параметр, используемый для вертикального шрифта, значение FALSE, если требуется, его можно использовать для горизонтального шрифта.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод был выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Шрифты используются для всех `CMFCMenuBar` объектов. Эти отдельные шрифты используются для меню горизонтальных и вертикальных полос.

Параметры шрифта, глобальные переменные и влияют на все `CMFCMenuBar` объектов.

##  <a name="setrecentlyusedmenus"></a>  CMFCMenuBar::SetRecentlyUsedMenus

Элементы управления, отображается ли строка меню недавно использованные команды меню.

```
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```

### <a name="parameters"></a>Параметры

*bOn*<br/>
[in] Логическое значение, управляющее, отображаются ли недавно использованных меню команд.

##  <a name="setshowallcommands"></a>  CMFCMenuBar::SetShowAllCommands

Определяет, отображает ли меню все доступные команды.

```
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```

### <a name="parameters"></a>Параметры

*bShowAllCommands*<br/>
[in] Логический параметр, который указывает, отображает ли приложение во всплывающем меню команд меню.

### <a name="remarks"></a>Примечания

Если меню не отображается все команды меню, он скрывает команды, которые используются редко. Дополнительные сведения об отображении команды меню, см. в разделе [класс CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
