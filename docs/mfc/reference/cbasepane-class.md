---
title: "Класс CBasePane | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- get_accState method
- get_accHelp method
- CBasePane class
- accLocation method
- accHitTest method
- get_accDescription method
- get_accDefaultAction method
- get_accName method
- get_accFocus method
- get_accRole method
- get_accValue method
- get_accChild method
- accSelect method
- get_accKeyboardShortcut method
- get_accChildCount method
- Serialize method
- PreTranslateMessage method
- get_accParent method
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
caps.latest.revision: 43
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0444c0647d83a1e9b431dd0c5bdb369da213b91b
ms.lasthandoff: 02/24/2017

---
# <a name="cbasepane-class"></a>Класс CBasePane
Базовый класс для всех панелей в MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBasePane : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CBasePane::CBasePane`|Конструктор по умолчанию.|  
|`CBasePane::~CBasePane`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CBasePane::accHitTest`|Вызывается платформой для извлечения дочернего элемента или дочернего объекта в заданной точке экрана. (Переопределяет [CWnd::accHitTest](../../mfc/reference/cwnd-class.md#acchittest).)|  
|`CBasePane::accLocation`|Вызывается платформой для получения текущее местоположение на экране для указанного объекта. (Переопределяет [CWnd::accLocation](../../mfc/reference/cwnd-class.md#acclocation).)|  
|[CBasePane::AccNotifyObjectFocusEvent](#accnotifyobjectfocusevent)|`CBasePane`не используйте этот метод.|  
|`CBasePane::accSelect`|Вызывается платформой для изменения выбранной области или перемещения фокуса клавиатурного ввода указанного объекта. (Переопределяет [CWnd::accSelect](../../mfc/reference/cwnd-class.md#accselect).)|  
|[CBasePane::AddPane](#addpane)|Добавляет диспетчеру закрепления панели.|  
|[CBasePane::AdjustDockingLayout](#adjustdockinglayout)|Перенаправляет вызов закрепления manager для настройки макета закрепления.|  
|[CBasePane::AdjustLayout](#adjustlayout)|Вызывается инфраструктурой при области следует изменить его внутренней структуры.|  
|[CBasePane::CalcFixedLayout](#calcfixedlayout)|Вычисляет размер панели элементов управления по горизонтали.|  
|[CBasePane::CanAcceptPane](#canacceptpane)|Определяет ли другую панель можно закрепить области.|  
|[CBasePane::CanAutoHide](#canautohide)|Определяет, поддерживает ли области режима автоматического скрытия.|  
|[CBasePane::CanBeAttached](#canbeattached)|Определяет ли область можно прикрепить к другой области.|  
|[CBasePane::CanBeClosed](#canbeclosed)|Определяет, можно ли закрыть области.|  
|[CBasePane::CanBeDocked](#canbedocked)|Определяет ли область можно прикрепить к другой области.|  
|[CBasePane::CanBeResized](#canberesized)|Определяет, возможно ли изменение размеров панели.|  
|[CBasePane::CanBeTabbedDocument](#canbetabbeddocument)|Указывает, можно ли преобразовать области документа с вкладками MDI.|  
|[CBasePane::CanFloat](#canfloat)|Определяет, может перемещаться ли области.|  
|[CBasePane::CanFocus](#canfocus)|Указывает, является ли область может получать фокус.|  
|[CBasePane::CopyState](#copystate)|Копирует состояние данной области.|  
|[CBasePane::CreateDefaultMiniframe](#createdefaultminiframe)|Если панель может перемещаться, создает окна области.|  
|[CBasePane::CreateEx](#createex)|Создает элемент управления.|  
|[CBasePane::DockPane](#dockpane)|Закрепляет область в другую область или фрейме окна.|  
|[CBasePane::DockPaneUsingRTTI](#dockpaneusingrtti)|Закрепляет область, используя сведения о типах во время выполнения.|  
|[CBasePane::DockToFrameWindow](#docktoframewindow)|Закрепляет Закрепляемая область кадра.|  
|[CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Определяет, может ли другой области динамически вставляются между этой панели и родительского фрейма.|  
|[CBasePane::EnableDocking](#enabledocking)|Включает Закрепление панели в основном фрейме.|  
|[CBasePane::EnableGripper](#enablegripper)|Включает или отключает захвата. Если включен захвата, пользователь может перетаскивать его, чтобы изменить положение панели.|  
|`CBasePane::FillWindowRect`|Для внутреннего использования.|  
|[CBasePane::FloatPane](#floatpane)|Смещает области.|  
|`CBasePane::get_accChild`|Вызывается платформой для извлечения адреса интерфейса `IDispatch` для указанного дочернего элемента. (Переопределяет [CWnd::get_accChild](../../mfc/reference/cwnd-class.md#get_accchild).)|  
|`CBasePane::get_accChildCount`|Вызывается платформой для получения число дочерних объектов, принадлежащих этому объекту. (Переопределяет [CWnd::get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount).)|  
|`CBasePane::get_accDefaultAction`|Вызывается средой, чтобы получить строку, описывающую выполняемое по умолчанию для объекта. (Переопределяет [CWnd::get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction).)|  
|`CBasePane::get_accDescription`|Вызывается платформой для извлечения строки, описывающей внешний вид указанного объекта. (Переопределяет [CWnd::get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription).)|  
|`CBasePane::get_accFocus`|Вызывается платформой для извлечения объекта, имеющего фокус клавиатурного ввода. (Переопределяет [CWnd::get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus).)|  
|`CBasePane::get_accHelp`|Вызывается платформой для получения строки свойства Help для объекта. (Переопределяет [CWnd::get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp).)|  
|[CBasePane::get_accHelpTopic](#get_acchelptopic)|Вызывается средой, чтобы получить полный путь файла WinHelp, связанного с указанным объектом и идентификатор в соответствующем разделе этого файла. (Переопределяет [CWnd::get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic).)|  
|`CBasePane::get_accKeyboardShortcut`|Вызывается платформой для получения заданное сочетание клавиш для объекта. (Переопределяет [CWnd::get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut).)|  
|`CBasePane::get_accName`|Вызывается платформой для извлечения имени указанного объекта. (Переопределяет [CWnd::get_accName](../../mfc/reference/cwnd-class.md#get_accname).)|  
|`CBasePane::get_accParent`|Вызывается платформой для получения `IDispatch` интерфейс для родительского объекта. (Переопределяет [CWnd::get_accParent](../../mfc/reference/cwnd-class.md#get_accparent).)|  
|`CBasePane::get_accRole`|Вызывается платформой для извлечения информации, описывающей роль указанного объекта. (Переопределяет [CWnd::get_accRole](../../mfc/reference/cwnd-class.md#get_accrole).)|  
|[CBasePane::get_accSelection](#get_accselection)|Вызывается платформой для извлечения выбранного дочернего элемента этого объекта. (Переопределяет [CWnd::get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection).)|  
|`CBasePane::get_accState`|Вызывается платформой для извлечения текущего состояния указанного объекта. (Переопределяет [CWnd::get_accState](../../mfc/reference/cwnd-class.md#get_accstate).)|  
|`CBasePane::get_accValue`|Вызывается платформой для извлечения значения указанного объекта. (Переопределяет [CWnd::get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue).)|  
|[CBasePane::GetCaptionHeight](#getcaptionheight)|Возвращает высоту заголовка.|  
|[CBasePane::GetControlBarStyle](#getcontrolbarstyle)|Возвращает стиль панели управления.|  
|[CBasePane::GetCurrentAlignment](#getcurrentalignment)|Возвращает текущее выравнивание панели.|  
|[CBasePane::GetDockingMode](#getdockingmode)|Возвращает текущий режим закрепления панели.|  
|[CBasePane::GetDockSiteFrameWnd](#getdocksiteframewnd)|Возвращает указатель на сайте закрепления панели окна.|  
|[CBasePane::GetEnabledAlignment](#getenabledalignment)|Возвращает CBRS_ALIGN_ стили, которые применяются к области.|  
|[CBasePane::GetMFCStyle](#getmfcstyle)|Возвращает стили панели с MFC.|  
|[CBasePane::GetPaneIcon](#getpaneicon)|Возвращает дескриптор для значка панели.|  
|`CBasePane::GetPaneRect`|Для внутреннего использования.|  
|[CBasePane::GetPaneRow](#getpanerow)|Возвращает указатель на [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)объекта место закрепления панели.|  
|[CBasePane::GetPaneStyle](#getpanestyle)|Возвращает стиль панели.|  
|[CBasePane::GetParentDockSite](#getparentdocksite)|Возвращает указатель на родительский сайт закрепления.|  
|[CBasePane::GetParentMiniFrame](#getparentminiframe)|Возвращает указатель окна родительской области.|  
|[CBasePane::GetParentTabbedPane](#getparenttabbedpane)|Возвращает указатель на область с вкладками родительского.|  
|[CBasePane::GetParentTabWnd](#getparenttabwnd)|Возвращает указатель, находящийся внутри вкладки родительского окна.|  
|[CBasePane::GetRecentVisibleState](#getrecentvisiblestate)|Платформа вызывает этот метод, когда область восстанавливается из архива.|  
|[CBasePane::HideInPrintPreviewMode](#hideinprintpreviewmode)|Указывает, скрыт ли панели в режиме предварительного просмотра.|  
|[CBasePane::InsertPane](#insertpane)|Регистрация указанной области закрепления диспетчером.|  
|[CBasePane::IsAccessibilityCompatible](#isaccessibilitycompatible)|Указывает, поддерживает ли области Active Accessibility.|  
|[CBasePane::IsAutoHideMode](#isautohidemode)|Определяет, является ли область в режиме автоматического скрытия.|  
|[CBasePane::IsDialogControl](#isdialogcontrol)|Указывает, является ли область элемента управления диалогового окна.|  
|[CBasePane::IsDocked](#isdocked)|Определяет, закреплен ли области.|  
|[CBasePane::IsFloating](#isfloating)|Определяет, ли плавающей панели.|  
|[CBasePane::IsHorizontal](#ishorizontal)|Определяет, является ли панель закреплена горизонтально.|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Указывает, является ли область в окне фрейма с несколькими областями.|  
|[CBasePane::IsMDITabbed](#ismditabbed)|Определяет, были ли добавлены области дочернюю MDI как документ с вкладками.|  
|[CBasePane::IsPaneVisible](#ispanevisible)|Указывает, является ли `WS_VISIBLE` флаг для области.|  
|[CBasePane::IsPointNearDockSite](#ispointneardocksite)|Определяет, является ли указанная точка рядом с сайта закрепления.|  
|[CBasePane::IsResizable](#isresizable)|Определяет, возможно ли изменение размеров панели.|  
|[CBasePane::IsRestoredFromRegistry](#isrestoredfromregistry)|Определяет, будет ли восстановлена области из реестра.|  
|[CBasePane::IsTabbed](#istabbed)|Определяет, ввела ли области в элементе управления "Вкладка" окна с вкладками.|  
|`CBasePane::IsTooltipTopmost`|Для внутреннего использования.|  
|[CBasePane::IsVisible](#isvisible)|Определяет, будет ли видна панель.|  
|[CBasePane::LoadState](#loadstate)|Загружает состояние области из реестра.|  
|[CBasePane::MoveWindow](#movewindow)|Перемещение области.|  
|[CBasePane::OnAfterChangeParent](#onafterchangeparent)|Вызывается платформой после изменения родительской области.|  
|[CBasePane::OnBeforeChangeParent](#onbeforechangeparent)|Вызывается средой перед изменения области родительского окна.|  
|[CBasePane::OnDrawCaption](#ondrawcaption)|Платформа вызывает этот метод при отрисовке заголовка.|  
|[CBasePane::OnMovePaneDivider](#onmovepanedivider)|В настоящее время этот метод не используется.|  
|[CBasePane::OnPaneContextMenu](#onpanecontextmenu)|Вызывается инфраструктурой при построении меню, которое содержит список областей.|  
|[CBasePane::OnRemoveFromMiniFrame](#onremovefromminiframe)|Вызывается платформой, когда область удаляется из родительского окна мини-кадра.|  
|[CBasePane::OnSetAccData](#onsetaccdata)|`CBasePane`не используйте этот метод.|  
|`CBasePane::OnUpdateCmdUI`|Для внутреннего использования.|  
|[CBasePane::PaneFromPoint](#panefrompoint)|Возвращает область, содержащую заданной точки.|  
|`CBasePane::PreTranslateMessage`|Используется классом [CWinApp](../../mfc/reference/cwinapp-class.md) для перевода оконных сообщений перед их отправкой [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CBasePane::RecalcLayout](#recalclayout)|`CBasePane`не используйте этот метод.|  
|[CBasePane::RemovePaneFromDockManager](#removepanefromdockmanager)|Отменяет регистрацию область и удаляет его из списка в диспетчере закрепления.|  
|[CBasePane::SaveState](#savestate)|Сохраняет состояние панели в реестр.|  
|[CBasePane::SelectDefaultFont](#selectdefaultfont)|Выбирает шрифт по умолчанию для контекста заданного устройства.|  
|`CBasePane::Serialize`|Считывает этот объект из архива или записывает в него. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CBasePane::SetControlBarStyle](#setcontrolbarstyle)|Задает стиль панели управления.|  
|[CBasePane::SetDockingMode](#setdockingmode)|Задает режим закрепления панели.|  
|`CBasePane::SetMDITabbed`|Для внутреннего использования.|  
|[CBasePane::SetPaneAlignment](#setpanealignment)|Задает выравнивание для области.|  
|`CBasePane::SetPaneRect`|Для внутреннего использования.|  
|[CBasePane::SetPaneStyle](#setpanestyle)|Задает стиль панели.|  
|`CBasePane::SetRestoredFromRegistry`|Для внутреннего использования.|  
|[CBasePane::SetWindowPos](#setwindowpos)|Изменение размера, положения и Z-порядок области.|  
|[CBasePane::ShowPane](#showpane)|Отображение или скрытие панели.|  
|[CBasePane::StretchPane](#stretchpane)|Растягивает панель по вертикали или горизонтали.|  
|[CBasePane::UndockPane](#undockpane)|Удаление области из сайта закрепления, по умолчанию ползунок или окна области, где он в настоящее время закреплен.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBasePane::DoPaint](#dopaint)|Заполняет фон панели.|  
  
## <a name="remarks"></a>Примечания  
 Если вы хотите создать класс области, которая поддерживает расширенные функции закрепления, доступные в MFC, необходимо выполнить наследование из `CBasePane` или [CPane класса](../../mfc/reference/cpane-class.md).  
  
## <a name="customization-tips"></a>Советы по настройке  
 Следующие советы по настройке относятся к `CBasePane Class` и любые классы, производные от него:  
  
-   При создании области, можно применить несколько новых стилей.  
  
    - `AFX_CBRS_FLOAT`делает области с плавающей запятой.  
  
    - `AFX_CBRS_AUTOHIDE`Включение автоматического скрытия режиме.  
  
    - `AFX_CBRS_CLOSE`позволяет области закрывается (скрытый).  
  
     Это флаги, которые можно комбинировать с помощью побитового или операции.  
  
 `CBasePane`реализует следующие виртуальные методы типа Boolean для отражения этих флагов: [CBasePane::CanBeClosed](#canbeclosed), [CBasePane::CanAutoHide](#canautohide), [CBasePane::CanFloat](#canfloat). Их можно переопределить в производных классах для настройки их поведения.  
  
-   Можно настроить поведение прикрепления путем переопределения [CBasePane::CanAcceptPane](#canacceptpane). Иметь свою собственную панель возвращать `FALSE` из этого метода, чтобы предотвратить другой области закрепления к нему.  
  
-   Если вы хотите создать статический область, не могут перемещаться и, запрещает закрепление перед любой другой панели (аналогично панели Outlook в примере OutlookDemo), создайте его и не с плавающей запятой и переопределить [CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore) для возврата `FALSE`. Реализация по умолчанию возвращает `FALSE` Если область создана без `AFX_CBRS_FLOAT` стиль.  
  
-   Создайте все области с идентификаторами отличные от -1.  
  
-   Чтобы определить область видимости, используйте [CBasePane::IsVisible](#isvisible). Правильно обрабатывает состояние видимости в виде вкладок и режимы автоматического скрытия.  
  
-   Если вы хотите создать изменяемые области, не с плавающей запятой, создайте его без `AFX_CBRS_FLOAT` стиля и вызов [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).  
  
-   Вызов для исключения из макета закрепления области или удалить панель инструментов с его Закрепление панели, [CBasePane::UndockPane](#undockpane). Не вызывайте этот метод для панелей в режиме автоматического скрытия или для областей, которые находятся на вкладках окон с вкладками.  
  
-   Если вы хотите float или отменить закрепление панели, которая находится в режиме автоматического скрытия, необходимо вызвать [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode) с `FALSE` в качестве первого аргумента, перед вызовом метода [CBasePane::FloatPane](#floatpane) или [CBasePane::UndockPane](#undockpane).  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как использовать различные методы в `CBasePane` класса. В примере показано, как извлечь область из `CFrameWndEx` класса и Установка режима закрепления, выравнивание по области и стиль панели. Фрагмент кода взят из [Word Pad образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&#2;](../../mfc/reference/codesnippet/cpp/cbasepane-class_1.cpp)]  
  
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
 Добавляет диспетчеру закрепления панели.  
  
```  
void AddPane(CBasePane* pBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на область для добавления.  
  
### <a name="remarks"></a>Примечания  
 Это удобный метод, который добавляет область закрепления manager. С помощью этого метода, не нужно писать код, который анализирует тип родительского фрейма.  
  
 Дополнительные сведения см. в разделе [класса CDockingManager](../../mfc/reference/cdockingmanager-class.md) и [CMDIFrameWndEx::AddPane](../../mfc/reference/cmdiframewndex-class.md#addpane).  
  
##  <a name="adjustdockinglayout"></a>CBasePane::AdjustDockingLayout  
 Перенаправляет вызов закрепления manager для настройки макета закрепления.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `hdwp`  
 Дескриптор структуру, содержащую несколько положение окон.  
  
### <a name="remarks"></a>Примечания  
 Это удобный метод, который настраивает макета закрепления. С помощью этого метода, не нужно писать код, который анализирует тип родительского фрейма.  
  
 Дополнительные сведения см. в разделе [CDockingManager::AdjustDockingLayout](../../mfc/reference/cdockingmanager-class.md#adjustdockinglayout)  
  
##  <a name="adjustlayout"></a>CBasePane::AdjustLayout  
 Вызывается платформой для настройки макета внутренней области.  
  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда область, который необходимо настроить его внутренней структуры. Базовая реализация ничего не делает.  
  
##  <a name="calcfixedlayout"></a>CBasePane::CalcFixedLayout  
 Вычисляет размер панели элементов управления по горизонтали.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bStretch`  
 Указывает, должен быть растянут панели, размер рамки. `bStretch` Параметр имеет ненулевое значение, при панели не прикрепляемые панели (недоступно для закрепления) и 0 при закрепленными или плавающими (доступно для закрепления).  
  
 [in] `bHorz`  
 Указывает, что полоса является горизонтально или вертикально. `bHorz` Параметр имеет ненулевое значение, если панель горизонтальный и равно 0, если это вертикально.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Панель элементов управления размер в точках из `CSize` объекта.  
  
### <a name="remarks"></a>Примечания  
 См. раздел примечания в [CControlBar::CalcFixedLayout](../../mfc/reference/ccontrolbar-class.md#calcfixedlayout)  
  
##  <a name="canacceptpane"></a>CBasePane::CanAcceptPane  
 Определяет ли другую панель можно закрепить области.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на панели, чтобы закрепить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если другой области могут приниматься; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод перед его закрепляет область, определяемое `pBar` в текущей области.  
  
 Используйте этот метод и [CBasePane::CanBeDocked](#canbedocked) способом управления как закрепление панелей в другие области в приложении.  
  
 Реализация по умолчанию возвращает значение `FALSE`.  
  
##  <a name="canautohide"></a>CBasePane::CanAutoHide  
 Определяет, поддерживает ли области режима автоматического скрытия.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если эта область поддерживает режим автоматического скрытия. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает эту функцию для определения того, поддерживает ли режим автоматического скрытия панели.  
  
 Во время построения, эту возможность можно задать, передав `AFX_CBRS_AUTOHIDE` флаг [CBasePane::CreateEx](#createex).  
  
 Реализация по умолчанию проверяет `AFX_CBRS_AUTOHIDE` флаг. Переопределите этот метод в производном классе, чтобы изменить это поведение.  
  
##  <a name="canbeattached"></a>CBasePane::CanBeAttached  
 Определяет ли область можно прикрепить к другой области окна или рамке окна.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область можно прикрепить к другой области или рамки окна; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию возвращает значение `FALSE`. Переопределите этот метод в производном классе, чтобы включить или отключить возможность закрепления без вызова [CBasePane::EnableDocking](#enabledocking).  
  
##  <a name="canbeclosed"></a>CBasePane::CanBeClosed  
 Определяет, можно ли закрыть области.  
  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область может быть закрыт; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, чтобы определить, можно ли закрыть области. Если метод возвращает `TRUE`, **закрыть** добавляется кнопка заголовка панели или, если плавающей панели в строке заголовка области окна области.  
  
 Во время построения, эту возможность можно задать, передав `AFX_CBRS_CLOSE` флаг [CBasePane::CreateEx](#createex).  
  
 Реализация по умолчанию проверяет `AFX_CBRS_CLOSE` флаг.  
  
##  <a name="canbedocked"></a>CBasePane::CanBeDocked  
 Определяет ли область можно прикрепить к другой области.  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDockBar`  
 Указатель на другую панель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если в этой области можно прикрепить к другой области; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод перед его закрепляет область, определяемое `pDockBar` в текущей области.  
  
 Используйте этот метод и [CBasePane::CanAcceptPane](#canacceptpane) способом управления как закрепление панелей в другие области в приложении.  
  
 Реализация по умолчанию возвращает значение `FALSE`.  
  
##  <a name="canberesized"></a>CBasePane::CanBeResized  
 Определяет, возможно ли изменение размеров панели.  
  
```  
virtual BOOL CanBeResized() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область может быть изменен; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод проверяет `AFX_CBRS_RESIZE` флаг, который задан по умолчанию в `CBasePane::OnCreate`. Если этот флаг не задан, закрепления manager флаги внутренне недвижимое, вместо его закрепления панели.  
  
##  <a name="canbetabbeddocument"></a>CBasePane::CanBeTabbedDocument  
 Указывает, можно ли преобразовать области документа с вкладками MDI.  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области могут быть преобразованы в документ с вкладками. в противном случае — `FALSE`. Параметр `CBasePane::CanBeTabbedDocument` всегда возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Только объекты, определенные `CBasePane`-производные типы, такие как [CDockablePane класса](../../mfc/reference/cdockablepane-class.md), можно преобразовать в документы с вкладками.  
  
##  <a name="canfloat"></a>CBasePane::CanFloat  
 Определяет, может перемещаться ли области.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель может перемещаться; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод для определения, может перемещаться ли области.  
  
 Во время построения, эту возможность можно задать, передав `AFX_CBRS_FLOAT` флаг [CBasePane::CreateEx](#createex).  
  
> [!NOTE]
>  Платформа предполагается, что не плавающей панели являются статическими и что нельзя изменить их состояние закрепления. Таким образом платформа не сохраняет состояние стыковки-плавающей панели.  
  
 Реализация по умолчанию проверяет `AFX_CBRS_FLOAT` стиль.  
  
##  <a name="canfocus"></a>CBasePane::CanFocus  
 Указывает, является ли область может получать фокус.  
  
```  
virtual BOOL CanFocus() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область может получать фокус; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе для управления фокус ввода. Например, так как панели инструментов, не может получать фокус, этот метод возвращает `FALSE` при вызове для объектов панели инструментов.  
  
 Платформа framework пытается установить фокус ввода при области закрепления или перемещению.  
  
##  <a name="copystate"></a>CBasePane::CopyState  
 Копирует состояние данной области.  
  
```  
virtual void CopyState(CBasePane* pOrgBar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pOrgBar`  
 Указатель на другую панель.  
  
### <a name="remarks"></a>Примечания  
 Этот метод копирует состояние из `pOrgBar` в эту область.  
  
##  <a name="createdefaultminiframe"></a>CBasePane::CreateDefaultMiniframe  
 Если панель может перемещаться, этот метод создает окна области для него.  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rectInitial`  
 Задает начальные координаты окна области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на новые окна области или `NULL` при создании произошла ошибка.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод после переключения панель в плавающем состоянии. Метод создает окна области и присоединяет панели этого окна.  
  
 Реализация по умолчанию возвращает значение `NULL`.  
  
##  <a name="createex"></a>CBasePane::CreateEx  
 Создает элемент управления.  
  
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
 Расширенные стили (см. [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) Дополнительные сведения).  
  
 [in] `lpszClassName`  
 Имя класса окна.  
  
 [in] `lpszWindowName`  
 Имя окна.  
  
 [in] `dwStyle`  
 Стиль окна (см. [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)).  
  
 [in] `rect`  
 Исходного прямоугольника.  
  
 [in] `pParentWnd`  
 Указатель на родительское окно.  
  
 [in] `nID`  
 Указывает идентификатор области. Должно быть уникальным.  
  
 [in] `dwControlBarStyle`  
 Флагов стилей для панели.  
  
 [in] `pContext`  
 Указатель на`CcreateContext`  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область создана успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Создает окно класса `lpszClassName`. При указании `WS_CAPTION`, этот метод очищает `WS_CAPTION` бит стиля и наборы `CBasePane::m_bHasCaption` для `TRUE`, так как библиотека не поддерживает области с субтитрами.  
  
 Можно использовать любое сочетание стили дочернего окна и панель (CBRS_) стили элементов управления MFC.  
  
 Библиотека добавляет несколько новых стилей для панели. В следующей таблице описаны новые стили:  
  
|Стиль|Описание|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Может быть плавающей панели.|  
|`AFX_CBRS_AUTOHIDE`|Область поддерживает режим автоматического скрытия|  
|`AFX_CBRS_RESIZE`|Возможность изменения размера области. **Важно:** этот стиль не реализован.|  
|`AFX_CBRS_CLOSE`|Области могут быть закрыты.|  
|`AFX_CBRS_AUTO_ROLLUP`|Возможность выполнять сведение области, когда она перемещается.|  
|`AFX_CBRS_REGULAR_TABS`|При закрепляет одной области в другую область, в которой этот стиль, создается регулярное окна с вкладками. (Дополнительные сведения см. в разделе [CTabbedPane класса](../../mfc/reference/ctabbedpane-class.md).)|  
|`AFX_CBRS_OUTLOOK_TABS`|Когда закрепляет одной области в другую область, в которой этот стиль, создается окна с вкладками стиле Outlook. (Дополнительные сведения см. в разделе [CMFCOutlookBar класса](../../mfc/reference/cmfcoutlookbar-class.md).)|  
  
 Чтобы использовать новые стили, укажите их в `dwControlBarStyle`.  
  
##  <a name="dockpane"></a>CBasePane::DockPane  
 Закрепляет область в другую область или фрейме окна.  
  
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
 Указывает прямоугольник назначения.  
  
 [in] `dockMethod`  
 Задает метод закрепления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель элементов управления был закреплен успешно; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для закрепить в области в другую область или Закрепить панель ( [класса CDockSite](../../mfc/reference/cdocksite-class.md)), заданным `pDockBar`, или для главного фрейма Если `pDockBar` — `NULL`.  
  
 `dockMethod`Задает способ закрепления панели. В разделе [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) список возможных значений.  
  
##  <a name="dockpaneusingrtti"></a>CBasePane::DockPaneUsingRTTI  
 Закрепляет область, используя сведения о типах во время выполнения.  
  
```  
void DockPaneUsingRTTI(BOOL bUseDockSite);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bUseDockSite`  
 Если `TRUE`, закрепить стыковочного узла. Если `FALSE`, закрепить родительского фрейма.  
  
##  <a name="docktoframewindow"></a>CBasePane::DockToFrameWindow  
 Закрепляет Закрепляемая область кадра.  
  
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
 Сторона, нужно закрепить области родительского фрейма.  
  
 [in] `lpRect`  
 Требуемый размер.  
  
 [in] `dwDockFlags`  
 Не обрабатывается.  
  
 [in] `pRelativeBar`  
 Не обрабатывается.  
  
 [in] `nRelativeIndex`  
 Не обрабатывается.  
  
 [in] `bOuterEdge`  
 Если `TRUE` и нет других закрепляемых областей на стороне, заданные `dwAlignment`, панель закреплена за пределами области, ближе к краю родительского фрейма. Если `FALSE`, области закреплена ближе к центру клиентской области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод был выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод не выполняется, если разделитель области ( [CPaneDivider класса](../../mfc/reference/cpanedivider-class.md)) не может быть создан. В противном случае — всегда возвращает `TRUE`.  
  
##  <a name="doesallowdyninsertbefore"></a>CBasePane::DoesAllowDynInsertBefore  
 Определяет, может ли другой области динамически вставляются между этой панели и родительского фрейма.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если пользователь может вставить другой области; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, чтобы определить, может ли пользователь динамически вставить области перед этой панели.  
  
 Например предположим, что приложение создается область, подключаемые к левому краю фрейма (например, панели Outlook). Чтобы предотвратить закрепление другую область слева от первой области, переопределите этот метод и вернуть `FALSE`.  
  
 Рекомендуется переопределить этот метод и вернуть `FALSE` для производного от класса-плавающей панели [CDockablePane класса](../../mfc/reference/cdockablepane-class.md).  
  
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
 Реализация по умолчанию вызывает текущий диспетчер визуального представления для заполнения фона ( [CMFCVisualManager::OnFillBarBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillbarbackground)).  
  
##  <a name="enabledocking"></a>CBasePane::EnableDocking  
 Включает Закрепление панели в основном фрейме.  
  
```  
virtual void EnableDocking(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwAlignment`  
 Задает выравнивание закрепления для включения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для закрепления выравнивание для главного фрейма. Вы можете передать сочетание `CBRS_ALIGN_` флаги (Дополнительные сведения см. в разделе [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).  
  
 `EnableDocking`задает внутренний флаг `CBasePane::m_dwEnabledAlignment` и платформа проверяет этот флаг, при закреплении области.  
  
 Вызов [CBasePane::GetEnabledAlignment](#getenabledalignment) для определения закрепления выравнивания для области.  
  
##  <a name="enablegripper"></a>CBasePane::EnableGripper  
 Включает или отключает захвата. Если включен захвата, пользователь может перетаскивать его, чтобы изменить положение панели.  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы включить захвата; `FALSE` для его отключения.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует этот метод для включения захвата вместо `WS_CAPTION` стиль.  
  
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
 Задает координаты на экране, где отображается плавающая панель.  
  
 [in] `dockMethod`  
 Задает метод dock для float области.  
  
 [in] `bShow`  
 Указывает, будет ли видна панель с плавающей запятой ( `TRUE`) или скрытым ( `FALSE`).  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если оставить плавающим области была успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для float область на экране позиции, указанной параметром `rectFloat`.  
  
##  <a name="get_acchelptopic"></a>CBasePane::get_accHelpTopic  
 Платформа вызывает этот метод, чтобы получить полный путь к `WinHelp` файл, связанный с указанным объектом и идентификатор этого файла в соответствующем разделе.  
  
```  
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,  
    VARIANT varChild,  
    long* pidTopic);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pszHelpFile`  
 Адрес `BSTR` , который получает полный путь к `WinHelp` файл, связанный с указанным объектом, при их наличии.  
  
 [in] `varChild`  
 Указывает, является ли раздел справки для извлечения объекта или одного из дочерних элементов объекта. Этот параметр может быть либо `CHILDID_SELF` (Чтобы получить раздел справки для объекта) или идентификатор дочернего (Чтобы получить раздел справки для одной из ее дочерних элементов объекта).  
  
 [in] `pidTopic`  
 Идентифицирует `Help` раздел файла, связанного с указанным объектом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `CBasePane`Этот метод не реализован. Таким образом `CBasePane::get_accHelpTopic` всегда возвращает `S_FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция является частью поддержки Active Accessibility в MFC. Переопределите эту функцию в производном классе для справочную информацию о объекта.  
  
##  <a name="get_accselection"></a>CBasePane::get_accSelection  
 Платформа вызывает этот метод для извлечения выбранного дочернего элемента этого объекта.  
  
```  
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pvarChildren`  
 Получает сведения, идентифицирующие выделенных дочерних объектов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `CBasePane`Этот метод не реализован. Если значением параметра `pvarChildren` является `NULL`, метод возвращает `E_INVALIDARG`. В противном случае этот метод возвращает `DISP_E_MEMBERNOTFOUND`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция является частью поддержки Active Accessibility в MFC. Переопределите эту функцию в производном классе, при наличии элементов-оконные пользовательского интерфейса, кроме безоконный элементы управления ActiveX.  
  
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
 Побитовое или сочетание флагов AFX_CBRS_.  
  
### <a name="remarks"></a>Примечания  
 Возвращает значение, сочетание следующих значений.  
  
|Стиль|Описание|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Делает плавающей панели управления.|  
|`AFX_CBRS_AUTOHIDE`|Включение автоматического скрытия режиме.|  
|`AFX_CBRS_RESIZE`|Разрешает изменение размера панели управления. Если этот флаг установлен, на панели управления можно поместить закрепляемой панели.|  
|`AFX_CBRS_CLOSE`|Позволяет скрыть панели элементов управления.|  
  
##  <a name="getcurrentalignment"></a>CBasePane::GetCurrentAlignment  
 Возвращает текущее выравнивание панели.  
  
```  
virtual DWORD GetCurrentAlignment() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее выравнивание панели управления. Ниже приведены возможные значения:  
  
|Значение|Выравнивание|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|Выравнивание по левому краю.|  
|`CBRS_ALIGN_RIGHT`|Выравнивание по правому краю.|  
|`CBRS_ALIGN_TOP`|Выравнивание по верхнему краю.|  
|`CBRS_ALIGN_BOTTOM`|Выравнивание нижней.|  
  
##  <a name="getdockingmode"></a>CBasePane::GetDockingMode  
 Возвращает текущий режим закрепления панели.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 При перетаскивании панели DT_STANDARD обозначается перетащите прямоугольник на экране. DT_IMMEDIATE при перетаскивании содержимого панели.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, чтобы определить текущий режим закрепления панели.  
  
 Если `CBasePane::m_dockMode` — не определено (DT_UNDEFINED), то режима закрепления берется из глобальный режим закрепления ( `AFX_GLOBAL_DATA::m_dockModeGlobal`).  
  
 Установив `m_dockMode` или переопределения `GetDockingMode` можно управлять режимом закрепления для каждой области.  
  
##  <a name="getdocksiteframewnd"></a>CBasePane::GetDockSiteFrameWnd  
 Возвращает указатель на [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)объекта место закрепления панели.  
  
```  
virtual CWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на сайте закрепления панели.  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы получить указатель на сайте закрепления панели. Закрепление сайта может быть фрейма главного окна, если закреплены области главного фрейма или окна области, если плавающей панели.  
  
##  <a name="getenabledalignment"></a>CBasePane::GetEnabledAlignment  
 Возвращает CBRS_ALIGN_ стили, которые применяются к области.  
  
```  
virtual DWORD GetEnabledAlignment() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сочетание CBRS_ALIGN_ стили. В следующей таблице показаны возможные стили:  
  
|Flag|Включено выравнивание|  
|----------|-----------------------|  
|`CBRS_ALIGN_LEFT`|По левому краю.|  
|`CBRS_ALIGN_RIGHT`|Правильно.|  
|`CBRS_ALIGN_TOP`|Вверх.|  
|`CBRS_ALIGN_BOTTOM`|По нижнему краю.|  
|`CBRS_ALIGN_ANY`|Сочетание всех флагов.|  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы определить, включена выравнивание для области. Включено выравнивание означает сторон фрейма главного окна, которую можно закрепить области.  
  
 Включение закрепления выравнивание с помощью [CBasePane::EnableDocking](#enabledocking).  
  
##  <a name="getmfcstyle"></a>CBasePane::GetMFCStyle  
 Возвращает область стилей, характерные для MFC.  
  
```  
virtual DWORD GetMFCStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сочетание стилей панели (AFX_CBRS_) для данной библиотеки.  
  
##  <a name="getpaneicon"></a>CBasePane::GetPaneIcon  
 Возвращает дескриптор для значка панели.  
  
```  
virtual HICON GetPaneIcon(BOOL bBigIcon);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bBigIcon`  
 Указывает 32 пикселя по значок размером 32 пикселя, если `TRUE`; указывает 16 пикселей значок 16 пикселей, если `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для значка панели. Если операция завершилась неудачей, возвращает `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает [CWnd::GetIcon](../../mfc/reference/cwnd-class.md#geticon).  
  
##  <a name="getpanerow"></a>CBasePane::GetPaneRow  
 Возвращает указатель на [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)объекта место закрепления панели.  
  
```  
CDockingPanesRow* GetPaneRow();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CDockingPanesRow` Если закрепленной панели или `NULL` , если он является перемещаемой.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для доступа к строке, место закрепления панели. Например, чтобы упорядочить области в конкретной строке, вызвать `GetPaneRow` , а затем вызвать [CDockingPanesRow::ArrangePanes](../../mfc/reference/cdockingpanesrow-class.md#arrangepanes).  
  
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
 Закрепление родительского узла.  
  
##  <a name="getparentminiframe"></a>CBasePane::GetParentMiniFrame  
 Возвращает указатель окна родительской области.  
  
```  
virtual CPaneFrameWnd* GetParentMiniFrame(BOOL bNoAssert=FALSE) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bNoAssert`  
 Если `TRUE`, этот метод не проверяет наличие недопустимых указатели. Если этот метод вызывается, когда приложение завершает работу, присвойте этому параметру значение `TRUE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель области родительского окна, если панель закреплена; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения указатель на родительское окно области. Этот метод выполняет итерацию по всем родительским элементам и проверяет наличие объект, производный от [CPaneFrameWnd класса](../../mfc/reference/cpaneframewnd-class.md).  
  
 Используйте `GetParentMiniFrame` для определения числа с плавающей панели.  
  
##  <a name="getparenttabbedpane"></a>CBasePane::GetParentTabbedPane  
 Возвращает указатель на область с вкладками родительского.  
  
```  
CBaseTabbedPane* GetParentTabbedPane() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на родительский области с вкладками, если он существует; в противном случае `NULL`.  
  
##  <a name="getparenttabwnd"></a>CBasePane::GetParentTabWnd  
 Возвращает указатель, находящийся внутри вкладки родительского окна.  
  
```  
CMFCBaseTabCtrl* GetParentTabWnd(HWND& hWndTab) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `hWndTab`  
 Если возвращаемое значение не `NULL`, этот параметр содержит дескриптор родительского окна с вкладками.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Окна с вкладками допустимый указатель на родительский или `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для получения указателя родительского окна с вкладками. Иногда может быть недостаточно для вызова `GetParent`, так как область может находиться внутри закрепления оболочки ( [класса CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)) или внутри области адаптера ( [CDockablePaneAdapter класса](../../mfc/reference/cdockablepaneadapter-class.md)). С помощью `GetParentTabWnd` можно будет получить допустимый указатель в таких случаях (при условии, что родительского окна с вкладками).  
  
##  <a name="getrecentvisiblestate"></a>CBasePane::GetRecentVisibleState  
 Платформа вызывает этот метод, когда область восстанавливается из архива.  
  
```  
virtual BOOL GetRecentVisibleState() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `BOOL` , указывающий последние видимое состояние. Если `TRUE`, области был видимым при сериализации и должен быть видимым при восстановлении. Если `FALSE`, области был скрыт при сериализации и должны быть скрыты при восстановлении.  
  
##  <a name="hideinprintpreviewmode"></a>CBasePane::HideInPrintPreviewMode  
 Указывает, скрыт ли панели в режиме предварительного просмотра.  
  
```  
virtual BOOL HideInPrintPreviewMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область не отображается в режиме предварительного просмотра; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Базовый панели не отображаются в режиме предварительного просмотра. Таким образом, этот метод всегда возвращает `TRUE`.  
  
##  <a name="insertpane"></a>CBasePane::InsertPane  
 Регистрация указанной области закрепления диспетчером.  
  
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
 `TRUE`Если область поддерживает Active Accessibility; в противном случае — `FALSE`.  
  
##  <a name="isautohidemode"></a>CBasePane::IsAutoHideMode  
 Определяет, является ли область в режиме автоматического скрытия.  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель в режиме автоматического скрытия. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Базовый областей нельзя автоматического скрытия. Этот метод всегда возвращает значение `FALSE`.  
  
##  <a name="isdialogcontrol"></a>CBasePane::IsDialogControl  
 Указывает, является ли панели управления диалогового окна.  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель управления диалогового окна; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа использует этот метод для обеспечения согласованности макет для всех панелей.  
  
##  <a name="isdocked"></a>CBasePane::IsDocked  
 Определяет, закреплен ли области.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если родительской области не мини-кадров или числа с плавающей панели в мини-кадр с другой области; в противном случае — `FALSE`.  
  
##  <a name="isfloating"></a>CBasePane::IsFloating  
 Определяет, ли плавающей панели.  
  
```  
virtual BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель закреплена; в противном случае — `FALSE`.  
  
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
 `TRUE`Если панель в окне фрейма несколькими областями. в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 В окне фрейма несколькими областями может перемещаться только закрепляемых областей. Таким образом `CBasePane::IsInFloatingMultiPaneFrameWnd` всегда возвращает `FALSE`.  
  
##  <a name="ismditabbed"></a>CBasePane::IsMDITabbed  
 Определяет, были ли добавлены области дочернюю MDI как документ с вкладками.  
  
```  
virtual BOOL IsMDITabbed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области были добавлены дочернего окна MDI как документ с вкладками; в противном случае — `FALSE`.  
  
##  <a name="ispanevisible"></a>CBasePane::IsPaneVisible  
 Указывает, является ли `WS_VISIBLE` флаг для области.  
  
```  
BOOL IsPaneVisible() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `WS_VISIBLE` установлено; в противном случае — `FALSE`.  
  
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
 Задает край приближается к точке. Возможные значения: `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP`, и`CBRS_ALIGN_BOTTOM`  
  
 [выходной] `bOuterEdge`  
 `TRUE`Если точка находится рядом с внешней границы сайта закрепления; `FALSE` в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если точка находится рядом с сайта закрепления; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Точка расположено сайта закрепления, когда он находится в пределах чувствительности, установите в диспетчере закрепления. По умолчанию учет — 15 точек.  
  
##  <a name="isresizable"></a>CBasePane::IsResizable  
 Определяет, возможно ли изменение размеров панели.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область может быть изменен пользователем; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Области [CDockablePane класса](../../mfc/reference/cdockablepane-class.md) может быть изменен.  
  
 В строке состояния ( [класса CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)) и закрепление панели ( [CDockSite класса](../../mfc/reference/cdocksite-class.md)) не может быть изменен.  
  
##  <a name="isrestoredfromregistry"></a>CBasePane::IsRestoredFromRegistry  
 Определяет, будет ли восстановлена области из реестра.  
  
```  
virtual BOOL IsRestoredFromRegistry() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если области восстанавливается из реестра; в противном случае — `FALSE`.  
  
##  <a name="istabbed"></a>CBasePane::IsTabbed  
 Определяет, ввела ли области в элементе управления "Вкладка" окна с вкладками.  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панель элементов управления вставляется на вкладке окна с вкладками; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод извлекает указатель на ближайший родительский и определяет, является ли родительский класс среды выполнения [CMFCBaseTabCtrl класса](../../mfc/reference/cmfcbasetabctrl-class.md).  
  
##  <a name="isvisible"></a>CBasePane::IsVisible  
 Определяет, будет ли видна панель.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если область является видимой; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для определения области видимости. Не используйте `::IsWindowVisible`.  
  
 Если область не с вкладками (см. [CBasePane::IsTabbed](#istabbed)), этот метод проверяет `WS_VISIBLE` стиль. Если области вкладок, этот метод проверяет видимость родительского окна с вкладками. Если родительское окно является видимым, функция проверяет видимость вкладки панели с помощью [CMFCBaseTabCtrl::IsTabVisible](../../mfc/reference/cmfcbasetabctrl-class.md#istabvisible).  
  
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
 `TRUE`Если панель состояния был загружен успешно. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод для загрузки состояния панели из реестра. Его можно переопределить в производном классе, чтобы загрузить дополнительные сведения, сохраненные в [CBasePane::SaveState](#savestate).  
  
##  <a name="movewindow"></a>CBasePane::MoveWindow  
 Перемещение области.  
  
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
 Дескриптор структуру положение окна отложенного или `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Если передать `NULL` как `hdwp` параметр, этот метод перемещает окно обычным образом. Если передается дескриптор, этот метод выполняет отложенное перемещения. Дескриптор можно получить, вызвав [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672) или сохранив возвращаемое значение предыдущего вызова этого метода.  
  
##  <a name="onafterchangeparent"></a>CBasePane::OnAfterChangeParent  
 Вызывается платформой после изменения родительской области.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndOldParent`  
 Указатель на предыдущий родительский элемент.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод после родительской панели изменяется, обычно из-за операции закрепления или с плавающей запятой.  
  
 Реализация по умолчанию не выполняет никаких действий.  
  
##  <a name="onbeforechangeparent"></a>CBasePane::OnBeforeChangeParent  
 Вызывается средой перед изменения области родительского окна.  
  
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
 Платформа вызывает этот метод непосредственно перед изменения родительской области, обычно из-за закрепление плавающей операции или автоматического скрытия.  
  
 Реализация по умолчанию не выполняет никаких действий.  
  
##  <a name="ondrawcaption"></a>CBasePane::OnDrawCaption  
 Платформа вызывает этот метод при отрисовке заголовка.  
  
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
 Вызывается инфраструктурой при построении меню, которое содержит список областей.  
  
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
 `OnPaneContextMenu`вызывает закрепления manager, который поддерживает список панелей, входящих в текущем фрейме окна. Этот метод добавляет имена областей в контекстное меню и отображает его. Команды в меню Показать или скрыть отдельные области.  
  
 Переопределите этот метод, чтобы изменить это поведение.  
  
##  <a name="onremovefromminiframe"></a>CBasePane::OnRemoveFromMiniFrame  
 Вызывается платформой, когда область удаляется из родительского окна мини-кадра.  
  
```  
virtual void OnRemoveFromMiniFrame(CPaneFrameWnd* pMiniFrame);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMiniFrame`  
 Указатель, из которой удаляется области окна области.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод при удалении области из области родительского окна (в результате закрепление, например).  
  
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
 Возвращает область, содержащую заданной точки.  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `point`  
 Указывает точку в координатах экрана, для проверки.  
  
 [in] `nSensitivity`  
 Увеличьте область поиска, этот объем. Область будет удовлетворять условиям поиска, если заданная точка находится в области повышения.  
  
 [in] `bExactBar`  
 `TRUE`Чтобы игнорировать `nSensitivity` параметр; в противном случае — `FALSE`.  
  
 [in] `pRTCBarType`  
 Если это не `NULL`, метод выполняет поиск только областей указанного типа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `CBasePane`-Производный объект, содержащий определенный момент или `NULL` Если области не был найден.  
  
##  <a name="recalclayout"></a>CBasePane::RecalcLayout  
 `CBasePane`не используйте этот метод.  
  
```  
virtual void RecalcLayout();
```  
  
##  <a name="removepanefromdockmanager"></a>CBasePane::RemovePaneFromDockManager  
 Отменяет регистрацию область и удаляет его из списка в диспетчере закрепления.  
  
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
 Указатель на область удаляется.  
  
 [in] `bDestroy`  
 Если `TRUE`, уничтожается области удален.  
  
 [in] `bAdjustLayout`  
 Если `TRUE`, настроить макет закрепления немедленно.  
  
 [in] `bAutoHide`  
 Если `TRUE`, макет закрепления относится к списку автоматическое скрытие панелей. Если `FALSE`, макет закрепления связан список регулярных панелей.  
  
 [in] `pBarReplacement`  
 Указатель на область, которая заменит область удален.  
  
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
 Платформа вызывает этот метод при сохранении состояния области реестра. Переопределение `SaveState` в производном классе для хранения дополнительных сведений.  
  
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
 Побитовое или сочетание следующих значений.  
  
|Стиль|Описание|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Делает плавающей панели управления.|  
|`AFX_CBRS_AUTOHIDE`|Включение автоматического скрытия режиме.|  
|`AFX_CBRS_RESIZE`|Разрешает изменение размера панели управления. Если этот флаг установлен, на панели управления можно поместить закрепляемой панели.|  
|`AFX_CBRS_CLOSE`|Позволяет скрыть панели элементов управления.|  
  
##  <a name="setdockingmode"></a>CBasePane::SetDockingMode  
 Задает режим закрепления панели.  
  
```  
void SetDockingMode(AFX_DOCK_TYPE dockModeNew);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dockModeNew`  
 Задает новый режим закрепления панели.  
  
### <a name="remarks"></a>Примечания  
 Платформа поддерживает два режима закрепления: стандартные и интерпретации.  
  
 В стандартном режиме закрепления панели и окна мини-фрейма перемещаются с помощью перетащите прямоугольник. В режиме интерпретации закрепляемых панелей элементов управления и окна мини-фрейма перемещаются немедленно вместе с контекстом.  
  
 Изначально закрепления режим определяется всему миру благодаря [CDockingManager::m_dockModeGlobal](../../mfc/reference/cdockingmanager-class.md#m_dockmodeglobal). Можно задать режим закрепления для каждой отдельно с помощью панели `SetDockingMode` метод.  
  
##  <a name="setpanealignment"></a>CBasePane::SetPaneAlignment  
 Задает выравнивание для области.  
  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwAlignment`  
 Задает новый выравнивание.  
  
### <a name="remarks"></a>Примечания  
 Как правило платформа вызывает этот метод при присоединении область из одной части главного фрейма в другой.  
  
 Ниже приведены возможные значения для `dwAlignment`:  
  
|Значение|Выравнивание|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|Выравнивание по левому краю.|  
|`CBRS_ALIGN_RIGHT`|Выравнивание по правому краю.|  
|`CBRS_ALIGN_TOP`|Выравнивание по верхнему краю.|  
|`CBRS_ALIGN_BOTTOM`|Выравнивание нижней.|  
  
##  <a name="setpanestyle"></a>CBasePane::SetPaneStyle  
 Задает стиль панели.  
  
```  
virtual void SetPaneStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `dwNewStyle`  
 Задает новый стиль для задания.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно присвоить CBRS_ стили, определенные в файле afxres.h. Поскольку стиль панели и выравнивания области хранятся вместе, задайте новый стиль, объединяя ее с текущего выравнивания следующим образом.  
  
 `pPane->SetPaneStyle (pPane->GetCurrentAlignment() | CBRS_TOOLTIPS);`  
  
##  <a name="setwindowpos"></a>CBasePane::SetWindowPos  
 Изменение размера, положения и Z-порядок области.  
  
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
 Идентифицирует `CWnd` объекта, который предшествует это `CWnd` объектов в Z-порядке. Дополнительные сведения см. в разделе [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).  
  
 [in] `x`  
 Задает позицию левого края окна.  
  
 [in] `y`  
 Задает позицию верхнего края окна.  
  
 [in] `cx`  
 Ширина окна.  
  
 [in] `cy`  
 Указывает высоту окна.  
  
 [in] `nFlags`  
 Указывает параметры размера и положения. Дополнительные сведения см. в разделе [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).  
  
 [in] `hdwp`  
 Ссылка на структуру, содержащую сведения о размере и позиции для одного или нескольких окон.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор структуру позиции обновленное окно отложенного или `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Если `pWndInsertAfter` — `NULL`, этот метод вызывает метод [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos). Если `pWndInsertAfter` отличен от `NULL`, этот метод вызывает метод `DeferWindowPos`.  
  
##  <a name="showpane"></a>CBasePane::ShowPane  
 Отображение или скрытие панели.  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bShow`  
 Указывает, следует ли отображать ( `TRUE`) или скрыть ( `FALSE`) области.  
  
 [in] `bDelay`  
 Если `TRUE`, повторное вычисление макета закрепления задерживается.  
  
 [in] `bActivate`  
 Если `TRUE`, активные при отображении области.  
  
### <a name="remarks"></a>Примечания  
 Этот метод показывает или скрывает панель. Используйте этот метод, а не `ShowWindow` , так как этот метод уведомляет соответствующие закрепления диспетчеры об изменениях в области видимости.  
  
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
 Длина, в котором растянуть области.  
  
 [in] `bVert`  
 Если `TRUE`, растянуть области по вертикали. Если `FALSE`, растянуть области по горизонтали.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер области растянутым.  
  
##  <a name="undockpane"></a>CBasePane::UndockPane  
 Удаление области из сайта закрепления, по умолчанию ползунок или окна области, где он в настоящее время закреплен.  
  
```  
virtual void UndockPane(BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `bDelay`  
 Значение TRUE, если макет закрепления не пересчитывается немедленно.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для управления состоянием области или исключить из макета закрепления панели.  
  
 Если вы хотите продолжать использовать эту панель, вызвать [CBasePane::DockPane](#dockpane) или [CBasePane::FloatPane](#floatpane) перед вызовом этого метода.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)

