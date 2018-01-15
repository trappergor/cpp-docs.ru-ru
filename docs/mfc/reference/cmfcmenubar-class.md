---
title: "Класс CMFCMenuBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "36"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 56e8e97645d4baa74033af07ba08ab2eae0a3557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcmenubar-class"></a>Класс CMFCMenuBar
Строка меню, которая реализует закрепление.  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCMenuBar : public CMFCToolbar  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCMenuBar::AdjustLocations](#adjustlocations)|(Переопределяет `CMFCToolBar::AdjustLocations`.)|  
|[CMFCMenuBar::AllowChangeTextLabels](#allowchangetextlabels)|Указывает, может ли отображаться текстовые метки в разделе изображения на кнопке панели инструментов. (Переопределяет [CMFCToolBar::AllowChangeTextLabels](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels).)|  
|[CMFCMenuBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Переопределяет `CPane::AllowShowOnPaneMenu`.)|  
|[CMFCMenuBar::CalcFixedLayout](#calcfixedlayout)|Вычисляет размер панели инструментов по горизонтали. (Переопределяет [CMFCToolBar::CalcFixedLayout](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout).)|  
|[CMFCMenuBar::CalcLayout](#calclayout)|(Переопределяет `CMFCToolBar::CalcLayout`.)|  
|[CMFCMenuBar::CalcMaxButtonHeight](#calcmaxbuttonheight)|Вычисляет Максимальная высота кнопки на панели инструментов. (Переопределяет [CMFCToolBar::CalcMaxButtonHeight](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight).)|  
|[CMFCMenuBar::CanBeClosed](#canbeclosed)|Указывает, является ли пользователь может закрыть панель инструментов. (Переопределяет [CMFCToolBar::CanBeClosed](../../mfc/reference/cmfctoolbar-class.md#canbeclosed).)|  
|[CMFCMenuBar::CanBeRestored](#canberestored)|Определяет ли система восстановить панель инструментов в исходное состояние после настройки. (Переопределяет [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|  
|[CMFCMenuBar::Create](#create)|Создает элемент управления меню и прикрепляет его к `CMFCMenuBar` объекта.|  
|[CMFCMenuBar::CreateEx](#createex)|Создает `CMFCMenuBar` объекта с дополнительными возможностями параметрами.|  
|[CMFCMenuBar::CreateFromMenu](#createfrommenu)|Инициализирует `CMFCMenuBar` объекта. Принимает `HMENU` параметр, который выступает в качестве шаблона для заполненного `CMFCMenuBar`.|  
|[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)|Включает **справки** со списком, расположенный справа от строки меню.|  
|[CMFCMenuBar::EnableMenuShadows](#enablemenushadows)|Указывает, следует ли отображать тени в контекстных меню.|  
|[CMFCMenuBar::GetAvailableExpandSize](#getavailableexpandsize)|(Переопределяет [CPane::GetAvailableExpandSize](../../mfc/reference/cpane-class.md#getavailableexpandsize).)|  
|[CMFCMenuBar::GetColumnWidth](#getcolumnwidth)|Возвращает ширину кнопки панели инструментов. (Переопределяет [CMFCToolBar::GetColumnWidth](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth).)|  
|[CMFCMenuBar::GetDefaultMenu](#getdefaultmenu)|Возвращает дескриптор для исходного меню в файле ресурсов.|  
|[CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)|Возвращает идентификатор ресурса для исходного меню в файле ресурсов.|  
|[CMFCMenuBar::GetFloatPopupDirection](#getfloatpopupdirection)||  
|[CMFCMenuBar::GetForceDownArrows](#getforcedownarrows)||  
|[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox)|Возвращает указатель на **справки** поле со списком.|  
|[CMFCMenuBar::GetHMenu](#gethmenu)|Возвращает дескриптор для меню, который подключен к `CMFCMenuBar` объекта.|  
|[CMFCMenuBar::GetMenuFont](#getmenufont)|Возвращает глобальный текущий шрифт для меню объектов.|  
|[CMFCMenuBar::GetMenuItem](#getmenuitem)|Возвращает кнопки панели инструментов, связанные с индекс указанного элемента.|  
|[CMFCMenuBar::GetRowHeight](#getrowheight)|Возвращает высоту кнопки панели инструментов. (Переопределяет [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|  
|[CMFCMenuBar::GetSystemButton](#getsystembutton)||  
|[CMFCMenuBar::GetSystemButtonsCount](#getsystembuttonscount)||  
|[CMFCMenuBar::GetSystemMenu](#getsystemmenu)||  
|[CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)|Указывает, выделяются ли пунктов меню отключен.|  
|[CMFCMenuBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Определяет, можно ли панели инструментов отображаются кнопки, расширена границы. (Переопределяет [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|  
|[CMFCMenuBar::IsHighlightDisabledItems](#ishighlightdisableditems)|Указывает, выделяются ли отключенные объекты.|  
|[CMFCMenuBar::IsMenuShadows](#ismenushadows)|Указывает, отображаются ли тени в контекстных меню.|  
|[CMFCMenuBar::IsRecentlyUsedMenus](#isrecentlyusedmenus)|Указывает, отображаются ли недавно используемым командам меню в строке меню.|  
|[CMFCMenuBar::IsShowAllCommands](#isshowallcommands)|Указывает, отображать ли всплывающие меню всех команд.|  
|[CMFCMenuBar::IsShowAllCommandsDelay](#isshowallcommandsdelay)|Указывает, является ли меню отображаются все команды после короткой задержки.|  
|[CMFCMenuBar::LoadState](#loadstate)|Загружает состояние `CMFCMenuBar` объекта из реестра.|  
|[CMFCMenuBar::OnChangeHot](#onchangehot)|Вызывается платформой, когда пользователь выбирает кнопку на панели инструментов. (Переопределяет [CMFCToolBar::OnChangeHot](../../mfc/reference/cmfctoolbar-class.md#onchangehot).)|  
|[CMFCMenuBar::OnDefaultMenuLoaded](#ondefaultmenuloaded)|Вызывается платформой, когда окно фрейма загружает меню по умолчанию из файла ресурсов.|  
|[CMFCMenuBar::OnSendCommand](#onsendcommand)|(Переопределяет `CMFCToolBar::OnSendCommand`.)|  
|[CMFCMenuBar::OnSetDefaultButtonText](#onsetdefaultbuttontext)|Вызывается платформой, если меню находится в режим настройки и пользователь изменяет текст пункта меню.|  
|[CMFCMenuBar::OnToolHitTest](#ontoolhittest)|(Переопределяет `CMFCToolBar::OnToolHitTest`.)|  
|[CMFCMenuBar::PreTranslateMessage](#pretranslatemessage)|(Переопределяет `CMFCToolBar::PreTranslateMessage`.)|  
|[CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate)|Вызывается платформой, если меню находится в режим настройки и пользователь выбирает **Сброс** для строки меню.|  
|[CMFCMenuBar::SaveState](#savestate)|Сохраняет состояние `CMFCMenuBar` объекта в реестр.|  
|[CMFCMenuBar::SetDefaultMenuResId](#setdefaultmenuresid)|Задает исходное меню в файле ресурсов.|  
|[CMFCMenuBar::SetForceDownArrows](#setforcedownarrows)||  
|[CMFCMenuBar::SetMaximizeMode](#setmaximizemode)|Вызывается платформой при его режим отображения дочернего окна MDI. Если дочернее окно MDI вновь развернуто или больше не развернуто, этот метод обновляет меню.|  
|[CMFCMenuBar::SetMenuButtonRTC](#setmenubuttonrtc)|Задает сведения о классе среды выполнения, создается, когда пользователь создает динамически кнопки меню.|  
|[CMFCMenuBar::SetMenuFont](#setmenufont)|Задает шрифт для всех меню в приложении.|  
|[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)|Указывает, отображается ли строка меню команды недавно использовавшихся меню.|  
|[CMFCMenuBar::SetShowAllCommands](#setshowallcommands)|Указывает, отображает ли строка меню все команды.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCMenuBar` Класс является строка меню, которая реализует функциональные возможности закрепления. Панель инструментов, как указано, несмотря на то, что он не может быть закрыт — всегда отображается.  
  
 `CMFCMenuBar`поддерживает параметр отображения объектов меню недавно использовавшихся элементов. Если этот параметр включен, `CMFCMenuBar` отображается только подмножество доступных команд на первом просмотре. После этого отображаются последние использованные команды, а также исходный набор команд. Кроме того пользователь всегда может развернуть меню, чтобы просмотреть все доступные команды. Таким образом каждая команда доступных настраивается постоянно отобразить, или для отображения только в том случае, если недавно был выбран.  
  
 Для использования `CMFCMenuBar` объекта, внедрите его в объект фрейма главного окна. При обработке `WM_CREATE` сообщений, вызовите метод `CMFCMenuBar::Create` или `CMFCMenuBar::CreateEx`. Независимо от того, которые создают функции использовать, следует передать указатель фрейма главного окна. Затем включите закрепление путем вызова [CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking). Закрепить это меню, вызвав [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CMFCMenuBar` класса. В примере показано, как задать стиль панели, включить кнопку Настройка, включение окно справки, тени в контекстных меню и обновления в меню. Этот фрагмент кода является частью [IE демонстрационный пример](../../visual-cpp-samples.md).  
  
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
  
##  <a name="adjustlocations"></a>CMFCMenuBar::AdjustLocations  
 Регулирует положение пунктов меню в строке меню.  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="allowchangetextlabels"></a>CMFCMenuBar::AllowChangeTextLabels  
 Определяет, могут ли метки, текст под изображениями в строке меню.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` , если пользователь может выбрать для отображения текстовых меток в списке изображений.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="allowshowonpanemenu"></a>CMFCMenuBar::AllowShowOnPaneMenu  

  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="calcfixedlayout"></a>CMFCMenuBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="calclayout"></a>CMFCMenuBar::CalcLayout  

  
```  
virtual CSize CalcLayout(
    DWORD dwMode,  
    int nLength = -1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwMode`  
 [in] `nLength`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="calcmaxbuttonheight"></a>CMFCMenuBar::CalcMaxButtonHeight  

  
```  
virtual int CalcMaxButtonHeight();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="canbeclosed"></a>CMFCMenuBar::CanBeClosed  

  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="canberestored"></a>CMFCMenuBar::CanBeRestored  

  
```  
virtual BOOL CanBeRestored() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="create"></a>CMFCMenuBar::Create  
 Создает элемент управления меню и прикрепляет его к [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,  
    UINT nID = AFX_IDW_MENUBAR);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParentWnd`  
 Указатель на родительское окно для нового `CMFCMenuBar` объекта.  
  
 [in] `dwStyle`  
 Стиль новое меню.  
  
 [in] `nID`  
 Идентификатор дочернего окна в строке меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `TRUE` в случае успешного выполнения; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 После создания `CMFCMenuBar` объекта, необходимо вызвать метод `Create`. Этот метод создает `CMFCMenuBar` управления и прикрепляет его к `CMFCMenuBar` объекта.  
  
 Дополнительные сведения о стилях инструментов см. в разделе [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).  
  
##  <a name="createex"></a>CMFCMenuBar::CreateEx  
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
 [in] `pParentWnd`  
 Указатель на родительское окно нового `CMFCMenuBar` объекта.  
  
 [in] `dwCtrlStyle`  
 Дополнительные стили для новой панели меню.  
  
 [in] `dwStyle`  
 Основной стиль новое меню.  
  
 [in] `rcBorders`  
 Объект `CRect` параметр, который указывает размеры для границ `CMFCMenuBar` объекта.  
  
 [in] `nID`  
 Идентификатор дочернего окна в строке меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Следует использовать эту функцию вместо [CMFCMenuBar::Create](#create) при необходимости укажите стили помимо стиля toolbar. Некоторые часто используемые дополнительные стили `TBSTYLE_TRANSPARENT` и `CBRS_TOP`.  
  
 Списки дополнительные стили, в разделе [панели инструментов и стили кнопок](http://msdn.microsoft.com/library/windows/desktop/bb760439), [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498), и [общие стили окна](http://msdn.microsoft.com/library/windows/desktop/ms632600).  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `CreateEx` метод `CMFCMenuBar` класса. Этот фрагмент кода является частью [IE демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#2](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]  
  
##  <a name="createfrommenu"></a>CMFCMenuBar::CreateFromMenu  
 Инициализирует [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта. Этот метод моделей `CMFCMenuBar` объекта после `HMENU` параметра.  
  
```  
virtual void CreateFromMenu(
    HMENU hMenu,  
    BOOL bDefaultMenu = FALSE,  
    BOOL bForceUpdate = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hMenu`  
 Дескриптор ресурса меню. `CreateFromMenu`использует этот ресурс в качестве шаблона для `CMFCMenuBar`.  
  
 [in] `bDefaultMenu`  
 Логическое значение, указывающее, является ли новое меню меню по умолчанию.  
  
 [in] `bForceUpdate`  
 Логическое значение, указывающее, является ли этот метод вызывает обновление меню.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, если элемент управления меню иметь одинаковые элементы меню как ресурс меню. Этот метод вызывается после вызова одной [CMFCMenuBar::Create](#create) или [CMFCMenuBar::CreateEx](#createex).  
  
##  <a name="enablehelpcombobox"></a>CMFCMenuBar::EnableHelpCombobox  
 Включает **справки** со списком, расположенный справа от строки меню.  
  
```  
void EnableHelpCombobox(
    UINT uiID,  
    LPCTSTR lpszPrompt = NULL,  
    int nComboBoxWidth = 150);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
 Идентификатор команды для кнопки **справки** поле со списком.  
  
 [in] `lpszPrompt`  
 Строка, содержащая текст, платформа отображает в поле со списком, если он является пустым и не активен. Например «введите здесь текст».  
  
 [in] `nComboBoxWidth`  
 Ширина кнопки для поля со списком в пикселях.  
  
### <a name="remarks"></a>Примечания  
 **Справки** напоминает списком **справки** поле со списком в строке меню [!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)].  
  
 При вызове этого метода с `uiID` задано значение 0, этот метод скрывает поле со списком. В противном случае этот метод поле со списком автоматически отображается на правой панели меню. После вызова этого метода необходимо вызвать [CMFCMenuBar::GetHelpCombobox](#gethelpcombobox) для получения указателя на вставленных [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) объекта.  
  
##  <a name="enablemenushadows"></a>CMFCMenuBar::EnableMenuShadows  
 Позволяет тени в контекстных меню.  
  
```  
static void EnableMenuShadows(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Логический параметр, указывает, следует ли включить тени в контекстных меню.  
  
### <a name="remarks"></a>Примечания  
 Алгоритм, который использует этот метод является сложной и может привести к снижению производительности приложения в медленных системах.  
  
##  <a name="getavailableexpandsize"></a>CMFCMenuBar::GetAvailableExpandSize  

  
```  
virtual int GetAvailableExpandSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getcolumnwidth"></a>CMFCMenuBar::GetColumnWidth  

  
```  
virtual int GetColumnWidth() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getdefaultmenu"></a>CMFCMenuBar::GetDefaultMenu  
 Получает дескриптор в исходное меню. Платформа исходное меню загружает из файла ресурсов.  
  
```  
HMENU GetDefaultMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор ресурса меню.  
  
### <a name="remarks"></a>Примечания  
 Если приложение настраивает меню, этот метод можно использовать для получения дескриптора в исходное меню.  
  
##  <a name="getdefaultmenuresid"></a>CMFCMenuBar::GetDefaultMenuResId  
 Извлекает идентификатор ресурса для меню по умолчанию.  
  
```  
UINT GetDefaultMenuResId() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор ресурса меню.  
  
### <a name="remarks"></a>Примечания  
 Платформа загружает меню по умолчанию для `CMFCMenuBar` объекта из файла ресурсов.  
  
##  <a name="getfloatpopupdirection"></a>CMFCMenuBar::GetFloatPopupDirection  

  
```  
int GetFloatPopupDirection(CMFCToolBarMenuButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getforcedownarrows"></a>CMFCMenuBar::GetForceDownArrows  

  
```  
BOOL GetForceDownArrows();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gethelpcombobox"></a>CMFCMenuBar::GetHelpCombobox  
 Возвращает указатель на **справки** поле со списком.  
  
```  
CMFCToolBarComboBoxButton* GetHelpCombobox();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на **справки** поле со списком. `NULL`Если **справки** списком скрыто или не включен.  
  
### <a name="remarks"></a>Примечания  
 **Справки** поле со списком находится справа от строки меню. Вызовите метод [CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox) для включения списком.  
  
##  <a name="gethmenu"></a>CMFCMenuBar::GetHMenu  
 Извлекает дескриптор меню, присоединенные к [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта.  
  
```  
HMENU GetHMenu() const;  
```  
  
##  <a name="getmenufont"></a>CMFCMenuBar::GetMenuFont  
 Извлекает текущий шрифт для меню.  
  
```  
static const CFont& GetMenuFont(BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bHorz`  
 Логический параметр, указывает, следует ли возвращать горизонтального или вертикального шрифта. `TRUE`Указывает горизонтальное шрифт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CFont](../../mfc/reference/cfont-class.md) параметра, который содержит текущий шрифт строки меню.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый шрифт имеет глобальных параметров для приложения. Глобальные шрифты сохраняются для всех `CMFCMenuBar` объектов. Эти отдельные шрифты используются для строки меню по горизонтали и вертикали.  
  
##  <a name="getmenuitem"></a>CMFCMenuBar::GetMenuItem  
 Извлекает [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) в строке меню в соответствии с индекс элемента.  
  
```  
CMFCToolBarButton* GetMenuItem(int iItem) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iItem`  
 Индекс возвращаемого элемента меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CMFCToolBarButton` объект, соответствующий индекс, заданный `iItem`. `NULL`Если индекс является недопустимым.  
  
##  <a name="getrowheight"></a>CMFCMenuBar::GetRowHeight  

  
```  
virtual int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getsystembutton"></a>CMFCMenuBar::GetSystemButton  

  
```  
CMFCToolBarMenuButtonsButton* GetSystemButton(
    UINT uiBtn,  
    BOOL bByCommand = TRUE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiBtn`  
 [in] `bByCommand`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getsystembuttonscount"></a>CMFCMenuBar::GetSystemButtonsCount  

  
```  
int GetSystemButtonsCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getsystemmenu"></a>CMFCMenuBar::GetSystemMenu  

  
```  
CMFCToolBarSystemMenuButton* GetSystemMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="highlightdisableditems"></a>CMFCMenuBar::HighlightDisabledItems  
 Определяет, выделяет ли платформа пунктов меню отключен.  
  
```  
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bHighlight`  
 Логический параметр, указывает ли платформа выделяет элементы меню недоступны.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа не выделяет элементы меню недоступны, при наведении указателя мыши над ними.  
  
##  <a name="isbuttonextrasizeavailable"></a>CMFCMenuBar::IsButtonExtraSizeAvailable  

  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ishighlightdisableditems"></a>CMFCMenuBar::IsHighlightDisabledItems  
 Указывает, выделяются ли платформа элементы меню недоступны.  
  
```  
static BOOL IsHighlightDisabledItems();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если элементы меню недоступны, выделяются; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа не выделяет элементы меню недоступны, при наведении указателя мыши над ними. Используйте [CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems) метод, чтобы включить эту функцию.  
  
##  <a name="ismenushadows"></a>CMFCMenuBar::IsMenuShadows  
 Указывает, является ли платформа, рисование с тенями в контекстных меню.  
  
```  
static BOOL IsMenuShadows();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если платформа Рисование с тенями меню; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCMenuBar::EnableMenuShadows](#enablemenushadows) метод, чтобы включить или отключить эту функцию.  
  
##  <a name="isrecentlyusedmenus"></a>CMFCMenuBar::IsRecentlyUsedMenus  
 Указывает, отображаются ли недавно используемым командам меню в строке меню.  
  
```  
static BOOL IsRecentlyUsedMenus();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CMFCMenuBar` объект отображает недавно использованных команд меню; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте функцию [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus) для управления ли в строке меню отображается недавно использованные команды меню.  
  
##  <a name="isshowallcommands"></a>CMFCMenuBar::IsShowAllCommands  
 Указывает, является ли меню отображаются все команды.  
  
```  
static BOOL IsShowAllCommands();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CMFCMenuBar` отображает все команды; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Объект `CMFCMenuBar` объект можно настроить отображение всех команд или Показать только часть команды. Дополнительные сведения об этой функции см. в разделе [CMFCMenuBar класса](../../mfc/reference/cmfcmenubar-class.md).  
  
 `IsShowAllCommands`Вы узнаете, как эта функция настраивается для `CMFCMenuBar` объекта. Чтобы контролировать, какие команды меню отображаются, используйте методы [CMFCMenuBar::SetShowAllCommands](#setshowallcommands) и [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus).  
  
##  <a name="isshowallcommandsdelay"></a>CMFCMenuBar::IsShowAllCommandsDelay  
 Указывает, является ли [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объект отображает все команды после короткой задержки.  
  
```  
static BOOL IsShowAllCommandsDelay();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если в строке меню отображается полные меню после короткой задержки; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 При настройке меню для отображения недавно использовавшихся элементов в меню отображает меню полностью одним из двух способов:  
  
-   Отображение полного меню после программируемых задержки из при наведении курсора на стрелку в нижней части меню.  
  
-   Отображение полного меню, при нажатии стрелки в нижней части меню.  
  
 По умолчанию все `CMFCMenuBar` объекты используют этот параметр для отображения полного меню после короткой задержки. Этот параметр нельзя изменить программным способом в `CMFCMenuBar` класса. Тем не менее, пользователь может изменить поведение во время настройки панели инструментов с помощью **Настройка** диалоговое окно...  
  
##  <a name="loadstate"></a>CMFCMenuBar::LoadState  
 Загружает состояние панели меню из реестра Windows.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Строка, содержащая путь к разделу реестра Windows.  
  
 [in] `nIndex`  
 Идентификатор элемента управления для строки меню.  
  
 [in] `uiID`  
 Зарезервированное значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCMenuBar::SaveState](#savestate) метод для сохранения состояния в меню реестр. Сохраненные данные включает элементы меню, состояние закрепления и позицию строки меню.  
  
 В большинстве случаев приложения не вызывает `LoadState`. Платформа вызывает этот метод во время инициализации рабочей области.  
  
##  <a name="onchangehot"></a>CMFCMenuBar::OnChangeHot  

  
```  
virtual void OnChangeHot(int iHot);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iHot`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondefaultmenuloaded"></a>CMFCMenuBar::OnDefaultMenuLoaded  
 Этот метод вызывается платформой при загрузке ресурсов меню из файла ресурсов.  
  
```  
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hMenu`  
 Дескриптор для меню присоединяется к `CMFCMenuBar` объекта.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию для выполнения пользовательского кода после платформа загружает ресурс меню из файла ресурсов.  
  
##  <a name="onsendcommand"></a>CMFCMenuBar::OnSendCommand  

  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onsetdefaultbuttontext"></a>CMFCMenuBar::OnSetDefaultButtonText  
 Этот метод вызывается платформой, когда пользователь изменяет текст элемента в строке меню.  
  
```  
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указатель на [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) объект, который требуется настроить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если платформа применяет изменения пользователя к строке меню; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию для этого метода изменения текста, где пользователь предоставляет текст кнопки.  
  
##  <a name="ontoolhittest"></a>CMFCMenuBar::OnToolHitTest  

  
```  
virtual INT_PTR OnToolHitTest(
    CPoint point,  
    TOOLINFO* pTI) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 [in] `pTI`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="pretranslatemessage"></a>CMFCMenuBar::PreTranslateMessage  

  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMsg`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="restoreoriginalstate"></a>CMFCMenuBar::RestoreOriginalstate  
 Вызывается платформой, когда пользователь выбирает **Сброс** из **Настройка** диалоговое окно.  
  
```  
virtual BOOL RestoreOriginalstate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, когда пользователь выбирает **Сброс** меню "настройки". Можно также вручную вызвать этот метод, чтобы программным образом сбросе состояния в меню. Этот метод загружает исходное состояние из файла ресурсов.  
  
 Переопределите этот метод, если вы хотите сделать какой-либо обработки, когда пользователь выбирает **Сброс** параметр.  
  
##  <a name="savestate"></a>CMFCMenuBar::SaveState  
 Сохраняет состояние [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта в реестр Windows.  
  
```  
virtual BOOL SaveState (
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Строка, содержащая путь к разделу реестра Windows.  
  
 [in] `nIndex`  
 Идентификатор элемента управления для строки меню.  
  
 [in] `uiID`  
 Зарезервированное значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`в случае успешного выполнения; в противном случае `FALSE`;  
  
### <a name="remarks"></a>Примечания  
 Как правило, приложение не вызывает `SaveState`. Этот метод вызывается платформой при сериализации рабочей области. Дополнительные сведения см. в разделе [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).  
  
 Сохраненные данные включает элементы меню, состояние закрепления и позицию строки меню.  
  
##  <a name="setdefaultmenuresid"></a>CMFCMenuBar::SetDefaultMenuResId  
 Задает меню по умолчанию для [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) в соответствии с его идентификатором ресурса.  
  
```  
void SetDefaultMenuResId(UINT uiResId);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiResId`  
 Идентификатор ресурса для нового меню по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 [CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate) метод восстанавливает меню по умолчанию из файла ресурсов.  
  
 Используйте [CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid) метод для извлечения меню по умолчанию без восстановления.  
  
##  <a name="setforcedownarrows"></a>CMFCMenuBar::SetForceDownArrows  

  
```  
void SetForceDownArrows(BOOL bValue);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bValue`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setmaximizemode"></a>CMFCMenuBar::SetMaximizeMode  
 Платформа вызывает этот метод, когда MDI изменяет его режим отображения и должны быть обновлены в меню.  
  
```  
void SetMaximizeMode(
    BOOL bMax,  
    CWnd* pWnd = NULL,  
    BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bMax`  
 Логическое значение, указывающее режим. Дополнительные сведения см. в разделе "Примечания".  
  
 [in] `pWnd`  
 Указатель на дочернее окно MDI, которой изменяется.  
  
 [in] `bRecalcLayout`  
 Логическое значение, указывающее, следует ли пересчитывать макета в меню сразу.  
  
### <a name="remarks"></a>Примечания  
 Если развернуто дочернего окна MDI, строка меню, прикрепленный к окну основного фрейма MDI отображает системное меню и **свернуть**, **развернуть** и **закрыть** кнопки. Если `bMax` — `TRUE` и `pWnd` не `NULL`, дочернее окно MDI-приложения развернуто и в меню должно содержать дополнительных элементов управления. В противном случае в меню возвращается в обычный состояние.  
  
##  <a name="setmenubuttonrtc"></a>CMFCMenuBar::SetMenuButtonRTC  
 Задает сведения о классе среды выполнения, платформа использует при создании пользователем кнопки меню.  
  
```  
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMenuButtonRTC`  
 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) сведения для класса, производным от [класс CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md).  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь добавляет новые кнопки строки меню, платформа создает кнопки динамически. По умолчанию создает `CMFCMenuButton` объектов. Переопределите этот метод, чтобы изменить тип кнопки объектов, которые платформа создает.  
  
##  <a name="setmenufont"></a>CMFCMenuBar::SetMenuFont  
 Задает шрифт для всех строк меню в приложении.  
  
```  
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpLogFont`  
 Указатель на [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/bb773327) структура, определяющая шрифта для задания.  
  
 [in] `bHorz`  
 Значение TRUE, если `lpLogFont` параметр, используемый для вертикального шрифта, FALSE, если требуется использовать для шрифта по горизонтали.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Шрифты, используемые для всех `CMFCMenuBar` объектов. Эти отдельные шрифты используются для строки меню по горизонтали и вертикали.  
  
 Параметры шрифта глобальные переменные и влияют на все `CMFCMenuBar` объектов.  
  
##  <a name="setrecentlyusedmenus"></a>CMFCMenuBar::SetRecentlyUsedMenus  
 Определяет, отображается ли строка меню недавно использованные команды меню.  
  
```  
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bOn`  
 Логическое значение, управляющее отображением команды меню недавно использованных.  
  
##  <a name="setshowallcommands"></a>CMFCMenuBar::SetShowAllCommands  
 Определяет, отображаются ли меню все доступные команды.  
  
```  
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShowAllCommands`  
 Логический параметр, указывает, отображаются ли всплывающие меню всех команд меню.  
  
### <a name="remarks"></a>Примечания  
 Если меню не отображает все команды меню, он скрывает команд, которые используются редко. Дополнительные сведения об отображении команды меню см. в разделе [CMFCMenuBar класса](../../mfc/reference/cmfcmenubar-class.md).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
