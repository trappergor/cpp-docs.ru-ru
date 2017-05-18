---
title: "Класс COleIPFrameWndEx | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleIPFrameWndEx
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AddDockSite
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AddPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AdjustDockingLayout
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::DockPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::DockPaneLeftOf
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnableAutoHidePanes
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnableDocking
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnablePaneMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetActivePopup
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetContainerFrameWindow
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDefaultResId
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDockFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDockingManager
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetMainFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetMenuBar
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetTearOffBars
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetToolbarButtonToolTipText
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::InsertPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::IsMenuBarAvailable
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::IsPointNearDockSite
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::LoadFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCloseDockingPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCloseMiniFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnClosePopupMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCmdMsg
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnDrawMenuImage
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnDrawMenuLogo
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnMenuButtonToolHitTest
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnMoveMiniFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnSetPreviewMode
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowCustomizePane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowPanes
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowPopupMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnTearOffMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::PaneFromPoint
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::PreTranslateMessage
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::RecalcLayout
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::RemovePaneFromDockManager
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::SetDockState
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::SetupToolbarMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::ShowPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::WinHelpA
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::InitUserToobars
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWndEx class
ms.assetid: ebff1560-a1eb-4854-af00-95d4a192bd55
caps.latest.revision: 34
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5eec8e3a9cc4ad71a1ee3de9f6d5f25cffef1242
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="coleipframewndex-class"></a>Класс COleIPFrameWndEx
Класс `COleIPFrameWndEx` реализует OLE-контейнер с поддержкой MFC. Необходимо создать производный класс фреймового окна приложения из `COleIPFrameWndEx` класса вместо наследования его из [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleIPFrameWndEx : public COleIPFrameWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleIPFrameWndEx::AddDockSite](#adddocksite)||  
|[COleIPFrameWndEx::AddPane](#addpane)||  
|[COleIPFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)||  
|[COleIPFrameWndEx::DockPane](#dockpane)||  
|[COleIPFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|Закрепляет одну область слева от другой области.|  
|[COleIPFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)||  
|[COleIPFrameWndEx::EnableDocking](#enabledocking)||  
|[COleIPFrameWndEx::EnablePaneMenu](#enablepanemenu)||  
|[COleIPFrameWndEx::GetActivePopup](#getactivepopup)|Возвращает указатель на отображаемое в данный момент контекстное меню.|  
|[COleIPFrameWndEx::GetContainerFrameWindow](#getcontainerframewindow)||  
|[COleIPFrameWndEx::GetDefaultResId](#getdefaultresid)|Возвращает заданный при загрузке окна идентификатор ресурса для окна фрейма.|  
|[COleIPFrameWndEx::GetDockFrame](#getdockframe)||  
|[COleIPFrameWndEx::GetDockingManager](#getdockingmanager)||  
|[COleIPFrameWndEx::GetMainFrame](#getmainframe)||  
|[COleIPFrameWndEx::GetMenuBar](#getmenubar)|Возвращает указатель на объект строки меню, прикрепленное к окну фрейма.|  
|[COleIPFrameWndEx::GetPane](#getpane)||  
|[COleIPFrameWndEx::GetTearOffBars](#gettearoffbars)|Возвращает список объектов области, которые находятся в состоянии перемещения.|  
|[COleIPFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|Вызывается платформой перед отображением подсказки для кнопки.|  
|[COleIPFrameWndEx::InsertPane](#insertpane)||  
|[COleIPFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|Определяет, что указатель на объект строки меню не имеет значение `NULL`.|  
|[COleIPFrameWndEx::IsPointNearDockSite](#ispointneardocksite)||  
|[COleIPFrameWndEx::LoadFrame](#loadframe)|(Переопределяет `COleIPFrameWnd::LoadFrame`.)|  
|[COleIPFrameWndEx::OnCloseDockingPane](#onclosedockingpane)||  
|[COleIPFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)||  
|[COleIPFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|Вызывается платформой, когда активное всплывающее меню обрабатывает сообщение WM_DESTROY.|  
|[COleIPFrameWndEx::OnCmdMsg](#oncmdmsg)|(Переопределяет `CFrameWnd::OnCmdMsg`.)|  
|[COleIPFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|Вызывается платформой при отрисовке изображения, связанного с пунктом меню.|  
|[COleIPFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|Вызывается инфраструктурой при [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)объект обрабатывает сообщение WM_PAINT.|  
|[COleIPFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|Вызывается инфраструктурой при [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)объектов процессов WM_NCHITTEST сообщение.|  
|[COleIPFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)||  
|[COleIPFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|Вызов этой функции-члена переключает окно главного фрейма приложения в режим предварительного просмотра и из него. (Переопределяет [CFrameWnd::OnSetPreviewMode](../../mfc/reference/cframewnd-class.md#onsetpreviewmode).)|  
|[COleIPFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)||  
|[COleIPFrameWndEx::OnShowPanes](#onshowpanes)||  
|[COleIPFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|Вызывается платформой при активации всплывающего меню.|  
|[COleIPFrameWndEx::OnTearOffMenu](#ontearoffmenu)|Вызывается платформой при активации меню с перемещаемой панелью.|  
|[COleIPFrameWndEx::PaneFromPoint](#panefrompoint)||  
|[COleIPFrameWndEx::PreTranslateMessage](#pretranslatemessage)|(Переопределяет `COleIPFrameWnd::PreTranslateMessage`.)|  
|[COleIPFrameWndEx::RecalcLayout](#recalclayout)|(Переопределяет `COleIPFrameWnd::RecalcLayout`.)|  
|[COleIPFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)||  
|[COleIPFrameWndEx::SetDockState](#setdockstate)|Применяет указанное состояние закрепления к областям, принадлежащим окну фрейма.|  
|[COleIPFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|Изменяет объект панели инструментов путем поиска фиктивных элементов и замены их указанными элементами, определяемыми пользователем.|  
|[COleIPFrameWndEx::ShowPane](#showpane)||  
|[COleIPFrameWndEx::WinHelpA](#winhelpa)|Вызывается платформой для запуска приложения WinHelp или контекстной справки.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleIPFrameWndEx::InitUserToobars](#initusertoobars)|Дает платформе команду инициализировать диапазон идентификаторов элементов управления, которые назначены панелям инструментов, определяемым пользователем.|  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как создать подкласс экземпляра класса `COleIPFrameWndEx` и переопределить его методы. В примере демонстрируется переопределение методов `OnDestory` , `RepositionFrame` , `RecalcLayout` и `CalcWindowRect` . Этот фрагмент кода является частью [Word Pad образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&#1;](../../mfc/reference/codesnippet/cpp/coleipframewndex-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)  
  
 [COleIPFrameWndEx](../../mfc/reference/coleipframewndex-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxoleipframewndex.h  
  
##  <a name="adddocksite"></a>COleIPFrameWndEx::AddDockSite  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AddDockSite();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="addpane"></a>COleIPFrameWndEx::AddPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pControlBar`  
 [in] `bTail`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="adjustdockinglayout"></a>COleIPFrameWndEx::AdjustDockingLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `hdwp`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="dockpane"></a>COleIPFrameWndEx::DockPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 [in] `nDockBarID`  
 [in] `lpRect`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="dockpaneleftof"></a>COleIPFrameWndEx::DockPaneLeftOf  
 Закрепляет одну область слева от другой области.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на панели, чтобы закрепить.  
  
 [in] `pLeftOf`  
 Указатель для области, которая выступает в качестве источника.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` , если операция выполнена успешно. В противном случае возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для прикрепления нескольких объектов области в заранее определенном порядке. Этот метод закрепляет область, определяемое `pBar` слева от области, определяемой `pLeftOf`.  
  
##  <a name="enableautohidepanes"></a>COleIPFrameWndEx::EnableAutoHidePanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwDockStyle`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enabledocking"></a>COleIPFrameWndEx::EnableDocking  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwDockStyle`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enablepanemenu"></a>COleIPFrameWndEx::EnablePaneMenu  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void EnablePaneMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeLabel,  
    UINT uiViewToolbarsMenuEntryID,  
    BOOL bContextMenuShowsToolbarsOnly = FALSE,  
    BOOL bViewMenuShowsToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 [in] `uiCustomizeCmd`  
 [in] `strCustomizeLabel`  
 [in] `uiViewToolbarsMenuEntryID`  
 [in] `bContextMenuShowsToolbarsOnly`  
 [in] `bViewMenuShowsToolbarsOnly`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getactivepopup"></a>COleIPFrameWndEx::GetActivePopup  
 Возвращает указатель на текущую отображаемую во всплывающем меню.  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на активный во всплывающем меню. в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы получить указатель на [CMFCPopupMenu класс](../../mfc/reference/cmfcpopupmenu-class.md) объекта, который отображается в данный момент.  
  
##  <a name="getcontainerframewindow"></a>COleIPFrameWndEx::GetContainerFrameWindow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
COleCntrFrameWndEx* GetContainerFrameWindow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getdefaultresid"></a>COleIPFrameWndEx::GetDefaultResId  
 Возвращает идентификатор ресурса меню, который был указан при загрузке меню в окне фрейма.  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает идентификатор ресурса меню или 0, если нет строки меню окна фрейма.  
  
### <a name="remarks"></a>Примечания  
 Вызов эту функцию, чтобы получить идентификатор ресурса, который был указан при загрузке ресурсов меню таблицы фрейме окна путем вызова `COleIPFrameWndEx::LoadFrame`.  
  
##  <a name="getdockframe"></a>COleIPFrameWndEx::GetDockFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CFrameWnd* GetDockFrame();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getdockingmanager"></a>COleIPFrameWndEx::GetDockingManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getmainframe"></a>COleIPFrameWndEx::GetMainFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CFrameWnd* GetMainFrame();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getmenubar"></a>COleIPFrameWndEx::GetMenuBar  
 Возвращает указатель на объект строки меню, прикрепленное к окну фрейма.  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект панели меню.  
  
### <a name="remarks"></a>Примечания  
 Эта функция позволяет получить указатель на объект панели меню, к которой принадлежит `COleIPFrameWndEx` объекта.  
  
##  <a name="getpane"></a>COleIPFrameWndEx::GetPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettearoffbars"></a>COleIPFrameWndEx::GetTearOffBars  
 Возвращает список объектов области, которые находятся в состоянии перемещения.  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на `CObList` объект, содержащий коллекцию ссылок на [CBasePane класса](../../mfc/reference/cbasepane-class.md)-производных объектов.  
  
### <a name="remarks"></a>Примечания  
 `COleIPFrameWndEx` Объект поддерживает коллекцию перемещаемое меню как список [CBasePane класса](../../mfc/reference/cbasepane-class.md)-производных объектов. Используйте этот метод, чтобы получить ссылку на этот список.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>COleIPFrameWndEx::GetToolbarButtonToolTipText  
 Вызывается платформой перед отображением подсказки для кнопки.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pButton`  
 Указатель на кнопку.  
  
 [in] `strTTText`  
 Указатель на текст всплывающей подсказки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки отображения подсказки для кнопки панели инструментов.  
  
##  <a name="initusertoobars"></a>COleIPFrameWndEx::InitUserToobars  
 Задает диапазон идентификаторов, платформа назначает пользовательские панели инструментов элемента управления.  
  
```  
void InitUserToolbars(
    LPCTSTR lpszRegEntry,   
    UINT uiUserToolbarFirst,   
    UINT uiUserToolbarLast)  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszRegEntry`  
 Запись реестра, где в библиотеке хранятся параметры панели инструментов для пользователя.  
  
 [in] `uiUserToolbarFirst`  
 Идентификатор элемента управления, назначенные первой пользовательской панели инструментов.  
  
 [in] `uiUserToolbarLast`  
 Идентификатор элемента управления, назначенном панели инструментов последние определяемых пользователем.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для инициализации диапазона идентификаторов элементов управления для назначения панели инструментов, которые динамически определить пользователей. Параметры `uiUserToolbarFirst` и `uiUserToolbarLast` определяют диапазон разрешенных инструментов идентификаторов элементов управления. Чтобы отключить создание пользовательских панелей инструментов, задайте `uiUserToolbarFirst` или `uiUserToolbarLast` -1.  
  
##  <a name="insertpane"></a>COleIPFrameWndEx::InsertPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pControlBar`  
 [in] `pTarget`  
 [in] `bAfter`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ismenubaravailable"></a>COleIPFrameWndEx::IsMenuBarAvailable  
 Определяет, является ли указатель на объект панели меню не`NULL`  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ненулевое значение, если окна фрейма имеется меню; в противном случае возвращает значение 0.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для определения ли фрейма окна поддерживает отличные от `NULL` указатель на объект панели меню.  
  
##  <a name="ispointneardocksite"></a>COleIPFrameWndEx::IsPointNearDockSite  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 [in] `dwBarAlignment`  
 [in] `bOuterEdge`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="loadframe"></a>COleIPFrameWndEx::LoadFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nIDResource`  
 [in] `dwDefaultStyle`  
 [in] `pParentWnd`  
 [in] `pContext`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onclosedockingpane"></a>COleIPFrameWndEx::OnCloseDockingPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCloseDockingPane(CDockablePane*);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CDockablePane*`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="oncloseminiframe"></a>COleIPFrameWndEx::OnCloseMiniFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd*);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CPaneFrameWnd*`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onclosepopupmenu"></a>COleIPFrameWndEx::OnClosePopupMenu  
 Вызывается инфраструктурой при обработке активных всплывающем меню `WM_DESTROY` сообщение.  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMenuPopup`  
 Указатель на объект во всплывающем меню.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для получения уведомлений от `CMFCPopupMenu` объектов при обработке `WM_DESTROY` сообщений.  
  
##  <a name="oncmdmsg"></a>COleIPFrameWndEx::OnCmdMsg  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nID`  
 [in] `nCode`  
 [in] `pExtra`  
 [in] `pHandlerInfo`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondrawmenuimage"></a>COleIPFrameWndEx::OnDrawMenuImage  
 Вызывается инфраструктурой при рисовании изображения, который связан с элементом меню.  
  
```  
virtual BOOL OnDrawMenuImage(
    CDC* pDC,  
    const CMFCToolBarMenuButton* pMenuButton,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pMenuButton`  
 Указатель на кнопке меню.  
  
 [in] `rectImage`  
 Изображение, связанное с элементом меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию не выполняет никаких действий и возвращает значение 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если требуется настроить для пунктов меню, принадлежащих к строке меню, принадлежащих рисования изображения `COleIPFrameWndEx`-производный объект.  
  
##  <a name="ondrawmenulogo"></a>COleIPFrameWndEx::OnDrawMenuLogo  
 Вызывается инфраструктурой при [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)объекта процессов `WM_PAINT` сообщение.  
  
```  
virtual void OnDrawMenuLogo(
    CDC* pDC,  
    CMFCPopupMenu* pMenu,  
    const CRect& rectLogo);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `pMenu`  
 Указатель на объект во всплывающем меню.  
  
 [in] `rectLogo`  
 Указатель эмблему для отображения.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для отображения всплывающего меню, связанные с меню, принадлежащих логотип `COleIPFrameWndEx`-производный объект. Реализация по умолчанию не выполняет никаких действий.  
  
##  <a name="onmenubuttontoolhittest"></a>COleIPFrameWndEx::OnMenuButtonToolHitTest  
 Вызывается инфраструктурой при [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)объекта процессов `WM_NCHITTEST` сообщение.  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>Параметры  
 [in] pButton  
 Указатель на кнопки меню.  
  
 [out] pTI  
 Указатель на структуру `TOOLINFO`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию не выполняет никаких действий и возвращает значение 0. Реализации должен возвращать ненулевое значение, если он заполняет `pTI` параметр.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для предоставления сведений подсказки о специальный пункт меню.  
  
##  <a name="onmoveminiframe"></a>COleIPFrameWndEx::OnMoveMiniFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pFrame`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onsetpreviewmode"></a>COleIPFrameWndEx::OnSetPreviewMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bPreview`  
 [in] `pState`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onshowcustomizepane"></a>COleIPFrameWndEx::OnShowCustomizePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMenuPane`  
 [in] `uiToolbarID`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onshowpanes"></a>COleIPFrameWndEx::OnShowPanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShow`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onshowpopupmenu"></a>COleIPFrameWndEx::OnShowPopupMenu  
 Вызывается инфраструктурой при отображении всплывающего меню.  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>Параметры  
 `[in] pMenuPopup`  
 Указатель для отображения всплывающего меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию не выполняет никаких действий и возвращает ненулевое значение. Реализация должна возвращать `FALSE` Если не удается отобразить во всплывающем меню.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для настройки отображения всплывающего меню. Например можно поменять кнопки меню для кнопки меню цветов или инициализировать перемещаемые полосы.  
  
##  <a name="ontearoffmenu"></a>COleIPFrameWndEx::OnTearOffMenu  
 Вызывается платформой, когда пользователь выбирает в меню, которое имеет панель перемещаемые.  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMenuPopup`  
 Указатель всплывающего меню, выбранный пользователем.  
  
 [in] `pBar`  
 Указатель на область, содержащая меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если требуется платформа для активации во всплывающем меню. в противном случае `FALSE`. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите настроить программу установки панели перемещаемые переопределите эту функцию.  
  
##  <a name="panefrompoint"></a>COleIPFrameWndEx::PaneFromPoint  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar,  
    CRuntimeClass* pRTCBarType) const;  
  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 [in] `nSensitivity`  
 [in] `bExactBar`  
 [in] `pRTCBarType`  
 [in] `dwAlignment`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="pretranslatemessage"></a>COleIPFrameWndEx::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMsg`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="recalclayout"></a>COleIPFrameWndEx::RecalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bNotify`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="removepanefromdockmanager"></a>COleIPFrameWndEx::RemovePaneFromDockManager  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pControlBar,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide,  
    CBasePane* pBarReplacement);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pControlBar`  
 [in] `bDestroy`  
 [in] `bAdjustLayout`  
 [in] `bAutoHide`  
 [in] `pBarReplacement`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setdockstate"></a>COleIPFrameWndEx::SetDockState  
 Применяет указанное состояние закрепления областей, входящих в фрейме окна.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `state`  
 Указывает состояние стыковки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для указания нового состояния закрепляемых панелей, которые принадлежат `COleIPFrameWndEx` объекта.  
  
##  <a name="setuptoolbarmenu"></a>COleIPFrameWndEx::SetupToolbarMenu  
 Изменяет объект панели инструментов путем поиска фиктивных элементов и замены их указанными элементами, определяемыми пользователем.  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `menu`  
 Ссылку на [CMenu](../../mfc/reference/cmenu-class.md) объект для изменения.  
  
 [in] `uiViewUserToolbarCmdFirst`  
 Команда первого определяемых пользователем.  
  
 [in] `uiViewUserToolbarCmdLast`  
 Указывает последнюю команду определяемых пользователем.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="showpane"></a>COleIPFrameWndEx::ShowPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 [in] `bShow`  
 [in] `bDelay`  
 [in] `bActivate`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="winhelpa"></a>COleIPFrameWndEx::WinHelpA  
 Вызывается платформой для запуска приложения WinHelp или контекстной справки.  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Параметры  
 [in] dwData  
 Указывает данные, необходимые для справки, тип которой задан `nCmd`.  
  
 [in] `nCmd`  
 Задает тип запрошенной справки. Список возможных значений и их влияние на параметр `dwData` см. в разделе [Функция WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CFrameWndEx](../../mfc/reference/cframewndex-class.md)   
 [CMDIFrameWndEx Class](../../mfc/reference/cmdiframewndex-class.md)

