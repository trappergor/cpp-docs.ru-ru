---
title: "Класс CBasePane | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBasePane
- AFXBASEPANE/CBasePane
- AFXBASEPANE/CBasePane::AccNotifyObjectFocusEvent
- AFXBASEPANE/CBasePane::AddPane
- AFXBASEPANE/CBasePane::AdjustDockingLayout
- AFXBASEPANE/CBasePane::AdjustLayout
- AFXBASEPANE/CBasePane::CalcFixedLayout
- AFXBASEPANE/CBasePane::CanAcceptPane
- AFXBASEPANE/CBasePane::CanAutoHide
- AFXBASEPANE/CBasePane::CanBeAttached
- AFXBASEPANE/CBasePane::CanBeClosed
- AFXBASEPANE/CBasePane::CanBeDocked
- AFXBASEPANE/CBasePane::CanBeResized
- AFXBASEPANE/CBasePane::CanBeTabbedDocument
- AFXBASEPANE/CBasePane::CanFloat
- AFXBASEPANE/CBasePane::CanFocus
- AFXBASEPANE/CBasePane::CopyState
- AFXBASEPANE/CBasePane::CreateDefaultMiniframe
- AFXBASEPANE/CBasePane::CreateEx
- AFXBASEPANE/CBasePane::DockPane
- AFXBASEPANE/CBasePane::DockPaneUsingRTTI
- AFXBASEPANE/CBasePane::DockToFrameWindow
- AFXBASEPANE/CBasePane::DoesAllowDynInsertBefore
- AFXBASEPANE/CBasePane::EnableDocking
- AFXBASEPANE/CBasePane::EnableGripper
- AFXBASEPANE/CBasePane::FloatPane
- AFXBASEPANE/CBasePane::get_accHelpTopic
- AFXBASEPANE/CBasePane::get_accSelection
- AFXBASEPANE/CBasePane::GetCaptionHeight
- AFXBASEPANE/CBasePane::GetControlBarStyle
- AFXBASEPANE/CBasePane::GetCurrentAlignment
- AFXBASEPANE/CBasePane::GetDockingMode
- AFXBASEPANE/CBasePane::GetDockSiteFrameWnd
- AFXBASEPANE/CBasePane::GetEnabledAlignment
- AFXBASEPANE/CBasePane::GetMFCStyle
- AFXBASEPANE/CBasePane::GetPaneIcon
- AFXBASEPANE/CBasePane::GetPaneRow
- AFXBASEPANE/CBasePane::GetPaneStyle
- AFXBASEPANE/CBasePane::GetParentDockSite
- AFXBASEPANE/CBasePane::GetParentMiniFrame
- AFXBASEPANE/CBasePane::GetParentTabbedPane
- AFXBASEPANE/CBasePane::GetParentTabWnd
- AFXBASEPANE/CBasePane::GetRecentVisibleState
- AFXBASEPANE/CBasePane::HideInPrintPreviewMode
- AFXBASEPANE/CBasePane::InsertPane
- AFXBASEPANE/CBasePane::IsAccessibilityCompatible
- AFXBASEPANE/CBasePane::IsAutoHideMode
- AFXBASEPANE/CBasePane::IsDialogControl
- AFXBASEPANE/CBasePane::IsDocked
- AFXBASEPANE/CBasePane::IsFloating
- AFXBASEPANE/CBasePane::IsHorizontal
- AFXBASEPANE/CBasePane::IsInFloatingMultiPaneFrameWnd
- AFXBASEPANE/CBasePane::IsMDITabbed
- AFXBASEPANE/CBasePane::IsPaneVisible
- AFXBASEPANE/CBasePane::IsPointNearDockSite
- AFXBASEPANE/CBasePane::IsResizable
- AFXBASEPANE/CBasePane::IsRestoredFromRegistry
- AFXBASEPANE/CBasePane::IsTabbed
- AFXBASEPANE/CBasePane::IsVisible
- AFXBASEPANE/CBasePane::LoadState
- AFXBASEPANE/CBasePane::MoveWindow
- AFXBASEPANE/CBasePane::OnAfterChangeParent
- AFXBASEPANE/CBasePane::OnBeforeChangeParent
- AFXBASEPANE/CBasePane::OnDrawCaption
- AFXBASEPANE/CBasePane::OnMovePaneDivider
- AFXBASEPANE/CBasePane::OnPaneContextMenu
- AFXBASEPANE/CBasePane::OnRemoveFromMiniFrame
- AFXBASEPANE/CBasePane::OnSetAccData
- AFXBASEPANE/CBasePane::PaneFromPoint
- AFXBASEPANE/CBasePane::RecalcLayout
- AFXBASEPANE/CBasePane::RemovePaneFromDockManager
- AFXBASEPANE/CBasePane::SaveState
- AFXBASEPANE/CBasePane::SelectDefaultFont
- AFXBASEPANE/CBasePane::SetControlBarStyle
- AFXBASEPANE/CBasePane::SetDockingMode
- AFXBASEPANE/CBasePane::SetPaneAlignment
- AFXBASEPANE/CBasePane::SetPaneStyle
- AFXBASEPANE/CBasePane::SetWindowPos
- AFXBASEPANE/CBasePane::ShowPane
- AFXBASEPANE/CBasePane::StretchPane
- AFXBASEPANE/CBasePane::UndockPane
- AFXBASEPANE/CBasePane::DoPaint
dev_langs: C++
helpviewer_keywords:
- CBasePane [MFC], AccNotifyObjectFocusEvent
- CBasePane [MFC], AddPane
- CBasePane [MFC], AdjustDockingLayout
- CBasePane [MFC], AdjustLayout
- CBasePane [MFC], CalcFixedLayout
- CBasePane [MFC], CanAcceptPane
- CBasePane [MFC], CanAutoHide
- CBasePane [MFC], CanBeAttached
- CBasePane [MFC], CanBeClosed
- CBasePane [MFC], CanBeDocked
- CBasePane [MFC], CanBeResized
- CBasePane [MFC], CanBeTabbedDocument
- CBasePane [MFC], CanFloat
- CBasePane [MFC], CanFocus
- CBasePane [MFC], CopyState
- CBasePane [MFC], CreateDefaultMiniframe
- CBasePane [MFC], CreateEx
- CBasePane [MFC], DockPane
- CBasePane [MFC], DockPaneUsingRTTI
- CBasePane [MFC], DockToFrameWindow
- CBasePane [MFC], DoesAllowDynInsertBefore
- CBasePane [MFC], EnableDocking
- CBasePane [MFC], EnableGripper
- CBasePane [MFC], FloatPane
- CBasePane [MFC], get_accHelpTopic
- CBasePane [MFC], get_accSelection
- CBasePane [MFC], GetCaptionHeight
- CBasePane [MFC], GetControlBarStyle
- CBasePane [MFC], GetCurrentAlignment
- CBasePane [MFC], GetDockingMode
- CBasePane [MFC], GetDockSiteFrameWnd
- CBasePane [MFC], GetEnabledAlignment
- CBasePane [MFC], GetMFCStyle
- CBasePane [MFC], GetPaneIcon
- CBasePane [MFC], GetPaneRow
- CBasePane [MFC], GetPaneStyle
- CBasePane [MFC], GetParentDockSite
- CBasePane [MFC], GetParentMiniFrame
- CBasePane [MFC], GetParentTabbedPane
- CBasePane [MFC], GetParentTabWnd
- CBasePane [MFC], GetRecentVisibleState
- CBasePane [MFC], HideInPrintPreviewMode
- CBasePane [MFC], InsertPane
- CBasePane [MFC], IsAccessibilityCompatible
- CBasePane [MFC], IsAutoHideMode
- CBasePane [MFC], IsDialogControl
- CBasePane [MFC], IsDocked
- CBasePane [MFC], IsFloating
- CBasePane [MFC], IsHorizontal
- CBasePane [MFC], IsInFloatingMultiPaneFrameWnd
- CBasePane [MFC], IsMDITabbed
- CBasePane [MFC], IsPaneVisible
- CBasePane [MFC], IsPointNearDockSite
- CBasePane [MFC], IsResizable
- CBasePane [MFC], IsRestoredFromRegistry
- CBasePane [MFC], IsTabbed
- CBasePane [MFC], IsVisible
- CBasePane [MFC], LoadState
- CBasePane [MFC], MoveWindow
- CBasePane [MFC], OnAfterChangeParent
- CBasePane [MFC], OnBeforeChangeParent
- CBasePane [MFC], OnDrawCaption
- CBasePane [MFC], OnMovePaneDivider
- CBasePane [MFC], OnPaneContextMenu
- CBasePane [MFC], OnRemoveFromMiniFrame
- CBasePane [MFC], OnSetAccData
- CBasePane [MFC], PaneFromPoint
- CBasePane [MFC], RecalcLayout
- CBasePane [MFC], RemovePaneFromDockManager
- CBasePane [MFC], SaveState
- CBasePane [MFC], SelectDefaultFont
- CBasePane [MFC], SetControlBarStyle
- CBasePane [MFC], SetDockingMode
- CBasePane [MFC], SetPaneAlignment
- CBasePane [MFC], SetPaneStyle
- CBasePane [MFC], SetWindowPos
- CBasePane [MFC], ShowPane
- CBasePane [MFC], StretchPane
- CBasePane [MFC], UndockPane
- CBasePane [MFC], DoPaint
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
caps.latest.revision: "43"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c077f18fb9536e615685455e7bfc6fd896c0cc81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cbasepane-class"></a>Класс CBasePane
Базовый класс для всех областей в MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBasePane : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CBasePane::CBasePane`|Конструктор по умолчанию.|  
|`CBasePane::~CBasePane`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CBasePane::accHitTest`|Вызывается платформой для извлечения дочернего элемента или дочернего объекта в заданной точке экрана. (Переопределяет [CWnd::accHitTest](../../mfc/reference/cwnd-class.md#acchittest).)|  
|`CBasePane::accLocation`|Вызывается платформой для получения текущего положения экрана для указанного объекта. (Переопределяет [CWnd::accLocation](../../mfc/reference/cwnd-class.md#acclocation).)|  
|[CBasePane::AccNotifyObjectFocusEvent](#accnotifyobjectfocusevent)|`CBasePane`не используйте этот метод.|  
|`CBasePane::accSelect`|Вызывается платформой для изменения выбранной области или перемещения фокуса клавиатурного ввода указанного объекта. (Переопределяет [CWnd::accSelect](../../mfc/reference/cwnd-class.md#accselect).)|  
|[CBasePane::AddPane](#addpane)|Добавляет панель в диспетчере закрепления.|  
|[CBasePane::AdjustDockingLayout](#adjustdockinglayout)|Перенаправляет вызов к диспетчеру закрепления для настройки макета закрепления.|  
|[CBasePane::AdjustLayout](#adjustlayout)|Вызывается платформой при области следует изменить его внутренние структуры.|  
|[CBasePane::CalcFixedLayout](#calcfixedlayout)|Вычисляет размер панели элементов управления по горизонтали.|  
|[CBasePane::CanAcceptPane](#canacceptpane)|Определяет ли другой области можно прикреплять к области.|  
|[CBasePane::CanAutoHide](#canautohide)|Определяет, поддерживает ли области режим автоматического скрытия.|  
|[CBasePane::CanBeAttached](#canbeattached)|Определяет закреплением панели в другую область.|  
|[CBasePane::CanBeClosed](#canbeclosed)|Определяет, может быть закрыт области.|  
|[CBasePane::CanBeDocked](#canbedocked)|Определяет закреплением панели в другую область.|  
|[CBasePane::CanBeResized](#canberesized)|Определяет, можно ли изменять размер области.|  
|[CBasePane::CanBeTabbedDocument](#canbetabbeddocument)|Указывает, можно ли преобразовать в документ с вкладками MDI области.|  
|[CBasePane::CanFloat](#canfloat)|Определяет, можно ли float области.|  
|[CBasePane::CanFocus](#canfocus)|Указывает, является ли область может получать фокус.|  
|[CBasePane::CopyState](#copystate)|Копирует состояние данной панели.|  
|[CBasePane::CreateDefaultMiniframe](#createdefaultminiframe)|Если области можно перемещаться, создает окна области.|  
|[CBasePane::CreateEx](#createex)|Создает панель управления.|  
|[CBasePane::DockPane](#dockpane)|Закрепляет область в другую область или область окна.|  
|[CBasePane::DockPaneUsingRTTI](#dockpaneusingrtti)|Закрепляет область, используя сведения о типах во время выполнения.|  
|[CBasePane::DockToFrameWindow](#docktoframewindow)|Закрепляет закрепляемую панель кадра.|  
|[CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Определяет, может ли другой области динамической вставки между этой панели и родительского фрейма.|  
|[CBasePane::EnableDocking](#enabledocking)|Включает закрепления панели для главного фрейма.|  
|[CBasePane::EnableGripper](#enablegripper)|Включает или отключает захвата. Если включен захвата, пользователь может перетащить его для изменения положения панели.|  
|`CBasePane::FillWindowRect`|Используется внутренним образом.|  
|[CBasePane::FloatPane](#floatpane)|Смещает области.|  
|`CBasePane::get_accChild`|Вызывается платформой для извлечения адреса интерфейса `IDispatch` для указанного дочернего элемента. (Переопределяет [CWnd::get_accChild](../../mfc/reference/cwnd-class.md#get_accchild).)|  
|`CBasePane::get_accChildCount`|Вызывается платформой для извлечения число дочерних объектов, принадлежащих этому объекту. (Переопределяет [CWnd::get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount).)|  
|`CBasePane::get_accDefaultAction`|Вызывается платформой для извлечения строки, описывающую выполняемое по умолчанию для объекта. (Переопределяет [CWnd::get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction).)|  
|`CBasePane::get_accDescription`|Вызывается платформой для извлечения строки, описывающей внешний вид указанного объекта. (Переопределяет [CWnd::get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription).)|  
|`CBasePane::get_accFocus`|Вызывается платформой для извлечения объекта, имеющего фокус клавиатурного ввода. (Переопределяет [CWnd::get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus).)|  
|`CBasePane::get_accHelp`|Вызывается платформой для извлечения строки свойства Help объекта. (Переопределяет [CWnd::get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp).)|  
|[CBasePane::get_accHelpTopic](#get_acchelptopic)|Вызывается платформой для извлечения полного пути файла WinHelp, связанного с указанным объектом и идентификатором нужного раздела в этом файле. (Переопределяет [CWnd::get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic).)|  
|`CBasePane::get_accKeyboardShortcut`|Вызывается платформой для извлечения указанного сочетание клавиш для объекта. (Переопределяет [CWnd::get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut).)|  
|`CBasePane::get_accName`|Вызывается платформой для извлечения имени указанного объекта. (Переопределяет [CWnd::get_accName](../../mfc/reference/cwnd-class.md#get_accname).)|  
|`CBasePane::get_accParent`|Вызывается платформой для извлечения `IDispatch` интерфейс для родительского объекта. (Переопределяет [CWnd::get_accParent](../../mfc/reference/cwnd-class.md#get_accparent).)|  
|`CBasePane::get_accRole`|Вызывается платформой для извлечения информации, описывающей роль указанного объекта. (Переопределяет [CWnd::get_accRole](../../mfc/reference/cwnd-class.md#get_accrole).)|  
|[CBasePane::get_accSelection](#get_accselection)|Вызывается платформой для извлечения выбранного дочернего элемента этого объекта. (Переопределяет [CWnd::get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection).)|  
|`CBasePane::get_accState`|Вызывается платформой для извлечения текущего состояния указанного объекта. (Переопределяет [CWnd::get_accState](../../mfc/reference/cwnd-class.md#get_accstate).)|  
|`CBasePane::get_accValue`|Вызывается платформой для извлечения значения указанного объекта. (Переопределяет [CWnd::get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue).)|  
|[CBasePane::GetCaptionHeight](#getcaptionheight)|Возвращает высоту заголовка.|  
|[CBasePane::GetControlBarStyle](#getcontrolbarstyle)|Возвращает стиль панели управления.|  
|[CBasePane::GetCurrentAlignment](#getcurrentalignment)|Возвращает текущее выравнивание панели.|  
|[CBasePane::GetDockingMode](#getdockingmode)|Возвращает режим закрепления панели.|  
|[CBasePane::GetDockSiteFrameWnd](#getdocksiteframewnd)|Возвращает указатель на сайте закрепления области окна.|  
|[CBasePane::GetEnabledAlignment](#getenabledalignment)|Возвращает CBRS_ALIGN_ стили, которые применяются к области.|  
|[CBasePane::GetMFCStyle](#getmfcstyle)|Возвращает области стили для MFC.|  
|[CBasePane::GetPaneIcon](#getpaneicon)|Возвращает дескриптор значка области.|  
|`CBasePane::GetPaneRect`|Используется внутренним образом.|  
|[CBasePane::GetPaneRow](#getpanerow)|Возвращает указатель на [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)объекта место закрепления панели.|  
|[CBasePane::GetPaneStyle](#getpanestyle)|Возвращает стиль панели.|  
|[CBasePane::GetParentDockSite](#getparentdocksite)|Возвращает указатель на родительский сайт закрепления.|  
|[CBasePane::GetParentMiniFrame](#getparentminiframe)|Возвращает указатель области родительского окна.|  
|[CBasePane::GetParentTabbedPane](#getparenttabbedpane)|Возвращает указатель на панель с вкладками родительского.|  
|[CBasePane::GetParentTabWnd](#getparenttabwnd)|Возвращает указатель на родительское окно, на вкладке.|  
|[CBasePane::GetRecentVisibleState](#getrecentvisiblestate)|Платформа вызывает этот метод при восстановлении область из архива.|  
|[CBasePane::HideInPrintPreviewMode](#hideinprintpreviewmode)|Указывает, скрыт ли панели в режиме предварительного просмотра.|  
|[CBasePane::InsertPane](#insertpane)|Регистрирует указанный панели в диспетчере закрепления.|  
|[CBasePane::IsAccessibilityCompatible](#isaccessibilitycompatible)|Указывает, поддерживает ли области Active Accessibility.|  
|[CBasePane::IsAutoHideMode](#isautohidemode)|Определяет, является ли область в режиме автоматического скрытия.|  
|[CBasePane::IsDialogControl](#isdialogcontrol)|Указывает, является ли область элемента управления диалогового окна.|  
|[CBasePane::IsDocked](#isdocked)|Определяет, закреплена ли области.|  
|[CBasePane::IsFloating](#isfloating)|Определяет, является ли область плавающее окно.|  
|[CBasePane::IsHorizontal](#ishorizontal)|Определяет, является ли панель закреплена горизонтально.|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Указывает, является ли область в окне фрейма несколькими областями.|  
|[CBasePane::IsMDITabbed](#ismditabbed)|Определяет, добавлен ли области в виде документа с вкладками дочернего окна MDI.|  
|[CBasePane::IsPaneVisible](#ispanevisible)|Указывает, является ли `WS_VISIBLE` флаг установлен для области.|  
|[CBasePane::IsPointNearDockSite](#ispointneardocksite)|Определяет, является ли указанная точка рядом с сайта закрепления.|  
|[CBasePane::IsResizable](#isresizable)|Определяет, можно ли изменять размер области.|  
|[CBasePane::IsRestoredFromRegistry](#isrestoredfromregistry)|Определяет, будет ли восстановлена панели из реестра.|  
|[CBasePane::IsTabbed](#istabbed)|Определяет ли области был вставлен в набор вкладок окна с вкладками.|  
|`CBasePane::IsTooltipTopmost`|Используется внутренним образом.|  
|[CBasePane::IsVisible](#isvisible)|Определяет, будет ли видна панель.|  
|[CBasePane::LoadState](#loadstate)|Загружает состояние панели из реестра.|  
|[CBasePane::MoveWindow](#movewindow)|Перемещает область.|  
|[CBasePane::OnAfterChangeParent](#onafterchangeparent)|Вызывается платформой при изменении родительской области.|  
|[CBasePane::OnBeforeChangeParent](#onbeforechangeparent)|Вызывается платформой непосредственно перед панель изменяется родительского окна.|  
|[CBasePane::OnDrawCaption](#ondrawcaption)|Этот метод вызывается платформой при отрисовке заголовка.|  
|[CBasePane::OnMovePaneDivider](#onmovepanedivider)|В настоящее время этот метод не используется.|  
|[CBasePane::OnPaneContextMenu](#onpanecontextmenu)|Вызывается платформой при построении меню, которое содержит список областей.|  
|[CBasePane::OnRemoveFromMiniFrame](#onremovefromminiframe)|Вызывается платформой при удалении области из родительского окна мини-рамки.|  
|[CBasePane::OnSetAccData](#onsetaccdata)|`CBasePane`не используйте этот метод.|  
|`CBasePane::OnUpdateCmdUI`|Используется внутренним образом.|  
|[CBasePane::PaneFromPoint](#panefrompoint)|Возвращает область, содержащее заданную точку.|  
|`CBasePane::PreTranslateMessage`|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для преобразования сообщений окна перед их передачей функциям Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) . (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CBasePane::RecalcLayout](#recalclayout)|`CBasePane`не используйте этот метод.|  
|[CBasePane::RemovePaneFromDockManager](#removepanefromdockmanager)|Отменяет регистрацию областью и удаляет его из списка в диспетчере закрепления.|  
|[CBasePane::SaveState](#savestate)|Сохраняет состояние панели в реестр.|  
|[CBasePane::SelectDefaultFont](#selectdefaultfont)|Выбирает шрифт по умолчанию для контекста заданного устройства.|  
|`CBasePane::Serialize`|Считывает этот объект из архива или записывает в него. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CBasePane::SetControlBarStyle](#setcontrolbarstyle)|Задает стиль панели управления.|  
|[CBasePane::SetDockingMode](#setdockingmode)|Задает режим для области закрепления.|  
|`CBasePane::SetMDITabbed`|Используется внутренним образом.|  
|[CBasePane::SetPaneAlignment](#setpanealignment)|Задает выравнивание для области.|  
|`CBasePane::SetPaneRect`|Используется внутренним образом.|  
|[CBasePane::SetPaneStyle](#setpanestyle)|Задает стиль окна.|  
|`CBasePane::SetRestoredFromRegistry`|Используется внутренним образом.|  
|[CBasePane::SetWindowPos](#setwindowpos)|Изменяет размер, положение и Z-порядок области.|  
|[CBasePane::ShowPane](#showpane)|Показывает или скрывает панель.|  
|[CBasePane::StretchPane](#stretchpane)|Растягивает панель по вертикали или горизонтали.|  
|[CBasePane::UndockPane](#undockpane)|Удаляет область из сайта закрепления, по умолчанию ползунок или окна области, где он в настоящее время закреплен.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBasePane::DoPaint](#dopaint)|Заполняет фон панели.|  
  
## <a name="remarks"></a>Примечания  
 Если вы хотите создать класс области, который поддерживает расширенные функции закрепления, доступные в MFC, необходимо выполнить наследование от `CBasePane` или [класса CPane](../../mfc/reference/cpane-class.md).  
  
## <a name="customization-tips"></a>Советы по настройке  
 Следующие советы по настройке относятся к `CBasePane Class` и всем классам, наследующим от него:  
  
-   При создании области, можно применить несколько новых стилей.  
  
    - `AFX_CBRS_FLOAT`делает области с плавающей запятой.  
  
    - `AFX_CBRS_AUTOHIDE`включает режим автоматического скрытия.  
  
    - `AFX_CBRS_CLOSE`включает панель будет закрыта (скрытый).  
  
     Это флаги, которые можно комбинировать с помощью операции побитового или.  
  
 `CBasePane`реализует следующие виртуальные методы логическое чтобы отразить эти флаги: [CBasePane::CanBeClosed](#canbeclosed), [CBasePane::CanAutoHide](#canautohide), [CBasePane::CanFloat](#canfloat). Их можно переопределить в производных классах для настройки их поведения.  
  
-   Можно настроить поведение прикрепления путем переопределения [CBasePane::CanAcceptPane](#canacceptpane). Иметь свою собственную панель возвращать `FALSE` из этого метода, чтобы предотвратить закрепление его в другой области.  
  
-   Если вы хотите создать Статичная область, не могут перемещаться и который препятствует закрепление перед любой другой панели (аналогично панели Outlook, в примере OutlookDemo), он не числом с плавающей и переопределить [CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore) для возврата `FALSE`. Реализация по умолчанию возвращает `FALSE` Если области создается без `AFX_CBRS_FLOAT` стиля.  
  
-   Создайте все панели с идентификаторами, отличным от – 1.  
  
-   Чтобы определить область видимости, используйте [CBasePane::IsVisible](#isvisible). Он правильно обрабатывает состояние видимости в с вкладками и режима автоматического скрытия.  
  
-   Если требуется создать не перемещаемой панели изменяемого размера, создайте ее без `AFX_CBRS_FLOAT` стиля и вызов [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).  
  
-   Запрет макет закрепления в области или удалить из ее строки закрепления панели инструментов, вызовите [CBasePane::UndockPane](#undockpane). Не вызывайте этот метод для панелей в режиме автоматического скрытия или областей, которые находятся на вкладках окон с вкладками.  
  
-   Если вы хотите float или отменить закрепление панели, которая находится в режиме автоматического скрытия, необходимо вызвать [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode) с `FALSE` в качестве первого аргумента, перед вызовом метода [CBasePane::FloatPane](#floatpane) или [ CBasePane::UndockPane](#undockpane).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование различных методов `CBasePane` класса. В примере показано, как извлечь область из `CFrameWndEx` класс и как задать режим закрепления, выравнивание по области и стиль панели. Фрагмент кода взят из [примера Word Pad](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#2](../../mfc/reference/codesnippet/cpp/cbasepane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxbasepane.h  
  
##  <a name="accnotifyobjectfocusevent"></a>CBasePane::AccNotifyObjectFocusEvent  
 `CBasePane`не используйте этот метод.  
  
```  
virtual void AccNotifyObjectFocusEvent(int);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `int`  
 Не используется.  
  
##  <a name="addpane"></a>CBasePane::AddPane  
 Добавляет панель в диспетчере закрепления.  
  
```  
void AddPane(CBasePane* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на область для добавления.  
  
### <a name="remarks"></a>Примечания  
 Это удобный метод, который добавляет панель в диспетчере закрепления. С помощью этого метода, не необходимо написать код, который анализирует тип родительского фрейма.  
  
 Дополнительные сведения см. в разделе [класса CDockingManager](../../mfc/reference/cdockingmanager-class.md) и [CMDIFrameWndEx::AddPane](../../mfc/reference/cmdiframewndex-class.md#addpane).  
  
##  <a name="adjustdockinglayout"></a>CBasePane::AdjustDockingLayout  
 Перенаправляет вызов к диспетчеру закрепления для настройки макета закрепления.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `hdwp`  
 Дескриптор структуру, содержащую несколько положение окон.  
  
### <a name="remarks"></a>Примечания  
 Это удобный метод, который настраивает макет закрепления. С помощью этого метода, не необходимо написать код, который анализирует тип родительского фрейма.  
  
 Дополнительные сведения см. в разделе [CDockingManager::AdjustDockingLayout](../../mfc/reference/cdockingmanager-class.md#adjustdockinglayout)  
  
##  <a name="adjustlayout"></a>CBasePane::AdjustLayout  
 Вызывается платформой для настройки макета внутренней области.  
  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод при панели, который необходимо настроить его внутренней структуры. Базовая реализация не выполняет никаких действий.  
  
##  <a name="calcfixedlayout"></a>CBasePane::CalcFixedLayout  
 Вычисляет размер панели элементов управления по горизонтали.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bStretch`  
 Указывает ли панель растягивания для размера кадра. `bStretch` Параметр имеет ненулевое значение, при строке не закрепляемую панель (недоступно для закрепления) и 0 при закрепленными или с плавающей запятой (доступны для закрепления).  
  
 [in] `bHorz`  
 Указывает, что полоса является горизонтально или вертикально. `bHorz` Параметр имеет ненулевое значение, если панель горизонтальный и равно 0, если она вертикально.  
  
### <a name="return-value"></a>Возвращаемое значение  
 На панели управления размер в пикселях объекта `CSize` объекта.  
  
### <a name="remarks"></a>Примечания  
 См. раздел примечания в [CControlBar::CalcFixedLayout](../../mfc/reference/ccontrolbar-class.md#calcfixedlayout)  
  
##  <a name="canacceptpane"></a>CBasePane::CanAcceptPane  
 Определяет ли другой области можно прикреплять к области.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на панель, чтобы закрепить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если другой области могут быть приняты; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой перед его закрепляет область определяется `pBar` для текущей области.  
  
 Используйте этот метод и [CBasePane::CanBeDocked](#canbedocked) метод для управления как закрепление панелей в другие области в приложении.  
  
 Реализация по умолчанию возвращает значение `FALSE`.  
  
##  <a name="canautohide"></a>CBasePane::CanAutoHide  
 Определяет, поддерживает ли области режим автоматического скрытия.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если эта область поддерживает режим автоматического скрытия. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает эту функцию, чтобы определить, поддерживает ли области режим автоматического скрытия.  
  
 Во время построения, эту возможность можно задать, передав `AFX_CBRS_AUTOHIDE` флаг [CBasePane::CreateEx](#createex).  
  
 Реализация по умолчанию проверяет наличие `AFX_CBRS_AUTOHIDE` флаг. Переопределите этот метод в производном классе для настройки этого поведения.  
  
##  <a name="canbeattached"></a>CBasePane::CanBeAttached  
 Определяет, можно ли прикрепить к другой панели или окне фрейма области.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области можно прикреплять к другой панели или окне фрейма; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию возвращает значение `FALSE`. Переопределите этот метод в производном классе, чтобы включить или отключить возможность закрепления без вызова [CBasePane::EnableDocking](#enabledocking).  
  
##  <a name="canbeclosed"></a>CBasePane::CanBeClosed  
 Определяет, может быть закрыт области.  
  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область может быть закрыт; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, чтобы определить, может быть закрыт области. Если метод возвращает `TRUE`, **закрыть** добавляется кнопка заголовка панели или, если области открывается как плавающее окно, заголовок окна плавающего окна области.  
  
 Во время построения, эту возможность можно задать, передав `AFX_CBRS_CLOSE` флаг [CBasePane::CreateEx](#createex).  
  
 Реализация по умолчанию проверяет наличие `AFX_CBRS_CLOSE` флаг.  
  
##  <a name="canbedocked"></a>CBasePane::CanBeDocked  
 Определяет закреплением панели в другую область.  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDockBar`  
 Указатель на другую панель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если в этой области можно прикреплять к другой области; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой перед его закрепляет область определяется `pDockBar` для текущей области.  
  
 Используйте этот метод и [CBasePane::CanAcceptPane](#canacceptpane) метод для управления как закрепление панелей в другие области в приложении.  
  
 Реализация по умолчанию возвращает значение `FALSE`.  
  
##  <a name="canberesized"></a>CBasePane::CanBeResized  
 Определяет, можно ли изменять размер области.  
  
```  
virtual BOOL CanBeResized() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если можно изменять размер области; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод проверяет `AFX_CBRS_RESIZE` флаг, который по умолчанию в `CBasePane::OnCreate`. Если этот флаг не указан, в диспетчере закрепления флаги области недвижимое вместо закрепить ее внутренним образом.  
  
##  <a name="canbetabbeddocument"></a>CBasePane::CanBeTabbedDocument  
 Указывает, можно ли преобразовать в документ с вкладками MDI области.  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область может быть преобразовано в документ с вкладками. в противном случае `FALSE`. Параметр `CBasePane::CanBeTabbedDocument` всегда возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Только объекты, определенные `CBasePane`-производные типы, такие как [класс CDockablePane](../../mfc/reference/cdockablepane-class.md), можно преобразовать в документы с вкладками.  
  
##  <a name="canfloat"></a>CBasePane::CanFloat  
 Определяет, можно ли float области.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область может число с плавающей запятой; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, чтобы определить, можно ли float области.  
  
 Во время построения, эту возможность можно задать, передав `AFX_CBRS_FLOAT` флаг [CBasePane::CreateEx](#createex).  
  
> [!NOTE]
>  Платформа предполагается, что неперемещаемая области являются статичными и что невозможно изменить свое состояние закрепления. Таким образом платформа не сохраняет состояние стыковки неперемещаемая панелей.  
  
 Реализация по умолчанию проверяет наличие `AFX_CBRS_FLOAT` стиля.  
  
##  <a name="canfocus"></a>CBasePane::CanFocus  
 Указывает, является ли область может получать фокус.  
  
```  
virtual BOOL CanFocus() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область может получать фокус; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе для управления фокус ввода. Например, так как панели инструментов не может получить фокус, этот метод возвращает `FALSE` при вызове на панели инструментов объекты.  
  
 Предпринимает попытку установить фокус ввода, когда область закрепления или перемещается.  
  
##  <a name="copystate"></a>CBasePane::CopyState  
 Копирует состояние данной панели.  
  
```  
virtual void CopyState(CBasePane* pOrgBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pOrgBar`  
 Указатель на другую панель.  
  
### <a name="remarks"></a>Примечания  
 Этот метод копирует состояние из `pOrgBar` в эту область.  
  
##  <a name="createdefaultminiframe"></a>CBasePane::CreateDefaultMiniframe  
 Если области можно перемещаться, этот метод создает окно области для него.  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectInitial`  
 Указывает начальные координаты окна области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новые окна области или `NULL` , если не удалось создать.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод при областью переключается в состояние с с плавающей запятой. Метод создает окно области и прикрепляет области на этот период.  
  
 Реализация по умолчанию возвращает значение `NULL`.  
  
##  <a name="createex"></a>CBasePane::CreateEx  
 Создает панель управления.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle=0,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwStyleEx`  
 Расширенные стили (см. [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) для получения дополнительной информации).  
  
 [in] `lpszClassName`  
 Имя класса окна.  
  
 [in] `lpszWindowName`  
 Имя окна.  
  
 [in] `dwStyle`  
 Стиль окна (в разделе [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)).  
  
 [in] `rect`  
 Исходного прямоугольника.  
  
 [in] `pParentWnd`  
 Указатель на родительское окно.  
  
 [in] `nID`  
 Указывает идентификатор области. Должно быть уникальным.  
  
 [in] `dwControlBarStyle`  
 Флаги стилей для панели.  
  
 [in] `pContext`  
 Указатель на`CcreateContext`  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область создана успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Создает окно класса `lpszClassName`. При указании `WS_CAPTION`, этот метод очищает `WS_CAPTION` бит стиля и наборы `CBasePane::m_bHasCaption` для `TRUE`, так как библиотеки не поддерживает области с подписями.  
  
 Можно использовать любое сочетание стилей окна дочерних и панель (CBRS_) стили элементов управления MFC.  
  
 Библиотека добавляет несколько новых стилей для панели. В следующей таблице описаны новые стили:  
  
|Стиль|Описание:|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Области можно с плавающей запятой.|  
|`AFX_CBRS_AUTOHIDE`|Область поддерживает режим автоматического скрытия|  
|`AFX_CBRS_RESIZE`|Области могут быть изменены. **Важно:** этот стиль не реализован.|  
|`AFX_CBRS_CLOSE`|Область может быть закрыт.|  
|`AFX_CBRS_AUTO_ROLLUP`|Возможность выполнять сведение области, когда она перемещается.|  
|`AFX_CBRS_REGULAR_TABS`|При на другую панель, в которой этот стиль закрепляет одну область, создается регулярное окна с вкладками. (Дополнительные сведения см. в разделе [CTabbedPane класса](../../mfc/reference/ctabbedpane-class.md).)|  
|`AFX_CBRS_OUTLOOK_TABS`|При на другую панель, в которой этот стиль закрепляет одну область, создается стиле Outlook окна с вкладками. (Дополнительные сведения см. в разделе [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).)|  
  
 Чтобы использовать новые стили, укажите их в `dwControlBarStyle`.  
  
##  <a name="dockpane"></a>CBasePane::DockPane  
 Закрепляет область в другую область или область окна.  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDockBar`  
 Указатель на другую панель.  
  
 [in] `lpRect`  
 Указывает прямоугольника назначения.  
  
 [in] `dockMethod`  
 Задает метод закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель управления был прикреплять успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию, чтобы закрепить в области для другой области или Закрепить панель ( [класс CDockSite](../../mfc/reference/cdocksite-class.md)), указанным параметром `pDockBar`, или для главного фрейма Если `pDockBar` — `NULL`.  
  
 `dockMethod`Задает способ закрепления панели. В разделе [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) список возможных значений.  
  
##  <a name="dockpaneusingrtti"></a>CBasePane::DockPaneUsingRTTI  
 Закрепляет область, используя сведения о типах во время выполнения.  
  
```  
void DockPaneUsingRTTI(BOOL bUseDockSite);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bUseDockSite`  
 Если `TRUE`, закрепить на сайте закрепления. Если `FALSE`, закрепите их родительского фрейма.  
  
##  <a name="docktoframewindow"></a>CBasePane::DockToFrameWindow  
 Закрепляет закрепляемую панель кадра.  
  
```  
virtual BOOL DockToFrameWindow(
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL,  
    DWORD dwDockFlags = DT_DOCK_LAST,  
    CBasePane* pRelativeBar = NULL,  
    int nRelativeIndex = -1,  
    BOOL bOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwAlignment`  
 В части, которую требуется закрепить на панели, чтобы родительского фрейма.  
  
 [in] `lpRect`  
 Требуемый размер.  
  
 [in] `dwDockFlags`  
 Не обрабатывается.  
  
 [in] `pRelativeBar`  
 Не обрабатывается.  
  
 [in] `nRelativeIndex`  
 Не обрабатывается.  
  
 [in] `bOuterEdge`  
 Если `TRUE` и нет других закрепляемых областей на стороне, заданные `dwAlignment`, панель закреплена за пределами области, ближе к краю родительского фрейма. Если `FALSE`, панель прикрепляется ближе к центру клиентской области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод завершается ошибкой, если разделитель области ( [CPaneDivider класса](../../mfc/reference/cpanedivider-class.md)) не может быть создан. В противном случае всегда возвращает `TRUE`.  
  
##  <a name="doesallowdyninsertbefore"></a>CBasePane::DoesAllowDynInsertBefore  
 Определяет, может ли другой области динамической вставки между этой панели и родительского фрейма.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если пользователь может вставить другой области; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, чтобы определить, может ли пользователь динамически вставить область перед этой панели.  
  
 Например предположим, что приложение создает область, закрепленную в левой области (например, панель Outlook). Чтобы предотвратить закрепление другую панель слева от первой области, переопределите этот метод и возвращать `FALSE`.  
  
 Мы рекомендуем, переопределите этот метод и возвращать `FALSE` для неперемещаемая панелей, производного от [класс CDockablePane](../../mfc/reference/cdockablepane-class.md).  
  
 Реализация по умолчанию возвращает значение `TRUE`.  
  
##  <a name="dopaint"></a>CBasePane::DoPaint  
 Заполняет фон панели.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает текущий диспетчер визуального представления для заливки фона ( [CMFCVisualManager::OnFillBarBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillbarbackground)).  
  
##  <a name="enabledocking"></a>CBasePane::EnableDocking  
 Включает закрепления панели для главного фрейма.  
  
```  
virtual void EnableDocking(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwAlignment`  
 Задает выравнивание закрепления для включения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для закрепления выравнивание для главного фрейма. Вы можете передать сочетание `CBRS_ALIGN_` флаги (Дополнительные сведения см. в разделе [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).  
  
 `EnableDocking`задает внутренний флаг `CBasePane::m_dwEnabledAlignment` и платформа проверяет этот флаг, если панель закреплена.  
  
 Вызовите [CBasePane::GetEnabledAlignment](#getenabledalignment) для определения закрепления выравнивание для области.  
  
##  <a name="enablegripper"></a>CBasePane::EnableGripper  
 Включает или отключает захвата. Если включен захвата, пользователь может перетащить его для изменения положения панели.  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Включение захвата; `FALSE` отключить ее.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует этот метод для включения захвата вместо `WS_CAPTION` стиля.  
  
##  <a name="floatpane"></a>CBasePane::FloatPane  
 Смещает области.  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod=DM_UNKNOWN,  
    bool bShow=true);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectFloat`  
 Указывает, где плавающей панели отображаются координаты на экране.  
  
 [in] `dockMethod`  
 Задает метод dock для использования в плавающее области.  
  
 [in] `bShow`  
 Указывает, будет ли видна панель с плавающей запятой ( `TRUE`) или скрытым ( `FALSE`).  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область была перемещается успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для float область на экране позиции, указанной параметром `rectFloat`.  
  
##  <a name="get_acchelptopic"></a>CBasePane::get_accHelpTopic  
 Платформа вызывает этот метод, чтобы получить полный путь к `WinHelp` файл, связанный с указанным объектом и идентификатором нужного раздела в этом файле.  
  
```  
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,  
    VARIANT varChild,  
    long* pidTopic);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pszHelpFile`  
 Адрес `BSTR` , который получает полный путь к `WinHelp` файл, связанный с указанным объектом, если таковые имеются.  
  
 [in] `varChild`  
 Указывает, является ли раздел справки, чтобы получить объект или один из дочерних элементов объекта. Этот параметр может быть как `CHILDID_SELF` (Чтобы получить раздел справки для объекта) или идентификатор дочернего (Чтобы получить раздел справки для одной из ее дочерних элементов объекта).  
  
 [in] `pidTopic`  
 Идентифицирует `Help` раздел файла, связанного с указанным объектом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `CBasePane`не реализует этот метод. Таким образом `CBasePane::get_accHelpTopic` всегда возвращает `S_FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция является частью поддержки Active Accessibility в MFC. Переопределите эту функцию в производном классе, чтобы справочную информацию о объекта.  
  
##  <a name="get_accselection"></a>CBasePane::get_accSelection  
 Платформа вызывает этот метод для извлечения выбранного дочернего элемента этого объекта.  
  
```  
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pvarChildren`  
 Получает сведения, которые определяют выбранного дочернего.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `CBasePane`не реализует этот метод. Если значением параметра `pvarChildren` является `NULL`, метод возвращает `E_INVALIDARG`. В противном случае этот метод возвращает `DISP_E_MEMBERNOTFOUND`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция является частью поддержки Active Accessibility в MFC. Переопределите эту функцию в производном классе, если элементы не оконные пользовательского интерфейса, отличные от элементов управления ActiveX без окон.  
  
##  <a name="getcaptionheight"></a>CBasePane::GetCaptionHeight  
 Возвращает высоту заголовка.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Высота заголовка.  
  
##  <a name="getcontrolbarstyle"></a>CBasePane::GetControlBarStyle  
 Возвращает стиль панели управления.  
  
```  
virtual DWORD GetControlBarStyle() const 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Побитовый оператор или сочетанием флагов AFX_CBRS_.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение состоит из следующих значений.  
  
|Стиль|Описание:|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Делает float панели управления.|  
|`AFX_CBRS_AUTOHIDE`|Включает режим автоматического скрытия.|  
|`AFX_CBRS_RESIZE`|Включает изменение размера панели элементов управления. Если этот флаг установлен, на панели управления может быть помещен в закрепляемую панель.|  
|`AFX_CBRS_CLOSE`|Обеспечивает скрытие панели элементов управления.|  
  
##  <a name="getcurrentalignment"></a>CBasePane::GetCurrentAlignment  
 Возвращает текущее выравнивание панели.  
  
```  
virtual DWORD GetCurrentAlignment() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее выравнивание панели элементов управления. В следующей таблице показаны возможные значения:  
  
|Значение|Выравнивание|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|Выравнивание по левому краю.|  
|`CBRS_ALIGN_RIGHT`|Выравнивание по правому краю.|  
|`CBRS_ALIGN_TOP`|Выравнивание по верхнему краю.|  
|`CBRS_ALIGN_BOTTOM`|Выравнивание нижней.|  
  
##  <a name="getdockingmode"></a>CBasePane::GetDockingMode  
 Возвращает режим закрепления панели.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 DT_STANDARD при перетаскивании панели на экране обозначается прямоугольника перетаскивания. DT_IMMEDIATE при перетаскивании содержимое области.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, чтобы определить текущий режим закрепления панели.  
  
 Если `CBasePane::m_dockMode` — не определено (DT_UNDEFINED), то режим закрепления берется из глобальный режим закрепления ( `AFX_GLOBAL_DATA::m_dockModeGlobal`).  
  
 Установив `m_dockMode` или переопределение `GetDockingMode` можно выбрать режим закрепления для каждой области.  
  
##  <a name="getdocksiteframewnd"></a>CBasePane::GetDockSiteFrameWnd  
 Возвращает указатель на [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)объекта место закрепления панели.  
  
```  
virtual CWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на сайте закрепления панели.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы получить указатель на сайте закрепления панели. Если панель открывается как плавающее окно, сайте закрепления можно фрейма главного окна, если область прикрепляется к главного фрейма или окна области.  
  
##  <a name="getenabledalignment"></a>CBasePane::GetEnabledAlignment  
 Возвращает CBRS_ALIGN_ стили, которые применяются к области.  
  
```  
virtual DWORD GetEnabledAlignment() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сочетание CBRS_ALIGN_ стили. В следующей таблице показаны возможные стили:  
  
|Flag|Выравнивание включена|  
|----------|-----------------------|  
|`CBRS_ALIGN_LEFT`|По левому краю.|  
|`CBRS_ALIGN_RIGHT`|Правильно.|  
|`CBRS_ALIGN_TOP`|Вверх.|  
|`CBRS_ALIGN_BOTTOM`|По нижнему краю.|  
|`CBRS_ALIGN_ANY`|Сочетание всех флагов.|  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы определить, включено выравнивание для области. Включено выравнивание означает сторон фрейма главного окна, которую можно закрепить панель.  
  
 Включение закрепления выравнивание с помощью [CBasePane::EnableDocking](#enabledocking).  
  
##  <a name="getmfcstyle"></a>CBasePane::GetMFCStyle  
 Возвращает области стили, характерные для MFC.  
  
```  
virtual DWORD GetMFCStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сочетание стилей панели (AFX_CBRS_) для данной библиотеки.  
  
##  <a name="getpaneicon"></a>CBasePane::GetPaneIcon  
 Возвращает дескриптор значка области.  
  
```  
virtual HICON GetPaneIcon(BOOL bBigIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bBigIcon`  
 Указывает 32 x 32 пикселя значок, если `TRUE`; указывает 16 пикселей значком 16 пикселей, если `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор значок панели. В случае неудачи возвращает `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает [CWnd::GetIcon](../../mfc/reference/cwnd-class.md#geticon).  
  
##  <a name="getpanerow"></a>CBasePane::GetPaneRow  
 Возвращает указатель на [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)объекта место закрепления панели.  
  
```  
CDockingPanesRow* GetPaneRow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CDockingPanesRow` Если панель закреплена, или `NULL` , если он является перемещаемой.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для доступа к строке, место закрепления панели. Например, для размещения панелей в конкретной строке, вызовите `GetPaneRow` и затем вызвать [CDockingPanesRow::ArrangePanes](../../mfc/reference/cdockingpanesrow-class.md#arrangepanes).  
  
##  <a name="getpanestyle"></a>CBasePane::GetPaneStyle  
 Возвращает стиль панели.  
  
```  
virtual DWORD GetPaneStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сочетание стилей элементов управления панели (включая стили CBRS_), заданные с [CBasePane::SetPaneStyle](#setpanestyle) метод во время создания.  
  
##  <a name="getparentdocksite"></a>CBasePane::GetParentDockSite  
 Возвращает указатель на родительский сайт закрепления.  
  
```  
virtual CDockSite* GetParentDockSite() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Закрепление родительского сайта.  
  
##  <a name="getparentminiframe"></a>CBasePane::GetParentMiniFrame  
 Возвращает указатель области родительского окна.  
  
```  
virtual CPaneFrameWnd* GetParentMiniFrame(BOOL bNoAssert=FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bNoAssert`  
 Если `TRUE`, этот метод не проверяет наличие недействительных указателей. Если этот метод вызывается при завершении работы приложения, присвойте этому параметру значение `TRUE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель на родительское окно минифрейма Если панель открывается как плавающее окно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию, чтобы получить указатель на родительское окно области. Этот метод выполняется итерация по всем родительским элементам и проверяет наличие объект, производный от [CPaneFrameWnd класса](../../mfc/reference/cpaneframewnd-class.md).  
  
 Используйте `GetParentMiniFrame` для определения, является ли область плавающее окно.  
  
##  <a name="getparenttabbedpane"></a>CBasePane::GetParentTabbedPane  
 Возвращает указатель на панель с вкладками родительского.  
  
```  
CBaseTabbedPane* GetParentTabbedPane() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на родительский панель с вкладками, если он существует; в противном случае `NULL`.  
  
##  <a name="getparenttabwnd"></a>CBasePane::GetParentTabWnd  
 Возвращает указатель на родительское окно, на вкладке.  
  
```  
CMFCBaseTabCtrl* GetParentTabWnd(HWND& hWndTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `hWndTab`  
 Если возвращаемое значение не `NULL`, этот параметр содержит дескриптор родительского окна с вкладками.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель на родительский с вкладками окна или `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для получения указатель на родительское окно с вкладками. Иногда может быть недостаточно для вызова `GetParent`, так как область может находиться внутри закрепляющую оболочку ( [класса CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)) или внутри адаптера области ( [CDockablePaneAdapter класса](../../mfc/reference/cdockablepaneadapter-class.md)). С помощью `GetParentTabWnd` можно будет получить допустимый указатель в таких случаях (при условии, что родительского окна с вкладками).  
  
##  <a name="getrecentvisiblestate"></a>CBasePane::GetRecentVisibleState  
 Платформа вызывает этот метод при восстановлении область из архива.  
  
```  
virtual BOOL GetRecentVisibleState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `BOOL` , указывающий последнее состояние видимости. Если `TRUE`, области было видимым при сериализации и должны быть видимыми при восстановлении. Если `FALSE`, области был скрыт при сериализации и должны быть скрыты при восстановлении.  
  
##  <a name="hideinprintpreviewmode"></a>CBasePane::HideInPrintPreviewMode  
 Указывает, скрыт ли панели в режиме предварительного просмотра.  
  
```  
virtual BOOL HideInPrintPreviewMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область не отображается в режиме предварительного просмотра; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Базовый панели не отображаются в режиме предварительного просмотра. Таким образом, этот метод всегда возвращает `TRUE`.  
  
##  <a name="insertpane"></a>CBasePane::InsertPane  
 Регистрирует указанный панели в диспетчере закрепления.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pControlBar`  
 Указатель на область для вставки.  
  
 [in] `pTarget`  
 Указатель на соседней панели.  
  
 [in] `bAfter`  
 Если `TRUE`, `pControlBar` вставляется после `pTarget`. Если `FALSE`, `pControlBar` вставляется перед `pTarget`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно, `FALSE` в противном случае.  
  
##  <a name="isaccessibilitycompatible"></a>CBasePane::IsAccessibilityCompatible  
 Указывает, поддерживает ли области Active Accessibility.  
  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область поддерживает Active Accessibility; в противном случае `FALSE`.  
  
##  <a name="isautohidemode"></a>CBasePane::IsAutoHideMode  
 Определяет, является ли область в режиме автоматического скрытия.  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область находится в режиме автоматического скрытия. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Базовый областей нельзя автоматического скрытия. Этот метод всегда возвращает значение `FALSE`.  
  
##  <a name="isdialogcontrol"></a>CBasePane::IsDialogControl  
 Указывает, является ли область управления диалогового окна.  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель управления диалогового окна; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует этот метод для обеспечения согласованности макета для всех областей.  
  
##  <a name="isdocked"></a>CBasePane::IsDocked  
 Определяет, закреплена ли области.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если родительский области не мини-рамки или области открывается как плавающее окно в мини-рамки с другой области; в противном случае `FALSE`.  
  
##  <a name="isfloating"></a>CBasePane::IsFloating  
 Определяет, является ли область плавающее окно.  
  
```  
virtual BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель открывается как плавающее окно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает значение противоположной [CBasePane::IsDocked](#isdocked).  
  
##  <a name="ishorizontal"></a>CBasePane::IsHorizontal  
 Определяет, является ли панель закреплена горизонтально.  
  
```  
virtual BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель закреплена горизонтально. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию проверяет текущее выравнивание закрепления для `CBRS_ORIENT_HORZ`.  
  
##  <a name="isinfloatingmultipaneframewnd"></a>CBasePane::IsInFloatingMultiPaneFrameWnd  
 Указывает, является ли область в окне фрейма несколькими областями ( [CMultiPaneFrameWnd класса](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель в окне фрейма несколькими областями. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 В окне фрейма несколькими областями только закрепляемых областей можно с плавающей запятой. Таким образом `CBasePane::IsInFloatingMultiPaneFrameWnd` всегда возвращает `FALSE`.  
  
##  <a name="ismditabbed"></a>CBasePane::IsMDITabbed  
 Определяет, добавлен ли области в виде документа с вкладками дочернего окна MDI.  
  
```  
virtual BOOL IsMDITabbed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`При добавлении области дочернего окна MDI как документ с вкладками; в противном случае `FALSE`.  
  
##  <a name="ispanevisible"></a>CBasePane::IsPaneVisible  
 Указывает, является ли `WS_VISIBLE` флаг установлен для области.  
  
```  
BOOL IsPaneVisible() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `WS_VISIBLE` ; в противном случае — значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CBasePane::IsVisible](#isvisible) для определения области видимости.  
  
##  <a name="ispointneardocksite"></a>CBasePane::IsPointNearDockSite  
 Определяет, является ли указанная точка рядом с сайта закрепления.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Указанная точка.  
  
 [выходной] `dwBarAlignment`  
 Задает край приближается к точке. Возможными значениями являются `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP`, и`CBRS_ALIGN_BOTTOM`  
  
 [выходной] `bOuterEdge`  
 `TRUE`Если точка находится рядом с внешней границы сайта закрепления; `FALSE` в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если точка находится рядом с сайта закрепления; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Точка расположено сайта закрепления, когда он находится в пределах чувствительности, установите в диспетчере закрепления. Чувствительность по умолчанию — 15 пикселей.  
  
##  <a name="isresizable"></a>CBasePane::IsResizable  
 Определяет, можно ли изменять размер области.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области могут быть изменены пользователем; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Областях [класс CDockablePane](../../mfc/reference/cdockablepane-class.md) могут быть изменены.  
  
 В строке состояния ( [класса CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)) и закрепление панели ( [класс CDockSite](../../mfc/reference/cdocksite-class.md)) изменять нельзя.  
  
##  <a name="isrestoredfromregistry"></a>CBasePane::IsRestoredFromRegistry  
 Определяет, будет ли восстановлена панели из реестра.  
  
```  
virtual BOOL IsRestoredFromRegistry() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области восстанавливается из реестра; в противном случае `FALSE`.  
  
##  <a name="istabbed"></a>CBasePane::IsTabbed  
 Определяет ли области был вставлен в набор вкладок окна с вкладками.  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель элементов управления вставляется на вкладке окна с вкладками; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод извлекает указатель на ближайший родительский и определяет, является ли класс среды выполнения родительского элемента [CMFCBaseTabCtrl класса](../../mfc/reference/cmfcbasetabctrl-class.md).  
  
##  <a name="isvisible"></a>CBasePane::IsVisible  
 Определяет, будет ли видна панель.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область является видимым. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для определения области видимости. Не используйте `::IsWindowVisible`.  
  
 Если области не с вкладками (в разделе [CBasePane::IsTabbed](#istabbed)), этот метод проверяет `WS_VISIBLE` стиля. Если области вкладок, этот метод проверяет видимость родительского окна с вкладками. Если родительское окно является видимым, функция проверяет видимость области вкладки с помощью [CMFCBaseTabCtrl::IsTabVisible](../../mfc/reference/cmfcbasetabctrl-class.md#istabvisible).  
  
##  <a name="loadstate"></a>CBasePane::LoadState  
 Загружает состояние панели из реестра.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Имя профиля.  
  
 [in] `nIndex`  
 Индекс профиля.  
  
 [in] `uiID`  
 Идентификатор области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если состояние панели был загружен успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод загружает состояние панели из реестра. Его можно переопределить в производном классе, чтобы загрузить дополнительные данные, сохраненные в [CBasePane::SaveState](#savestate).  
  
##  <a name="movewindow"></a>CBasePane::MoveWindow  
 Перемещает область.  
  
```  
virtual HDWP MoveWindow(
    CRect& rect,  
    BOOL bRepaint = TRUE,  
    HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Прямоугольник, указав новое расположение и размер области.  
  
 [in] `bRepaint`  
 Если `TRUE`, окрашивание области. Если `FALSE`, области не разрешено.  
  
 [in] `hdwp`  
 Дескриптор структуру позиции отложенное окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор к структуре положение окна отложенного или `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Если передать `NULL` как `hdwp` параметра, этот метод перемещает окно обычным образом. Если передается дескриптор, этот метод выполняет отложенное перемещения. Дескриптор можно получить, вызвав [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672) или сохранив возвращаемое значение предыдущего вызова этого метода.  
  
##  <a name="onafterchangeparent"></a>CBasePane::OnAfterChangeParent  
 Вызывается структурой после изменения родительской области.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndOldParent`  
 Указатель на предыдущий родительский элемент.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод после родительской области изменений, обычно из-за операции закрепления или с плавающей запятой.  
  
 Реализация по умолчанию не выполняет никаких действий.  
  
##  <a name="onbeforechangeparent"></a>CBasePane::OnBeforeChangeParent  
 Вызывается платформой непосредственно перед панель изменяется родительского окна.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndNewParent`  
 Указатель на новый родительского окна.  
  
 [in] `bDelay`  
 Указывает, может быть задержана изменения макета.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод непосредственно перед изменений родительской области, обычно из-за закрепления, с плавающей запятой или операции автоматического скрытия.  
  
 Реализация по умолчанию не выполняет никаких действий.  
  
##  <a name="ondrawcaption"></a>CBasePane::OnDrawCaption  
 Этот метод вызывается платформой при отрисовке заголовка.  
  
```  
virtual void OnDrawCaption();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод не имеет функциональных возможностей для `CBasePane` класса.  
  
##  <a name="onmovepanedivider"></a>CBasePane::OnMovePaneDivider  
 В настоящее время этот метод не используется.  
  
```  
virtual void OnMovePaneDivider(CPaneDivider*);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `CPaneDivider*`  
 Не используется.  
  
##  <a name="onpanecontextmenu"></a>CBasePane::OnPaneContextMenu  
 Вызывается платформой при построении меню, которое содержит список областей.  
  
```  
virtual void OnPaneContextMenu(
    CWnd* pParentFrame,  
    CPoint point);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pParentFrame`  
 Указатель родительского фрейма.  
  
 [in] `point`  
 Указывает расположение в контекстном меню.  
  
### <a name="remarks"></a>Примечания  
 `OnPaneContextMenu`вызывает закрепления диспетчер, который ведет список областей, которые принадлежат к окну текущего кадра. Этот метод добавляет имена областей в контекстное меню и отображает его. Команды в меню, отображение или скрытие отдельных областей.  
  
 Переопределите этот метод для настройки этого поведения.  
  
##  <a name="onremovefromminiframe"></a>CBasePane::OnRemoveFromMiniFrame  
 Вызывается платформой при удалении области из родительского окна мини-рамки.  
  
```  
virtual void OnRemoveFromMiniFrame(CPaneFrameWnd* pMiniFrame);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMiniFrame`  
 Указатель из которого удаляется области окна области.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при удалении области из области родительского окна (в результате закрепления, например).  
  
 Реализация по умолчанию не выполняет никаких действий.  
  
##  <a name="onsetaccdata"></a>CBasePane::OnSetAccData  
 `CBasePane`не используйте этот метод.  
  
```  
virtual BOOL OnSetAccData(long lVal);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lVal`  
 Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="panefrompoint"></a>CBasePane::PaneFromPoint  
 Возвращает область, содержащее заданную точку.  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Указывает точку, в экранных координатах, для проверки.  
  
 [in] `nSensitivity`  
 Увеличьте область поиска на указанное значение. Панель будет удовлетворять условиям поиска, если заданная точка находится в области увеличения.  
  
 [in] `bExactBar`  
 `TRUE`Чтобы игнорировать `nSensitivity` параметр; в противном случае `FALSE`.  
  
 [in] `pRTCBarType`  
 В противном случае `NULL`, метод выполняет поиск только области заданного типа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `CBasePane`-Производного объекта, содержащее заданную точку или `NULL` Если области не был найден.  
  
##  <a name="recalclayout"></a>CBasePane::RecalcLayout  
 `CBasePane`не используйте этот метод.  
  
```  
virtual void RecalcLayout();
```  
  
##  <a name="removepanefromdockmanager"></a>CBasePane::RemovePaneFromDockManager  
 Отменяет регистрацию областью и удаляет его из списка в диспетчере закрепления.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pBar,  
    BOOL bDestroy = TRUE,  
    BOOL bAdjustLayout = FALSE,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на область для удаления.  
  
 [in] `bDestroy`  
 Если `TRUE`, уничтожается области удален.  
  
 [in] `bAdjustLayout`  
 Если `TRUE`, настроить макет закрепления немедленно.  
  
 [in] `bAutoHide`  
 Если `TRUE`, макет закрепления относится к списку автоматическое скрытие панелей. Если `FALSE`, макет закрепления связан список регулярных панелей.  
  
 [in] `pBarReplacement`  
 Указатель на область, которая заменяет области удален.  
  
##  <a name="savestate"></a>CBasePane::SaveState  
 Сохраняет состояние панели в реестр.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszProfileName`  
 Имя профиля.  
  
 [in] `nIndex`  
 Индекс профиля.  
  
 [in] `uiID`  
 Идентификатор области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если состояние была сохранена успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой при сохраняет состояние панели в реестр. Переопределить `SaveState` в производном классе для хранения дополнительных сведений.  
  
##  <a name="selectdefaultfont"></a>CBasePane::SelectDefaultFont  
 Выбирает шрифт по умолчанию для контекста заданного устройства.  
  
```  
CFont* SelectDefaultFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Контекст устройства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на значение по умолчанию [CFont-класс](../../mfc/reference/cfont-class.md) объекта.  
  
##  <a name="setcontrolbarstyle"></a>CBasePane::SetControlBarStyle  
 Задает стиль панели управления.  
  
```  
virtual void SetControlBarStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwNewStyle`  
 Побитовый оператор или сочетание следующих значений.  
  
|Стиль|Описание:|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Делает float панели управления.|  
|`AFX_CBRS_AUTOHIDE`|Включает режим автоматического скрытия.|  
|`AFX_CBRS_RESIZE`|Включает изменение размера панели элементов управления. Если этот флаг установлен, на панели управления может быть помещен в закрепляемую панель.|  
|`AFX_CBRS_CLOSE`|Обеспечивает скрытие панели элементов управления.|  
  
##  <a name="setdockingmode"></a>CBasePane::SetDockingMode  
 Задает режим для области закрепления.  
  
```  
void SetDockingMode(AFX_DOCK_TYPE dockModeNew);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dockModeNew`  
 Задает новый режим закрепления для области.  
  
### <a name="remarks"></a>Примечания  
 Платформа поддерживает два режима закрепления: стандартные и интерпретации.  
  
 В стандартном режиме закрепления панели и окна перемещаются вокруг с помощью прямоугольника перетаскивания. В режиме интерпретации закрепляемых панелей элементов управления и окна перемещаются немедленно вместе с контекстом.  
  
 Изначально режим закрепления определяется по глобально [CDockingManager::m_dockModeGlobal](../../mfc/reference/cdockingmanager-class.md#m_dockmodeglobal). Можно задать режим закрепления для каждой области по отдельности с помощью `SetDockingMode` метод.  
  
##  <a name="setpanealignment"></a>CBasePane::SetPaneAlignment  
 Задает выравнивание для области.  
  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwAlignment`  
 Задает новый выравнивание.  
  
### <a name="remarks"></a>Примечания  
 Как правило, этот метод вызывается платформой при присоединении панель с одной стороны главного фрейма в другой.  
  
 В следующей таблице показаны возможные значения для `dwAlignment`:  
  
|Значение|Выравнивание|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|Выравнивание по левому краю.|  
|`CBRS_ALIGN_RIGHT`|Выравнивание по правому краю.|  
|`CBRS_ALIGN_TOP`|Выравнивание по верхнему краю.|  
|`CBRS_ALIGN_BOTTOM`|Выравнивание нижней.|  
  
##  <a name="setpanestyle"></a>CBasePane::SetPaneStyle  
 Задает стиль окна.  
  
```  
virtual void SetPaneStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwNewStyle`  
 Указывает новый стиль для задания.  
  
### <a name="remarks"></a>Примечания  
 Этот метод может использоваться, чтобы устанавливать любые CBRS_ стили, которые определены в файле afxres.h. Поскольку стиль панели и выравнивание панели хранятся вместе, задайте новый стиль, сочетая ее с текущее выравнивание следующим образом.  
  
 `pPane->SetPaneStyle (pPane->GetCurrentAlignment() | CBRS_TOOLTIPS);`  
  
##  <a name="setwindowpos"></a>CBasePane::SetWindowPos  
 Изменяет размер, положение и Z-порядок области.  
  
```  
virtual HDWP SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags,  
    HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndInsertAfter`  
 Идентифицирует `CWnd` объекта, который предшествует это `CWnd` объекта в Z-порядке. Дополнительные сведения см. в разделе [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).  
  
 [in] `x`  
 Задает позицию левого края окна.  
  
 [in] `y`  
 Задает позицию верхнего края окна.  
  
 [in] `cx`  
 Задает ширину окна.  
  
 [in] `cy`  
 Указывает высоту окна.  
  
 [in] `nFlags`  
 Указывает параметры размера и положения. Дополнительные сведения см. в разделе [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).  
  
 [in] `hdwp`  
 Ссылка на структуру, содержащую сведения о размере и позиции для одного или нескольких окон.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор структуру позиции обновленное отложенное окно или `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Если `pWndInsertAfter` — `NULL`, этот метод вызывает метод [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos). Если `pWndInsertAfter` не является `NULL`, этот метод вызывает метод `DeferWindowPos`.  
  
##  <a name="showpane"></a>CBasePane::ShowPane  
 Показывает или скрывает панель.  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShow`  
 Указывает, следует ли отображать ( `TRUE`) или скрыть ( `FALSE`) областью.  
  
 [in] `bDelay`  
 Если `TRUE`, повторное вычисление макет закрепления откладывается.  
  
 [in] `bActivate`  
 Если `TRUE`, область активна, при отображении.  
  
### <a name="remarks"></a>Примечания  
 Этот метод отображает или скрывает панель. Используйте этот метод, а не `ShowWindow` , так как этот метод уведомляет соответствующие закрепления диспетчеры об изменениях в области видимости.  
  
 Используйте [CBasePane::IsVisible](#isvisible) для определения текущей области видимости.  
  
##  <a name="stretchpane"></a>CBasePane::StretchPane  
 Растягивает панель по вертикали или горизонтали.  
  
```  
virtual CSize StretchPane(
    int nLength,  
    BOOL bVert);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nLength`  
 Длина, с помощью которого для растяжения области.  
  
 [in] `bVert`  
 Если `TRUE`, растянуть области по вертикали. Если `FALSE`, растянуть панели по горизонтали.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер области растяжением.  
  
##  <a name="undockpane"></a>CBasePane::UndockPane  
 Удаляет область из сайта закрепления, по умолчанию ползунок или окна области, где он в настоящее время закреплен.  
  
```  
virtual void UndockPane(BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bDelay`  
 Значение TRUE, если макет закрепления не пересчитывается немедленно.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для изменения состояния панели или исключить из макет закрепления панели.  
  
 Если вы хотите продолжать использовать эту панель, вызвать либо метод [CBasePane::DockPane](#dockpane) или [CBasePane::FloatPane](#floatpane) перед вызовом этого метода.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [Класс CWnd](../../mfc/reference/cwnd-class.md)
