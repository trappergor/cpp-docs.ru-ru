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
ms.openlocfilehash: 278feca6b64915d0cf789e8f68af3c3fdf9b3129
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739478"
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
|[CMFCMenuBar:: Аджустлокатионс](#adjustlocations)|(Переопределяет `CMFCToolBar::AdjustLocations`.)|
|[CMFCMenuBar:: Алловчанжетекстлабелс](#allowchangetextlabels)|Указывает, могут ли текстовые метки отображаться в области изображения на кнопках панели инструментов. (Переопределяет [CMFCToolBar:: алловчанжетекстлабелс](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels).)|
|[CMFCMenuBar:: Алловшовонпанемену](#allowshowonpanemenu)|(Переопределяет `CPane::AllowShowOnPaneMenu`.)|
|[CMFCMenuBar:: Калкфикседлайаут](#calcfixedlayout)|Вычисляет горизонтальный размер панели инструментов. (Переопределяет [CMFCToolBar:: калкфикседлайаут](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout).)|
|[CMFCMenuBar:: Калклайаут](#calclayout)|(Переопределяет `CMFCToolBar::CalcLayout`.)|
|[CMFCMenuBar:: Калкмаксбуттонхеигхт](#calcmaxbuttonheight)|Вычисляет максимальную высоту кнопок на панели инструментов. (Переопределяет [CMFCToolBar:: калкмаксбуттонхеигхт](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight).)|
|[CMFCMenuBar:: Канбеклосед](#canbeclosed)|Указывает, может ли пользователь закрыть панель инструментов. (Переопределяет [CMFCToolBar:: канбеклосед](../../mfc/reference/cmfctoolbar-class.md#canbeclosed).)|
|[CMFCMenuBar:: Канбересторед](#canberestored)|Определяет, может ли система восстановить исходное состояние панели инструментов после настройки. (Переопределяет [CMFCToolBar:: канбересторед](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|
|[CMFCMenuBar:: Create](#create)|Создает элемент управления Menu и прикрепляет его к `CMFCMenuBar` объекту.|
|[CMFCMenuBar:: Креатикс](#createex)|`CMFCMenuBar` Создает объект с дополнительными параметрами стиля.|
|[CMFCMenuBar:: Креатефроммену](#createfrommenu)|Инициализирует `CMFCMenuBar` объект. Принимает параметр HMENU, который выступает в качестве шаблона для заполнения `CMFCMenuBar`.|
|[CMFCMenuBar:: Енаблехелпкомбобокс](#enablehelpcombobox)|Включает поле со списком **справки** , расположенное в правой части строки меню.|
|[CMFCMenuBar:: Енаблеменушадовс](#enablemenushadows)|Указывает, следует ли отображать тени для всплывающих меню.|
|[CMFCMenuBar:: Жетаваилабликспандсизе](#getavailableexpandsize)|(Переопределяет [CPane:: жетаваилабликспандсизе](../../mfc/reference/cpane-class.md#getavailableexpandsize).)|
|[CMFCMenuBar:: Жетколумнвидс](#getcolumnwidth)|Возвращает ширину кнопок панели инструментов. (Переопределяет [CMFCToolBar:: жетколумнвидс](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth).)|
|[CMFCMenuBar:: Жетдефаултмену](#getdefaultmenu)|Возвращает маркер исходного меню в файле ресурсов.|
|[CMFCMenuBar:: Жетдефаултменуресид](#getdefaultmenuresid)|Возвращает идентификатор ресурса для исходного меню в файле ресурсов.|
|[CMFCMenuBar:: Жетфлоатпопупдиректион](#getfloatpopupdirection)||
|[CMFCMenuBar:: Жетфорцедовнарровс](#getforcedownarrows)||
|[CMFCMenuBar:: Жеселпкомбобокс](#gethelpcombobox)|Возвращает указатель на поле со списком **справки** .|
|[CMFCMenuBar:: Жесмену](#gethmenu)|Возвращает маркер меню, присоединенного к `CMFCMenuBar` объекту.|
|[CMFCMenuBar:: Жетменуфонт](#getmenufont)|Возвращает текущий глобальный шрифт для объектов меню.|
|[CMFCMenuBar:: MenuItem](#getmenuitem)|Возвращает кнопку панели инструментов, связанную с указанным индексом элемента.|
|[CMFCMenuBar:: Жетровхеигхт](#getrowheight)|Возвращает высоту кнопок панели инструментов. (Переопределяет [CMFCToolBar:: жетровхеигхт](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[CMFCMenuBar:: Жетсистембуттон](#getsystembutton)||
|[CMFCMenuBar:: Жетсистембуттонскаунт](#getsystembuttonscount)||
|[CMFCMenuBar:: Жетсистеммену](#getsystemmenu)||
|[CMFCMenuBar:: Хигхлигхтдисабледитемс](#highlightdisableditems)|Указывает, выделяются ли отключенные пункты меню.|
|[CMFCMenuBar:: Исбуттонекстрасизеаваилабле](#isbuttonextrasizeavailable)|Определяет, может ли на панели инструментов отображаться кнопка с расширенными границами. (Переопределяет [CMFCToolBar:: исбуттонекстрасизеаваилабле](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|
|[CMFCMenuBar:: Ишигхлигхтдисабледитемс](#ishighlightdisableditems)|Указывает, выделяются ли отключенные элементы.|
|[CMFCMenuBar:: Исменушадовс](#ismenushadows)|Указывает, отображаются ли тени для всплывающих меню.|
|[CMFCMenuBar:: Исрецентлюседменус](#isrecentlyusedmenus)|Указывает, отображаются ли недавно использованные команды меню в строке меню.|
|[CMFCMenuBar:: Исшоваллкоммандс](#isshowallcommands)|Указывает, отображаются ли во всплывающих меню все команды.|
|[CMFCMenuBar:: Исшоваллкоммандсделай](#isshowallcommandsdelay)|Указывает, отображаются ли в меню все команды после небольшой задержки.|
|[CMFCMenuBar:: LoadState](#loadstate)|Загружает состояние `CMFCMenuBar` объекта из реестра.|
|[CMFCMenuBar:: Ончанжехот](#onchangehot)|Вызывается структурой, когда пользователь выбирает кнопку на панели инструментов. (Переопределяет [CMFCToolBar:: ончанжехот](../../mfc/reference/cmfctoolbar-class.md#onchangehot).)|
|[CMFCMenuBar:: Ондефаултменулоадед](#ondefaultmenuloaded)|Вызывается структурой, когда окно фрейма загружает меню по умолчанию из файла ресурсов.|
|[CMFCMenuBar:: Онсендкомманд](#onsendcommand)|(Переопределяет `CMFCToolBar::OnSendCommand`.)|
|[CMFCMenuBar:: Онсетдефаултбуттонтекст](#onsetdefaultbuttontext)|Вызывается структурой, когда меню находится в режиме настройки, и пользователь изменяет текст пункта меню.|
|[CMFCMenuBar:: Онтулхиттест](#ontoolhittest)|(Переопределяет `CMFCToolBar::OnToolHitTest`.)|
|[CMFCMenuBar::P Ретранслатемессаже](#pretranslatemessage)|(Переопределяет `CMFCToolBar::PreTranslateMessage`.)|
|[CMFCMenuBar:: Рестореоригиналстате](#restoreoriginalstate)|Вызывается структурой, когда меню находится в режиме настройки, и пользователь выбирает **Сброс** для строки меню.|
|[CMFCMenuBar:: SaveState](#savestate)|Сохраняет состояние `CMFCMenuBar` объекта в реестре.|
|[CMFCMenuBar:: Сетдефаултменуресид](#setdefaultmenuresid)|Задает исходное меню в файле ресурсов.|
|[CMFCMenuBar:: Сетфорцедовнарровс](#setforcedownarrows)||
|[CMFCMenuBar:: Сетмаксимиземоде](#setmaximizemode)|Вызывается структурой при изменении режима его просмотра дочернего окна MDI. Если дочернее окно MDI является только что развернутым или больше не развернуто, этот метод обновляет строку меню.|
|[CMFCMenuBar:: Сетменубуттонртк](#setmenubuttonrtc)|Задает сведения о классе среды выполнения, создаваемые при динамическом создании пользователем кнопок меню.|
|[CMFCMenuBar:: Сетменуфонт](#setmenufont)|Задает шрифт для всех меню в приложении.|
|[CMFCMenuBar:: Сетрецентлюседменус](#setrecentlyusedmenus)|Указывает, отображаются ли в строке меню недавно использованные команды меню.|
|[CMFCMenuBar:: Сетшоваллкоммандс](#setshowallcommands)|Указывает, отображаются ли в строке меню все команды.|

## <a name="remarks"></a>Примечания

`CMFCMenuBar` Класс представляет собой строку меню, которая реализует функции закрепления. Она напоминает панель инструментов, но не может быть закрыта — она всегда отображается.

`CMFCMenuBar`поддерживает параметр отображения недавно использованных объектов пункта меню. Если этот параметр включен, `CMFCMenuBar` при первом просмотре отображается только подмножество доступных команд. После этого недавно использованные команды отображаются вместе с исходным подмножеством команд. Кроме того, пользователь всегда может развернуть меню, чтобы просмотреть все доступные команды. Поэтому каждая доступная команда настроена для показа постоянно или для просмотра только в том случае, если она была недавно выбрана.

Чтобы использовать `CMFCMenuBar` объект, внедрите его в основной объект фрейма окна. При обработке `WM_CREATE` сообщения вызовите метод `CMFCMenuBar::Create` или `CMFCMenuBar::CreateEx`. Независимо от того, какая функция создания используется, передайте указатель на главное окно фрейма. Затем включите закрепление, вызвав [CFrameWndEx:: енабледоккинг](../../mfc/reference/cframewndex-class.md#enabledocking). Закрепите это меню, вызвав [CFrameWndEx::D оккпане](../../mfc/reference/cframewndex-class.md#dockpane).

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCMenuBar` . В примере показано, как задать стиль панели, включить кнопку Настройка, включить окно справки, включить тени для всплывающих меню и обновить строку меню. Этот фрагмент кода является частью [примера демонстрационной версии IE](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]
[!code-cpp[NVC_MFC_IEDemo#3](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[кмфкбасетулбар](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

`CMFCMenuBar`

## <a name="requirements"></a>Требования

**Заголовок:** афксменубар. h

##  <a name="adjustlocations"></a>CMFCMenuBar:: Аджустлокатионс

Корректирует положение пунктов меню в строке меню.

```
virtual void AdjustLocations();
```

### <a name="remarks"></a>Примечания

##  <a name="allowchangetextlabels"></a>CMFCMenuBar:: Алловчанжетекстлабелс

Определяет, разрешены ли текстовые метки в изображениях в строке меню.

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если пользователь может выбрать отображение текстовых меток в области изображения.

### <a name="remarks"></a>Примечания

##  <a name="allowshowonpanemenu"></a>CMFCMenuBar:: Алловшовонпанемену

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="calcfixedlayout"></a>CMFCMenuBar:: Калкфикседлайаут

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

##  <a name="calclayout"></a>CMFCMenuBar:: Калклайаут

```
virtual CSize CalcLayout(
    DWORD dwMode,
    int nLength = -1);
```

### <a name="parameters"></a>Параметры

окне *двмоде*<br/>

окне *нленгс*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="calcmaxbuttonheight"></a>CMFCMenuBar:: Калкмаксбуттонхеигхт

```
virtual int CalcMaxButtonHeight();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="canbeclosed"></a>CMFCMenuBar:: Канбеклосед

```
virtual BOOL CanBeClosed() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="canberestored"></a>CMFCMenuBar:: Канбересторед

```
virtual BOOL CanBeRestored() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="create"></a>CMFCMenuBar:: Create

Создает элемент управления Menu и прикрепляет его к объекту [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) .

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,
    UINT nID = AFX_IDW_MENUBAR);
```

### <a name="parameters"></a>Параметры

*ппарентвнд*<br/>
окне Указатель на родительское окно для нового `CMFCMenuBar` объекта.

*двстиле*<br/>
окне Стиль новой строки меню.

*nID*<br/>
окне Идентификатор дочернего окна строки меню.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

После создания `CMFCMenuBar` объекта необходимо вызвать метод `Create`. Этот метод создает `CMFCMenuBar` элемент управления и прикрепляет его `CMFCMenuBar` к объекту.

Дополнительные сведения о стилях панелей инструментов см. в разделе [CBasePane:: сетпанестиле](../../mfc/reference/cbasepane-class.md#setpanestyle).

##  <a name="createex"></a>CMFCMenuBar:: Креатикс

Создает объект [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) с указанными расширенными стилями.

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

*ппарентвнд*<br/>
окне Указатель на родительское окно нового `CMFCMenuBar` объекта.

*двктрлстиле*<br/>
окне Дополнительные стили для новой строки меню.

*двстиле*<br/>
окне Основной стиль новой строки меню.

*ркбордерс*<br/>
окне Параметр, указывающий размеры границ `CMFCMenuBar` объекта. `CRect`

*nID*<br/>
окне Идентификатор дочернего окна строки меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод успешно выполнен; в противном случае — 0.

### <a name="remarks"></a>Примечания

Эту функцию следует использовать вместо [CMFCMenuBar:: Create](#create) , если требуется указать стили в дополнение к стилю панели инструментов. К часто используемым дополнительным стилям относятся TBSTYLE_TRANSPARENT и CBRS_TOP.

Список дополнительных стилей см. в разделе [стили элементов управления и кнопок панели инструментов](/windows/win32/Controls/toolbar-control-and-button-styles), [общие стили элементов управления](/windows/win32/Controls/common-control-styles)и [общие стили окна](/windows/win32/winmsg/window-styles).

### <a name="example"></a>Пример

В следующем примере показано, `CreateEx` как использовать метод `CMFCMenuBar` класса. Этот фрагмент кода является частью [примера демонстрационной версии IE](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]
[!code-cpp[NVC_MFC_IEDemo#2](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]

##  <a name="createfrommenu"></a>CMFCMenuBar:: Креатефроммену

Инициализирует объект [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) . Этот метод моделирует `CMFCMenuBar` объект после параметра HMENU.

```
virtual void CreateFromMenu(
    HMENU hMenu,
    BOOL bDefaultMenu = FALSE,
    BOOL bForceUpdate = FALSE);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
окне Маркер для ресурса меню. `CreateFromMenu`использует этот ресурс в качестве шаблона для `CMFCMenuBar`.

*бдефаултмену*<br/>
окне Логическое значение, указывающее, является ли новое меню меню по умолчанию.

*бфорцеупдате*<br/>
окне Логическое значение, указывающее, вызывает ли этот метод обновление меню.

### <a name="remarks"></a>Примечания

Используйте этот метод, если требуется, чтобы элемент управления Menu имел те же элементы меню, что и ресурс меню. Этот метод вызывается после вызова метода [CMFCMenuBar:: Create](#create) или [CMFCMenuBar:: креатикс](#createex).

##  <a name="enablehelpcombobox"></a>CMFCMenuBar:: Енаблехелпкомбобокс

Включает поле со списком **справки** , расположенное в правой части строки меню.

```
void EnableHelpCombobox(
    UINT uiID,
    LPCTSTR lpszPrompt = NULL,
    int nComboBoxWidth = 150);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
окне Идентификатор команды для кнопки в поле со списком **справки** .

*лпсзпромпт*<br/>
окне Строка, содержащая текст, который платформа отображает в поле со списком, если она пуста и не активна. Например, "введите текст здесь".

*нкомбобоксвидс*<br/>
окне Ширина кнопки для поля со списком в пикселях.

### <a name="remarks"></a>Примечания

Поле со списком **справки** напоминает поле со списком **справки** в строке меню Microsoft Word.

При вызове этого метода с параметром *уиид* , равным 0, этот метод скрывает поле со списком. В противном случае этот метод автоматически отображает поле со списком в правой части строки меню. После вызова этого метода вызовите метод [CMFCMenuBar:: жеселпкомбобокс](#gethelpcombobox) , чтобы получить указатель на вставленный объект [кмфктулбаркомбобоксбуттон](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) .

##  <a name="enablemenushadows"></a>CMFCMenuBar:: Енаблеменушадовс

Включает тени для всплывающих меню.

```
static void EnableMenuShadows(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
окне Логический параметр, указывающий, должны ли быть включены тени для всплывающих меню.

### <a name="remarks"></a>Примечания

Алгоритм, используемый этим методом, является сложным и может снизить производительность приложения в более медленных системах.

##  <a name="getavailableexpandsize"></a>CMFCMenuBar:: Жетаваилабликспандсизе

```
virtual int GetAvailableExpandSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getcolumnwidth"></a>CMFCMenuBar:: Жетколумнвидс

```
virtual int GetColumnWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getdefaultmenu"></a>CMFCMenuBar:: Жетдефаултмену

Извлекает маркер исходного меню. Платформа загружает исходное меню из файла ресурсов.

```
HMENU GetDefaultMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

Маркер для ресурса меню.

### <a name="remarks"></a>Примечания

Если приложение настраивает меню, этот метод можно использовать для получения маркера в исходное меню.

##  <a name="getdefaultmenuresid"></a>CMFCMenuBar:: Жетдефаултменуресид

Возвращает идентификатор ресурса для меню по умолчанию.

```
UINT GetDefaultMenuResId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса меню.

### <a name="remarks"></a>Примечания

Платформа загружает меню по умолчанию для `CMFCMenuBar` объекта из файла ресурсов.

##  <a name="getfloatpopupdirection"></a>CMFCMenuBar:: Жетфлоатпопупдиректион

```
int GetFloatPopupDirection(CMFCToolBarMenuButton* pButton);
```

### <a name="parameters"></a>Параметры

окне *пбуттон*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getforcedownarrows"></a>CMFCMenuBar:: Жетфорцедовнарровс

```
BOOL GetForceDownArrows();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="gethelpcombobox"></a>CMFCMenuBar:: Жеселпкомбобокс

Возвращает указатель на поле со списком **справки** .

```
CMFCToolBarComboBoxButton* GetHelpCombobox();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на поле со списком **справки** . Значение NULL, если поле со списком **справки** скрыто или не включено.

### <a name="remarks"></a>Примечания

Поле со списком **справки** находится в правой части строки меню. Чтобы включить это поле со списком, вызовите метод [CMFCMenuBar:: енаблехелпкомбобокс](#enablehelpcombobox) .

##  <a name="gethmenu"></a>CMFCMenuBar:: Жесмену

Получает маркер меню, присоединенного к объекту [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) .

```
HMENU GetHMenu() const;
```

##  <a name="getmenufont"></a>CMFCMenuBar:: Жетменуфонт

Извлекает шрифт текущего меню.

```
static const CFont& GetMenuFont(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Параметры

*бхорз*<br/>
окне Логический параметр, указывающий, следует ли возвращать горизонтальный или вертикальный шрифт. Значение TRUE указывает горизонтальный шрифт.

### <a name="return-value"></a>Возвращаемое значение

Указатель на параметр [кфонт](../../mfc/reference/cfont-class.md) , который содержит текущий шрифт строки меню.

### <a name="remarks"></a>Примечания

Возвращаемый шрифт является глобальным параметром для приложения. Для всех `CMFCMenuBar` объектов поддерживается два глобальных шрифта. Эти отдельные шрифты используются для горизонтальных и вертикальных строк меню.

##  <a name="getmenuitem"></a>CMFCMenuBar:: MenuItem

Извлекает объект [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) в строке меню на основе индекса элемента.

```
CMFCToolBarButton* GetMenuItem(int iItem) const;
```

### <a name="parameters"></a>Параметры

*iItem*<br/>
окне Индекс возвращаемого элемента меню.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CMFCToolBarButton` объект, соответствующий индексу, заданному параметром *Член iItem*. Значение NULL, если индекс является недопустимым.

##  <a name="getrowheight"></a>CMFCMenuBar:: Жетровхеигхт

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getsystembutton"></a>CMFCMenuBar:: Жетсистембуттон

```
CMFCToolBarMenuButtonsButton* GetSystemButton(
    UINT uiBtn,
    BOOL bByCommand = TRUE) const;
```

### <a name="parameters"></a>Параметры

окне *уибтн*<br/>

окне *ббикомманд*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getsystembuttonscount"></a>CMFCMenuBar:: Жетсистембуттонскаунт

```
int GetSystemButtonsCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="getsystemmenu"></a>CMFCMenuBar:: Жетсистеммену

```
CMFCToolBarSystemMenuButton* GetSystemMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="highlightdisableditems"></a>CMFCMenuBar:: Хигхлигхтдисабледитемс

Определяет, выделяются ли элементы меню в платформе.

```
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```

### <a name="parameters"></a>Параметры

*бхигхлигхт*<br/>
окне Логический параметр, указывающий, выделяют ли платформа недоступные пункты меню.

### <a name="remarks"></a>Примечания

По умолчанию платформа не выделяет недоступные пункты меню, когда пользователь позиционирует на них указатель мыши.

##  <a name="isbuttonextrasizeavailable"></a>CMFCMenuBar:: Исбуттонекстрасизеаваилабле

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ishighlightdisableditems"></a>CMFCMenuBar:: Ишигхлигхтдисабледитемс

Указывает, выделяют ли платформа недоступные пункты меню.

```
static BOOL IsHighlightDisabledItems();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если недоступные элементы меню выделены; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

По умолчанию платформа не выделяет недоступные пункты меню, когда пользователь позиционирует на них указатель мыши. Чтобы включить эту функцию, используйте метод [CMFCMenuBar:: хигхлигхтдисабледитемс](#highlightdisableditems) .

##  <a name="ismenushadows"></a>CMFCMenuBar:: Исменушадовс

Указывает, выводит ли платформа тени для всплывающих меню.

```
static BOOL IsMenuShadows();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если платформа рисует меню тени; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Чтобы включить или отключить эту функцию, используйте метод [CMFCMenuBar:: енаблеменушадовс](#enablemenushadows) .

##  <a name="isrecentlyusedmenus"></a>CMFCMenuBar:: Исрецентлюседменус

Указывает, отображаются ли недавно использованные команды меню в строке меню.

```
static BOOL IsRecentlyUsedMenus();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое `CMFCMenuBar` значение, если объект показывает недавно использованные команды меню; в противном случае — 0.

### <a name="remarks"></a>Примечания

Используйте функцию [CMFCMenuBar:: сетрецентлюседменус](#setrecentlyusedmenus) , чтобы указать, отображаются ли в строке меню недавно использованные команды меню.

##  <a name="isshowallcommands"></a>CMFCMenuBar:: Исшоваллкоммандс

Указывает, отображаются ли в меню все команды.

```
static BOOL IsShowAllCommands();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое `CMFCMenuBar` значение, если отображает все команды; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

`CMFCMenuBar` Объект можно настроить так, чтобы он отображал все команды или отображал только подмножество команд. Дополнительные сведения об этой функции см. в разделе [класс CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md).

`IsShowAllCommands`сведения о том, как эта функция настроена для `CMFCMenuBar` объекта. Чтобы управлять отображением команд меню, используйте методы [CMFCMenuBar:: сетшоваллкоммандс](#setshowallcommands) и [CMFCMenuBar:: сетрецентлюседменус](#setrecentlyusedmenus).

##  <a name="isshowallcommandsdelay"></a>CMFCMenuBar:: Исшоваллкоммандсделай

Указывает, отображает ли объект [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) все команды после небольшой задержки.

```
static BOOL IsShowAllCommandsDelay();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если в строке меню отображаются полные меню после небольшой задержки; в противном случае — 0.

### <a name="remarks"></a>Примечания

При настройке строки меню для отображения недавно использованных элементов в строке меню отображается полное меню одним из двух способов:

- Отображение полного меню после запрограммированной задержки, когда пользователь наводит указатель мыши на стрелку в нижней части меню.

- Отображение полного меню после нажатия пользователем стрелки в нижней части меню.

По умолчанию все `CMFCMenuBar` объекты используют параметр для отображения полного меню после небольшой задержки. Этот параметр не может быть изменен программно `CMFCMenuBar` в классе. Однако пользователь может изменить поведение во время настройки панели инструментов с помощью диалогового окна « **Настройка** ».

##  <a name="loadstate"></a>CMFCMenuBar:: LoadState

Загружает состояние строки меню из реестра Windows.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT)-1);
```

### <a name="parameters"></a>Параметры

*лпсзпрофиленаме*<br/>
окне Строка, содержащая путь к разделу реестра Windows.

*ниндекс*<br/>
окне Идентификатор элемента управления для строки меню.

*uiID*<br/>
окне Зарезервированное значение.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Используйте метод [CMFCMenuBar:: SaveState](#savestate) , чтобы сохранить состояние строки меню в реестре. Сохраненные сведения включают пункты меню, состояние закрепления и положение строки меню.

В большинстве случаев приложение не вызывает `LoadState`. Платформа вызывает этот метод при инициализации рабочей области.

##  <a name="onchangehot"></a>CMFCMenuBar:: Ончанжехот

```
virtual void OnChangeHot(int iHot);
```

### <a name="parameters"></a>Параметры

окне *ихот*<br/>

### <a name="remarks"></a>Примечания

##  <a name="ondefaultmenuloaded"></a>CMFCMenuBar:: Ондефаултменулоадед

Платформа вызывает этот метод при загрузке ресурса меню из файла ресурсов.

```
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
окне Маркер для меню, присоединенного к `CMFCMenuBar` объекту.

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию для выполнения пользовательского кода после того, как платформа загрузит ресурс меню из файла ресурсов.

##  <a name="onsendcommand"></a>CMFCMenuBar:: Онсендкомманд

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Параметры

окне *пбуттон*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="onsetdefaultbuttontext"></a>CMFCMenuBar:: Онсетдефаултбуттонтекст

Платформа вызывает этот метод, когда пользователь изменяет текст элемента в строке меню.

```
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Параметры

*пбуттон*<br/>
окне Указатель на объект [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) , который пользователь хочет настроить.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если платформа применяет пользовательские изменения к строке меню; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Реализация по умолчанию для этого метода изменяет текст кнопки на текст, предоставляемый пользователем.

##  <a name="ontoolhittest"></a>CMFCMenuBar:: Онтулхиттест

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

##  <a name="pretranslatemessage"></a>CMFCMenuBar::P Ретранслатемессаже

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

[in] *pMsg*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="restoreoriginalstate"></a>CMFCMenuBar:: Рестореоригиналстате

Вызывается платформой, когда пользователь выбирает параметр " **Сброс** " в диалоговом окне " **Настройка** ".

```
virtual BOOL RestoreOriginalstate();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод успешно выполнен; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод вызывается, когда пользователь выбирает параметр **Сброс** в меню Настройка. Можно также вручную вызвать этот метод, чтобы программно сбросить состояние строки меню. Этот метод загружает исходное состояние из файла ресурсов.

Переопределите этот метод, если требуется выполнять обработку, когда пользователь выбирает параметр **сброса** .

##  <a name="savestate"></a>CMFCMenuBar:: SaveState

Сохраняет состояние объекта [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) в реестре Windows.

```
virtual BOOL SaveState (
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT)-1);
```

### <a name="parameters"></a>Параметры

*лпсзпрофиленаме*<br/>
окне Строка, содержащая путь к разделу реестра Windows.

*ниндекс*<br/>
окне Идентификатор элемента управления для строки меню.

*uiID*<br/>
окне Зарезервированное значение.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE в случае успешного выполнения; в противном случае FALSE;

### <a name="remarks"></a>Примечания

Как правило, приложение не вызывает `SaveState`. Платформа вызывает этот метод при сериализации рабочей области. Дополнительные сведения см. в разделе [CWinAppEx:: SaveState](../../mfc/reference/cwinappex-class.md#savestate).

Сохраненные сведения включают пункты меню, состояние закрепления и положение строки меню.

##  <a name="setdefaultmenuresid"></a>CMFCMenuBar:: Сетдефаултменуресид

Задает меню по умолчанию для объекта [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) на основе идентификатора ресурса.

```
void SetDefaultMenuResId(UINT uiResId);
```

### <a name="parameters"></a>Параметры

*уиресид*<br/>
окне Идентификатор ресурса для нового меню по умолчанию.

### <a name="remarks"></a>Примечания

Метод [CMFCMenuBar:: рестореоригиналстате](#restoreoriginalstate) восстанавливает меню по умолчанию из файла ресурсов.

Используйте метод [CMFCMenuBar:: жетдефаултменуресид](#getdefaultmenuresid) , чтобы получить меню по умолчанию без его восстановления.

##  <a name="setforcedownarrows"></a>CMFCMenuBar:: Сетфорцедовнарровс

```
void SetForceDownArrows(BOOL bValue);
```

### <a name="parameters"></a>Параметры

окне *bValue*<br/>

### <a name="remarks"></a>Примечания

##  <a name="setmaximizemode"></a>CMFCMenuBar:: Сетмаксимиземоде

Платформа вызывает этот метод, когда интерфейс MDI изменяет свой режим экрана и строка меню должна быть обновлена.

```
void SetMaximizeMode(
    BOOL bMax,
    CWnd* pWnd = NULL,
    BOOL bRecalcLayout = TRUE);
```

### <a name="parameters"></a>Параметры

*бмакс*<br/>
окне Логическое значение, указывающее режим. Дополнительные сведения см. в разделе "Примечания".

*Приводится*<br/>
окне Указатель на изменяемое дочернее окно MDI.

*bRecalcLayout*<br/>
окне Логическое значение, указывающее, следует ли немедленно повторно вычислять макет строки меню.

### <a name="remarks"></a>Примечания

Когда дочернее окно MDI разворачивается, в строке меню, прикрепленной к окну главного фрейма MDI, отображается системное меню и кнопки **сворачивания**, **развертывания** и **закрытия** . Если *бмакс* имеет значение true и *ПРИВОДИТСЯ* не равно null, ДОчернее окно MDI разворачивается, а строка меню должна включать дополнительные элементы управления. В противном случае строка меню будет возвращена в обычное состояние.

##  <a name="setmenubuttonrtc"></a>CMFCMenuBar:: Сетменубуттонртк

Задает сведения о классе среды выполнения, используемые платформой при создании пользователем кнопок меню.

```
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```

### <a name="parameters"></a>Параметры

*пменубуттонртк*<br/>
окне Сведения о [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) для класса, производного от [класса CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md).

### <a name="remarks"></a>Примечания

Когда пользователь добавляет новые кнопки в строку меню, платформа создает динамические кнопки. По умолчанию он создает `CMFCMenuButton` объекты. Переопределите этот метод, чтобы изменить тип объектов кнопки, создаваемый платформой.

##  <a name="setmenufont"></a>CMFCMenuBar:: Сетменуфонт

Задает шрифт для всех строк меню в приложении.

```
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Параметры

*лплогфонт*<br/>
окне Указатель на структуру [LOGFONT](/windows/win32/api/dimm/ns-dimm-logfonta) , определяющую устанавливаемый шрифт.

*бхорз*<br/>
окне Значение TRUE, если требуется, чтобы параметр *лплогфонт* использовался для вертикального ШРИФТА, значение false, если его нужно использовать для горизонтального шрифта.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Для всех `CMFCMenuBar` объектов используются два шрифта. Эти отдельные шрифты используются для горизонтальных и вертикальных строк меню.

Параметры шрифта являются глобальными переменными и влияют `CMFCMenuBar` на все объекты.

##  <a name="setrecentlyusedmenus"></a>CMFCMenuBar:: Сетрецентлюседменус

Определяет, отображаются ли в строке меню недавно использованные команды меню.

```
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```

### <a name="parameters"></a>Параметры

*Системе*<br/>
окне Логическое значение, определяющее, отображаются ли недавно использованные команды меню.

##  <a name="setshowallcommands"></a>CMFCMenuBar:: Сетшоваллкоммандс

Определяет, отображаются ли в меню все доступные команды.

```
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```

### <a name="parameters"></a>Параметры

*бшоваллкоммандс*<br/>
окне Логический параметр, указывающий, отображаются ли во всплывающем меню все команды меню.

### <a name="remarks"></a>Примечания

Если меню не отображает все команды меню, она скрывает редко используемые команды. Дополнительные сведения о отображении команд меню см. в разделе [класс CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
