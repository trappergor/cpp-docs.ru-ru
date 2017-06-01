---
title: "Класс CMFCMenuBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuBar class
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
caps.latest.revision: 36
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ab2896f5ebab0df894f70e5ddb85bae3a5e1d5af
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcmenubar-class"></a>Класс CMFCMenuBar
Строка меню, которая реализует закрепление.  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCMenuBar : public CMFCToolbar  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCMenuBar::AdjustLocations](#adjustlocations)|(Переопределяет `CMFCToolBar::AdjustLocations`.)|  
|[CMFCMenuBar::AllowChangeTextLabels](#allowchangetextlabels)|Указывает, может ли отображаться текстовые метки в списке изображений на кнопках панели инструментов. (Переопределяет [CMFCToolBar::AllowChangeTextLabels](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels).)|  
|[CMFCMenuBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Переопределяет `CPane::AllowShowOnPaneMenu`.)|  
|[CMFCMenuBar::CalcFixedLayout](#calcfixedlayout)|Вычисляет размер по горизонтали на панели инструментов. (Переопределяет [CMFCToolBar::CalcFixedLayout](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout).)|  
|[CMFCMenuBar::CalcLayout](#calclayout)|(Переопределяет `CMFCToolBar::CalcLayout`.)|  
|[CMFCMenuBar::CalcMaxButtonHeight](#calcmaxbuttonheight)|Вычисляет Максимальная высота кнопки на панели инструментов. (Переопределяет [CMFCToolBar::CalcMaxButtonHeight](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight).)|  
|[CMFCMenuBar::CanBeClosed](#canbeclosed)|Указывает, может ли пользователь закрыть панели инструментов. (Переопределяет [CMFCToolBar::CanBeClosed](../../mfc/reference/cmfctoolbar-class.md#canbeclosed).)|  
|[CMFCMenuBar::CanBeRestored](#canberestored)|Определяет ли система восстановить панели инструментов в исходное состояние после настройки. (Переопределяет [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|  
|[CMFCMenuBar::Create](#create)|Создает элемент управления menu и присоединяет его к `CMFCMenuBar` объекта.|  
|[CMFCMenuBar::CreateEx](#createex)|Создает `CMFCMenuBar` объекта с дополнительными возможностями параметрами.|  
|[CMFCMenuBar::CreateFromMenu](#createfrommenu)|Инициализирует `CMFCMenuBar` объекта. Принимает `HMENU` параметр, который действует как шаблон для заполненного `CMFCMenuBar`.|  
|[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)|Позволяет **помочь** поле со списком, расположенный справа от строки меню.|  
|[CMFCMenuBar::EnableMenuShadows](#enablemenushadows)|Признак отображения тени для всплывающих меню.|  
|[CMFCMenuBar::GetAvailableExpandSize](#getavailableexpandsize)|(Переопределяет [CPane::GetAvailableExpandSize](../../mfc/reference/cpane-class.md#getavailableexpandsize).)|  
|[CMFCMenuBar::GetColumnWidth](#getcolumnwidth)|Возвращает ширину кнопки панели инструментов. (Переопределяет [CMFCToolBar::GetColumnWidth](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth).)|  
|[CMFCMenuBar::GetDefaultMenu](#getdefaultmenu)|Возвращает дескриптор в исходное меню в файле ресурсов.|  
|[CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)|Возвращает идентификатор ресурса для исходное меню в файле ресурсов.|  
|[CMFCMenuBar::GetFloatPopupDirection](#getfloatpopupdirection)||  
|[CMFCMenuBar::GetForceDownArrows](#getforcedownarrows)||  
|[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox)|Возвращает указатель на **помочь** поле со списком.|  
|[CMFCMenuBar::GetHMenu](#gethmenu)|Возвращает дескриптор меню, к которому присоединена `CMFCMenuBar` объекта.|  
|[CMFCMenuBar::GetMenuFont](#getmenufont)|Возвращает текущий шрифт глобальных объектов меню.|  
|[CMFCMenuBar::GetMenuItem](#getmenuitem)|Возвращает кнопки панели инструментов, связанные с индекс указанного элемента.|  
|[CMFCMenuBar::GetRowHeight](#getrowheight)|Возвращает высоту кнопки панели инструментов. (Переопределяет [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|  
|[CMFCMenuBar::GetSystemButton](#getsystembutton)||  
|[CMFCMenuBar::GetSystemButtonsCount](#getsystembuttonscount)||  
|[CMFCMenuBar::GetSystemMenu](#getsystemmenu)||  
|[CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)|Указывает, выделяются ли запрещенным командам.|  
|[CMFCMenuBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Определяет, может ли отображать кнопки, расширена границы панели инструментов. (Переопределяет [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|  
|[CMFCMenuBar::IsHighlightDisabledItems](#ishighlightdisableditems)|Указывает, выделяются ли отключенных элементов.|  
|[CMFCMenuBar::IsMenuShadows](#ismenushadows)|Указывает, отображаются ли тени для всплывающих меню.|  
|[CMFCMenuBar::IsRecentlyUsedMenus](#isrecentlyusedmenus)|Указывает, отображаются ли недавно используемым командам меню в строке меню.|  
|[CMFCMenuBar::IsShowAllCommands](#isshowallcommands)|Указывает, отображать ли всплывающие меню всех команд.|  
|[CMFCMenuBar::IsShowAllCommandsDelay](#isshowallcommandsdelay)|Указывает, является ли меню отображаются все команды после короткой задержки.|  
|[CMFCMenuBar::LoadState](#loadstate)|Загружает состояние `CMFCMenuBar` объекта из реестра.|  
|[CMFCMenuBar::OnChangeHot](#onchangehot)|Вызывается платформой, когда пользователь выбирает кнопку на панели инструментов. (Переопределяет [CMFCToolBar::OnChangeHot](../../mfc/reference/cmfctoolbar-class.md#onchangehot).)|  
|[CMFCMenuBar::OnDefaultMenuLoaded](#ondefaultmenuloaded)|Вызывается инфраструктурой при загрузке фрейма окна меню по умолчанию из файла ресурсов.|  
|[CMFCMenuBar::OnSendCommand](#onsendcommand)|(Переопределяет `CMFCToolBar::OnSendCommand`.)|  
|[CMFCMenuBar::OnSetDefaultButtonText](#onsetdefaultbuttontext)|Вызывается инфраструктурой при меню находится в режиме настройки, и пользователь изменяет текст пункта меню.|  
|[CMFCMenuBar::OnToolHitTest](#ontoolhittest)|(Переопределяет `CMFCToolBar::OnToolHitTest`.)|  
|[CMFCMenuBar::PreTranslateMessage](#pretranslatemessage)|(Переопределяет `CMFCToolBar::PreTranslateMessage`.)|  
|[CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate)|Вызывается инфраструктурой при меню находится в режиме настройки, а пользователь выбирает **Сброс** для строки меню.|  
|[CMFCMenuBar::SaveState](#savestate)|Сохраняет состояние `CMFCMenuBar` объекта в реестре.|  
|[CMFCMenuBar::SetDefaultMenuResId](#setdefaultmenuresid)|Задает исходное меню в файле ресурсов.|  
|[CMFCMenuBar::SetForceDownArrows](#setforcedownarrows)||  
|[CMFCMenuBar::SetMaximizeMode](#setmaximizemode)|Вызывается платформой, изменения его режима отображения дочернего окна MDI. Если дочернего окна MDI вновь развернута или больше не развернуто, этот метод обновляет меню.|  
|[CMFCMenuBar::SetMenuButtonRTC](#setmenubuttonrtc)|Задает информацию о класса среды выполнения, которая создается, когда пользователь создает динамически кнопки меню.|  
|[CMFCMenuBar::SetMenuFont](#setmenufont)|Задает шрифт для всех меню в приложении.|  
|[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)|Указывает, отображается ли строка меню недавно использованных команд.|  
|[CMFCMenuBar::SetShowAllCommands](#setshowallcommands)|Указывает, отображается ли меню все команды.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCMenuBar` Класс является строка меню, которая реализует функции закрепления. Он напоминает панель инструментов, несмотря на то, что он не может быть закрыт — всегда отображается.  
  
 `CMFCMenuBar`поддерживает параметр отображения объектов меню недавно использовавшихся элементов. Если этот параметр включен, `CMFCMenuBar` отображается только подмножество доступных команд на первом просмотре. После этого отображаются последние использованные команды, а также исходный набор команд. Кроме того пользователь всегда может развернуть меню, чтобы просмотреть все доступные команды. Таким образом всех доступных команд настраивается для отображения постоянно или для отображения только в том случае, если недавно был выбран.  
  
 Для использования `CMFCMenuBar` объекта, внедрить его в объект фрейма главного окна. При обработке `WM_CREATE` сообщений, вызовите метод `CMFCMenuBar::Create` или `CMFCMenuBar::CreateEx`. Независимо от того, что создать функцию использовать, следует передать указатель фрейма главного окна. Затем включите закрепление путем вызова [CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking). Закрепить это меню путем вызова [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane).  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CMFCMenuBar` класса. Пример показано, как задать стиль области, включить кнопку Настройка, включение окно справки, тени для всплывающих меню и обновлять меню. Этот фрагмент кода является частью [IE демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo&#3;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_2.cpp)]  
  
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
 Определяет, могут ли метки текст под изображениями в строке меню.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` , если пользователь может выбирать для отображения текстовых меток в списке изображений.  
  
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
 Создает элемент управления menu и присоединяет его к [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта.  
  
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
 После создания `CMFCMenuBar` объекта необходимо вызвать метод `Create`. Этот метод создает `CMFCMenuBar` управления и присоединяет его к `CMFCMenuBar` объекта.  
  
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
 Дополнительные стили для новой строки меню.  
  
 [in] `dwStyle`  
 Основной стиль новое меню.  
  
 [in] `rcBorders`  
 Объект `CRect` параметр, который задает размеры для границ `CMFCMenuBar` объекта.  
  
 [in] `nID`  
 Идентификатор дочернего окна в строке меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Следует использовать эту функцию вместо [CMFCMenuBar::Create](#create) , если требуется указать стили помимо стиль панели инструментов. Некоторые часто используемые стили дополнительных `TBSTYLE_TRANSPARENT` и `CBRS_TOP`.  
  
 Списки дополнительных стилей см. в разделе [панели инструментов и стили кнопок](http://msdn.microsoft.com/library/windows/desktop/bb760439), [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498), и [общие стили окна](http://msdn.microsoft.com/library/windows/desktop/ms632600).  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `CreateEx` метод `CMFCMenuBar` класса. Этот фрагмент кода является частью [IE демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]  
  
##  <a name="createfrommenu"></a>CMFCMenuBar::CreateFromMenu  
 Инициализирует [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта. Этот метод моделей `CMFCMenuBar` объекта после `HMENU` параметр.  
  
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
 Используйте этот метод, если вы хотите иметь такие же пункты меню как ресурс меню элемента управления меню. Этот метод вызывается после вызова либо [CMFCMenuBar::Create](#create) или [CMFCMenuBar::CreateEx](#createex).  
  
##  <a name="enablehelpcombobox"></a>CMFCMenuBar::EnableHelpCombobox  
 Позволяет **помочь** поле со списком, расположенный справа от строки меню.  
  
```  
void EnableHelpCombobox(
    UINT uiID,  
    LPCTSTR lpszPrompt = NULL,  
    int nComboBoxWidth = 150);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
 Идентификатор команды для кнопки **помочь** поле со списком.  
  
 [in] `lpszPrompt`  
 Строка, содержащая текст, отображаемый платформы в поле со списком, если он пустой и не активен. Например «введите здесь текст».  
  
 [in] `nComboBoxWidth`  
 Ширина кнопки для поля со списком в пикселях.  
  
### <a name="remarks"></a>Примечания  
 **Помочь** списком напоминает **помочь** поле со списком на панели меню [!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)].  
  
 При вызове этого метода с `uiID` задано значение 0, этот метод скрывает поле со списком. В противном случае, этот метод отображает поле со списком автоматически справа в строке меню. После вызова этого метода необходимо вызвать [CMFCMenuBar::GetHelpCombobox](#gethelpcombobox) для получения указателя вставленных [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) объекта.  
  
##  <a name="enablemenushadows"></a>CMFCMenuBar::EnableMenuShadows  
 Позволяет тени для всплывающих меню.  
  
```  
static void EnableMenuShadows(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Логический параметр, указывающий, включены ли тени для всплывающих меню.  
  
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
 Получает дескриптор в исходное меню. Платформа framework загружает исходное меню из файла ресурсов.  
  
```  
HMENU GetDefaultMenu() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор ресурса меню.  
  
### <a name="remarks"></a>Примечания  
 Если приложение настраивает меню, этот метод можно использовать для получения дескриптора в исходное меню.  
  
##  <a name="getdefaultmenuresid"></a>CMFCMenuBar::GetDefaultMenuResId  
 Получает идентификатор ресурса для меню по умолчанию.  
  
```  
UINT GetDefaultMenuResId() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор ресурса меню.  
  
### <a name="remarks"></a>Примечания  
 Платформа framework загружает меню по умолчанию для `CMFCMenuBar` из файла ресурсов.  
  
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
 Возвращает указатель на **помочь** поле со списком.  
  
```  
CMFCToolBarComboBoxButton* GetHelpCombobox();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на **помочь** поле со списком. `NULL`Если **помочь** списком скрыто или не включен.  
  
### <a name="remarks"></a>Примечания  
 **Помочь** поле со списком находится справа от строки меню. Вызовите метод [CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox) для включения списком.  
  
##  <a name="gethmenu"></a>CMFCMenuBar::GetHMenu  
 Получает дескриптор меню, подключенное к [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта.  
  
```  
HMENU GetHMenu() const;  
```  
  
##  <a name="getmenufont"></a>CMFCMenuBar::GetMenuFont  
 Извлекает текущий шрифт меню.  
  
```  
static const CFont& GetMenuFont(BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bHorz`  
 Логический параметр, который указывает, следует ли возвращать горизонтального или вертикального шрифта. `TRUE`Указывает горизонтальное шрифт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CFont](../../mfc/reference/cfont-class.md) параметра, который содержит текущий шрифт панели меню.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый шрифт является глобальных параметров для приложения. Глобальные шрифты сохраняются для всех `CMFCMenuBar` объектов. Эти отдельные шрифты используются для меню горизонтальных и вертикальных полос.  
  
##  <a name="getmenuitem"></a>CMFCMenuBar::GetMenuItem  
 Извлекает [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) в строке меню на основе индекса элемента.  
  
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
 Определяет, выделяет ли платформа запрещенным командам.  
  
```  
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bHighlight`  
 Логический параметр, указывающий, выделяет ли платформа элементы меню недоступны.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа не выделяет элементы меню недоступны при наведении указателя мыши на них.  
  
##  <a name="isbuttonextrasizeavailable"></a>CMFCMenuBar::IsButtonExtraSizeAvailable  

  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ishighlightdisableditems"></a>CMFCMenuBar::IsHighlightDisabledItems  
 Указывает, выделяет ли платформа элементы меню недоступны.  
  
```  
static BOOL IsHighlightDisabledItems();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если выделены элементы меню недоступны; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию платформа не выделяет элементы меню недоступны при наведении указателя мыши на них. Используйте [CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems) метод, чтобы включить эту функцию.  
  
##  <a name="ismenushadows"></a>CMFCMenuBar::IsMenuShadows  
 Указывает ли платформа Рисование с тенями всплывающих меню.  
  
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
 Ненулевое значение, если `CMFCMenuBar` объект показан недавно использованных команд меню; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте функцию [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus) для управления ли в строке меню отображается недавно использованные команды меню.  
  
##  <a name="isshowallcommands"></a>CMFCMenuBar::IsShowAllCommands  
 Указывает, является ли меню отображаются все команды.  
  
```  
static BOOL IsShowAllCommands();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если `CMFCMenuBar` выводит список всех команд; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Объект `CMFCMenuBar` объект можно настроить на отображение всех команд или Показать только подмножество команд. Дополнительные сведения об этой функции см. в разделе [CMFCMenuBar класса](../../mfc/reference/cmfcmenubar-class.md).  
  
 `IsShowAllCommands`сообщает о том, как этот компонент настроен для `CMFCMenuBar` объекта. Чтобы контролировать, какие команды меню отображаются, используйте методы [CMFCMenuBar::SetShowAllCommands](#setshowallcommands) и [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus).  
  
##  <a name="isshowallcommandsdelay"></a>CMFCMenuBar::IsShowAllCommandsDelay  
 Указывает, является ли [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) объекта отображаются все команды после короткой задержки.  
  
```  
static BOOL IsShowAllCommandsDelay();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если в строке меню отображается полные меню после короткой задержки; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 При настройке меню для недавно использовавшихся элементов меню отображается полное меню одним из двух способов:  
  
-   Отображение полного меню задержкой запрограммированных из при наведении курсора на стрелку в нижней части меню.  
  
-   Отображение полного меню при нажатии стрелки в нижней части меню.  
  
 По умолчанию все `CMFCMenuBar` объекты параметр используется для отображения полного меню после короткой задержки. Этот параметр не может изменяться программно в `CMFCMenuBar` класса. Тем не менее, пользователь может изменить поведение во время настройки панели инструментов с помощью **Настройка** диалоговое окно...  
  
##  <a name="loadstate"></a>CMFCMenuBar::LoadState  
 Загружает состояние элемента меню из реестра Windows.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Строка, содержащая путь реестра Windows.  
  
 [in] `nIndex`  
 Идентификатор элемента управления меню.  
  
 [in] `uiID`  
 Зарезервированное значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод был выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CMFCMenuBar::SaveState](#savestate) метод для сохранения состояния в меню реестр. Сохраненные сведения включает элементы меню, состояние закрепления и позиции в строке меню.  
  
 В большинстве случаев приложения не вызывает `LoadState`. Платформа вызывает этот метод при инициализации рабочей области.  
  
##  <a name="onchangehot"></a>CMFCMenuBar::OnChangeHot  

  
```  
virtual void OnChangeHot(int iHot);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iHot`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondefaultmenuloaded"></a>CMFCMenuBar::OnDefaultMenuLoaded  
 Платформа вызывает этот метод при загрузке ресурсов меню из файла ресурсов.  
  
```  
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hMenu`  
 Дескриптор для меню присоединен к `CMFCMenuBar` объекта.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию для выполнения пользовательского кода после framework загружает ресурс меню из файла ресурсов.  
  
##  <a name="onsendcommand"></a>CMFCMenuBar::OnSendCommand  

  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onsetdefaultbuttontext"></a>CMFCMenuBar::OnSetDefaultButtonText  
 Платформа вызывает этот метод, когда пользователь изменяет текст элемента в строке меню.  
  
```  
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указатель на [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) объект, который необходимо настроить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если платформа применяет изменения пользователя меню; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию для этого метода изменяет текст кнопки, текст, который предоставляет пользователю.  
  
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
 Этот метод вызывается, когда пользователь выбирает **Сброс** меню настройки. Можно также вручную вызвать этот метод, чтобы сбросить состояние меню программными средствами. Этот метод загружает исходное состояние из файла ресурсов.  
  
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
 Строка, содержащая путь реестра Windows.  
  
 [in] `nIndex`  
 Идентификатор элемента управления меню.  
  
 [in] `uiID`  
 Зарезервированное значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`в случае успешного выполнения; в противном случае `FALSE`;  
  
### <a name="remarks"></a>Примечания  
 Как правило, приложения не вызывает `SaveState`. Платформа вызывает этот метод при сериализации рабочей области. Дополнительные сведения см. в разделе [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).  
  
 Сохраненные сведения включает элементы меню, состояние закрепления и позиции в строке меню.  
  
##  <a name="setdefaultmenuresid"></a>CMFCMenuBar::SetDefaultMenuResId  
 Задает меню по умолчанию для [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) в соответствии с идентификатором ресурса.  
  
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
 Платформа вызывает этот метод при MDI изменения его режима отображения и должны быть обновлены на панели меню.  
  
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
 Указатель дочернего окна MDI, которой изменяется.  
  
 [in] `bRecalcLayout`  
 Логическое значение, указывающее, должны быть пересчитаны макет меню немедленно.  
  
### <a name="remarks"></a>Примечания  
 Если дочерних MDI-окно развернуто, строка меню, присоединенные к окну основного фрейма MDI отображает меню системы и **свернуть**, **развернуть** и **закрыть** кнопки. Если `bMax` — `TRUE` и `pWnd` не `NULL`меню необходимо включить дополнительные элементы управления и развернуто дочернего окна MDI. В противном случае — меню возвращается в обычный состояние.  
  
##  <a name="setmenubuttonrtc"></a>CMFCMenuBar::SetMenuButtonRTC  
 Задает сведения класса среды выполнения, платформа использует при создании пользователем кнопки меню.  
  
```  
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMenuButtonRTC`  
 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) сведения для класса, производным от [CMFCMenuButton класса](../../mfc/reference/cmfcmenubutton-class.md).  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь добавляет новые кнопки в строке меню, платформа создает кнопки динамически. По умолчанию создает `CMFCMenuButton` объектов. Переопределите этот метод, чтобы изменить тип объектов button, платформа создает.  
  
##  <a name="setmenufont"></a>CMFCMenuBar::SetMenuFont  
 Задает шрифт для всех строк меню в приложении.  
  
```  
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpLogFont`  
 Указатель на [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/bb773327) структура, определяющая шрифт для задания.  
  
 [in] `bHorz`  
 Значение TRUE, если `lpLogFont` параметр, используемый для вертикального шрифта, FALSE, если требуется использовать для горизонтального шрифта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод был выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Шрифты используются для всех `CMFCMenuBar` объектов. Эти отдельные шрифты используются для меню горизонтальных и вертикальных полос.  
  
 Параметры шрифта глобальные переменные и влияют на все `CMFCMenuBar` объектов.  
  
##  <a name="setrecentlyusedmenus"></a>CMFCMenuBar::SetRecentlyUsedMenus  
 Элементы управления ли строка меню отображает последние использованные команды меню.  
  
```  
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bOn`  
 Логическое значение, определяющее, отображаются ли недавно использованных команд.  
  
##  <a name="setshowallcommands"></a>CMFCMenuBar::SetShowAllCommands  
 Определяет, отображается ли меню всех доступных команд.  
  
```  
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShowAllCommands`  
 Логический параметр, который указывает, отображаются ли всплывающие меню все команды меню.  
  
### <a name="remarks"></a>Примечания  
 Если меню не отображает все команды меню, он скрывает команды, которые используются редко. Дополнительные сведения об отображении команды меню в разделе [CMFCMenuBar класса](../../mfc/reference/cmfcmenubar-class.md).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

