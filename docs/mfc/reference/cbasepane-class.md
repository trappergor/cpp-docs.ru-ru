---
title: "CBasePane Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBasePane::get_accKeyboardShortcut"
  - "CBasePane.get_accKeyboardShortcut"
  - "CBasePane.accSelect"
  - "get_accDefaultAction"
  - "accSelect"
  - "CBasePane.accHitTest"
  - "CBasePane.get_accRole"
  - "get_accKeyboardShortcut"
  - "CBasePane::Serialize"
  - "CBasePane"
  - "CBasePane::get_accDefaultAction"
  - "get_accParent"
  - "CBasePane::accSelect"
  - "accLocation"
  - "CBasePane.get_accDescription"
  - "get_accName"
  - "CBasePane::get_accChildCount"
  - "CBasePane.get_accChild"
  - "CBasePane::accHitTest"
  - "accHitTest"
  - "get_accHelp"
  - "CBasePane.get_accChildCount"
  - "CBasePane.get_accValue"
  - "CBasePane::get_accDescription"
  - "get_accChildCount"
  - "CBasePane.accLocation"
  - "CBasePane.PreTranslateMessage"
  - "CBasePane.get_accName"
  - "PreTranslateMessage"
  - "CBasePane::get_accFocus"
  - "get_accDescription"
  - "CBasePane::get_accRole"
  - "get_accValue"
  - "CBasePane.Serialize"
  - "CBasePane::accLocation"
  - "get_accRole"
  - "CBasePane::get_accChild"
  - "get_accFocus"
  - "CBasePane::get_accHelp"
  - "CBasePane.get_accDefaultAction"
  - "CBasePane.get_accHelp"
  - "CBasePane::PreTranslateMessage"
  - "CBasePane::get_accState"
  - "CBasePane.get_accParent"
  - "CBasePane::get_accParent"
  - "get_accChild"
  - "CBasePane::get_accValue"
  - "Serialize"
  - "get_accState"
  - "CBasePane.get_accState"
  - "CBasePane.get_accFocus"
  - "CBasePane::get_accName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accHitTest method"
  - "accLocation method"
  - "accSelect method"
  - "CBasePane class"
  - "get_accChild method"
  - "get_accChildCount method"
  - "get_accDefaultAction method"
  - "get_accDescription method"
  - "get_accFocus method"
  - "get_accHelp method"
  - "get_accKeyboardShortcut method"
  - "get_accName method"
  - "get_accParent method"
  - "get_accRole method"
  - "get_accState method"
  - "get_accValue method"
  - "PreTranslateMessage method"
  - "Serialize method"
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
caps.latest.revision: 43
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBasePane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Базовый класс для всех панелей в MFC.  
  
## Синтаксис  
  
```  
class CBasePane : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CBasePane::CBasePane`|Конструктор по умолчанию.|  
|`CBasePane::~CBasePane`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|`CBasePane::accHitTest`|Вызываемый платформой для получения дочернего элемента или дочерний объект в заданной точке на экране.  \(Переопределяет [CWnd::accHitTest](../Topic/CWnd::accHitTest.md)\).|  
|`CBasePane::accLocation`|Вызываемый платформой для получения текущего расположения экрана для указанного объекта.  \(Переопределяет [CWnd::accLocation](../Topic/CWnd::accLocation.md)\).|  
|[CBasePane::AccNotifyObjectFocusEvent](../Topic/CBasePane::AccNotifyObjectFocusEvent.md)|`CBasePane` не использует этот метод.|  
|`CBasePane::accSelect`|Вызываемый платформой, чтобы изменить выделение или переместить фокус клавиатуры для указанного объекта.  \(Переопределяет [CWnd::accSelect](../Topic/CWnd::accSelect.md)\).|  
|[CBasePane::AddPane](../Topic/CBasePane::AddPane.md)|Добавление панели закрепления на него.|  
|[CBasePane::AdjustDockingLayout](../Topic/CBasePane::AdjustDockingLayout.md)|Перенаправляет вызов к диспетчеру закрепления, чтобы обработать структуру закрепления.|  
|[CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md)|Если панель с границами будет должна обрабатывать свою внутреннюю структуру.|  
|[CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md)|Вычисляет горизонтальный размер области элементов управления.|  
|[CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md)|Определяет, является ли другую панель можно закрепить в области.|  
|[CBasePane::CanAutoHide](../Topic/CBasePane::CanAutoHide.md)|Определяет, поддерживает ли режим автоматического скрытия панели.|  
|[CBasePane::CanBeAttached](../Topic/CBasePane::CanBeAttached.md)|Определяет, является ли панель можно закрепить в другой области.|  
|[CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md)|Определяет, является ли панель можно закрыть.|  
|[CBasePane::CanBeDocked](../Topic/CBasePane::CanBeDocked.md)|Определяет, является ли панель можно закрепить в другой области.|  
|[CBasePane::CanBeResized](../Topic/CBasePane::CanBeResized.md)|Определяет, является ли панель можно изменить размер.|  
|[CBasePane::CanBeTabbedDocument](../Topic/CBasePane::CanBeTabbedDocument.md)|Определяет, является ли панель можно преобразовать в документ нашитому MDI.|  
|[CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md)|Определяет, может ли панель плыть.|  
|[CBasePane::CanFocus](../Topic/CBasePane::CanFocus.md)|Определяет, является ли панель может получать фокус.|  
|[CBasePane::CopyState](../Topic/CBasePane::CopyState.md)|Копирует состояние данной панели.|  
|[CBasePane::CreateDefaultMiniframe](../Topic/CBasePane::CreateDefaultMiniframe.md)|Если область может плыть, то создается окно области.|  
|[CBasePane::CreateEx](../Topic/CBasePane::CreateEx.md)|Создает элемент управления панели.|  
|[CBasePane::DockPane](../Topic/CBasePane::DockPane.md)|Закрепит панель к другой области или фреймовому окно.|  
|[CBasePane::DockPaneUsingRTTI](../Topic/CBasePane::DockPaneUsingRTTI.md)|Закрепит панель с использованием сведений о типах во время выполнения.|  
|[CBasePane::DockToFrameWindow](../Topic/CBasePane::DockToFrameWindow.md)|Закрепит закрепляемая панель к кадру.|  
|[CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md)|Определяет, является ли другую панель можно динамически вставить между этой панелью и родительским кадром.|  
|[CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md)|Включает закрепления панелей в главного фрейма.|  
|[CBasePane::EnableGripper](../Topic/CBasePane::EnableGripper.md)|Включение или отключение отслеживания.  Если отслеживание включено, то пользователь может перетащить его, чтобы переместить область.|  
|`CBasePane::FillWindowRect`|Для внутреннего использования.|  
|[CBasePane::FloatPane](../Topic/CBasePane::FloatPane.md)|Область располагается.|  
|`CBasePane::get_accChild`|Вызываемый платформой для получения адреса интерфейса `IDispatch` для заданного дочернего элемента.  \(Переопределяет [CWnd::get\_accChild](../Topic/CWnd::get_accChild.md)\).|  
|`CBasePane::get_accChildCount`|Вызываемый платформой для получения число дочерних объектов, принадлежащих этому объекту.  \(Переопределяет [CWnd::get\_accChildCount](../Topic/CWnd::get_accChildCount.md)\).|  
|`CBasePane::get_accDefaultAction`|Вызываемый платформой для получения строку, описывающую выполняемое по умолчанию для объекта.  \(Переопределяет [CWnd::get\_accDefaultAction](../Topic/CWnd::get_accDefaultAction.md)\).|  
|`CBasePane::get_accDescription`|Вызываемый платформой для получения строку, описывающую внешний вид указанного объекта.  \(Переопределяет [CWnd::get\_accDescription](../Topic/CWnd::get_accDescription.md)\).|  
|`CBasePane::get_accFocus`|Вызываемый платформой для получения объект, имеющий фокус клавиатуры.  \(Переопределяет [CWnd::get\_accFocus](../Topic/CWnd::get_accFocus.md)\).|  
|`CBasePane::get_accHelp`|Вызываемый платформой для получения строки свойства Справки для объекта.  \(Переопределяет [CWnd::get\_accHelp](../Topic/CWnd::get_accHelp.md)\).|  
|[CBasePane::get\_accHelpTopic](../Topic/CBasePane::get_accHelpTopic.md)|Вызываемый платформой, чтобы получить полный путь WinHelpfile , сопоставлено с указанным объектом и идентификатором соответствующей подразделы, содержащиеся в этом файле.  \(Переопределяет [CWnd::get\_accHelpTopic](../Topic/CWnd::get_accHelpTopic.md)\).|  
|`CBasePane::get_accKeyboardShortcut`|Вызываемый платформой для получения указанное сочетание клавиш для объекта.  \(Переопределяет [CWnd::get\_accKeyboardShortcut](../Topic/CWnd::get_accKeyboardShortcut.md)\).|  
|`CBasePane::get_accName`|Вызываемый платформой для получения имя указанного объекта.  \(Переопределяет [CWnd::get\_accName](../Topic/CWnd::get_accName.md)\).|  
|`CBasePane::get_accParent`|Вызываемый платформой для получения интерфейса `IDispatch` для родительского объекта.  \(Переопределяет [CWnd::get\_accParent](../Topic/CWnd::get_accParent.md)\).|  
|`CBasePane::get_accRole`|Вызываемый платформой для получения сведения, которые описывают роль указанного объекта.  \(Переопределяет [CWnd::get\_accRole](../Topic/CWnd::get_accRole.md)\).|  
|[CBasePane::get\_accSelection](../Topic/CBasePane::get_accSelection.md)|Вызываемый платформой для получения выбранные дочерние элементы данного объект.  \(Переопределяет [CWnd::get\_accSelection](../Topic/CWnd::get_accSelection.md)\).|  
|`CBasePane::get_accState`|Вызываемый платформой для получения текущее состояние заданного объекта.  \(Переопределяет [CWnd::get\_accState](../Topic/CWnd::get_accState.md)\).|  
|`CBasePane::get_accValue`|Вызываемый платформой для получения значения указанного объекта.  \(Переопределяет [CWnd::get\_accValue](../Topic/CWnd::get_accValue.md)\).|  
|[CBasePane::GetCaptionHeight](../Topic/CBasePane::GetCaptionHeight.md)|Возвращает высоту заголовка.|  
|[CBasePane::GetControlBarStyle](../Topic/CBasePane::GetControlBarStyle.md)|Возвращает стиль панели элементов управления.|  
|[CBasePane::GetCurrentAlignment](../Topic/CBasePane::GetCurrentAlignment.md)|Возвращает текущее выравнивание панели.|  
|[CBasePane::GetDockingMode](../Topic/CBasePane::GetDockingMode.md)|Возвращает текущий режим для закрепления панелей.|  
|[CBasePane::GetDockSiteFrameWnd](../Topic/CBasePane::GetDockSiteFrameWnd.md)|Возвращает указатель на окно, сайт закрепления для панели.|  
|[CBasePane::GetEnabledAlignment](../Topic/CBasePane::GetEnabledAlignment.md)|Получает стили CBRS\_ALIGN\_, применены на панели.|  
|[CBasePane::GetMFCStyle](../Topic/CBasePane::GetMFCStyle.md)|Получает стили области, относящиеся к MFC.|  
|[CBasePane::GetPaneIcon](../Topic/CBasePane::GetPaneIcon.md)|Возвращает дескриптор для значка панели.|  
|`CBasePane::GetPaneRect`|Для внутреннего использования.|  
|[CBasePane::GetPaneRow](../Topic/CBasePane::GetPaneRow.md)|Возвращает указатель на объект [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md), где панель закреплена.|  
|[CBasePane::GetPaneStyle](../Topic/CBasePane::GetPaneStyle.md)|Возвращает стиль панели.|  
|[CBasePane::GetParentDockSite](../Topic/CBasePane::GetParentDockSite.md)|Возвращает указатель на родительский сайту закрепления.|  
|[CBasePane::GetParentMiniFrame](../Topic/CBasePane::GetParentMiniFrame.md)|Возвращает указатель на родительский окно области.|  
|[CBasePane::GetParentTabbedPane](../Topic/CBasePane::GetParentTabbedPane.md)|Возвращает указатель на панели нашитой родительским элементом.|  
|[CBasePane::GetParentTabWnd](../Topic/CBasePane::GetParentTabWnd.md)|Возвращает указатель к родительскому окну, внутри вкладки.|  
|[CBasePane::GetRecentVisibleState](../Topic/CBasePane::GetRecentVisibleState.md)|Платформа вызывает этот метод, когда панель восстановлена из архива.|  
|[CBasePane::HideInPrintPreviewMode](../Topic/CBasePane::HideInPrintPreviewMode.md)|Определяет, является ли скрыта панели в режиме предварительного просмотра.|  
|[CBasePane::InsertPane](../Topic/CBasePane::InsertPane.md)|Регистрирует указанной панели с диспетчером закрепления.|  
|[CBasePane::IsAccessibilityCompatible](../Topic/CBasePane::IsAccessibilityCompatible.md)|Определяет, поддерживает ли панель активные специальные возможности.|  
|[CBasePane::IsAutoHideMode](../Topic/CBasePane::IsAutoHideMode.md)|Определяет, является ли область в режиме автоматического скрытия.|  
|[CBasePane::IsDialogControl](../Topic/CBasePane::IsDialogControl.md)|Определяет, является ли панель элемент управления диалогового окна.|  
|[CBasePane::IsDocked](../Topic/CBasePane::IsDocked.md)|Определяет, является ли закреплена панель.|  
|[CBasePane::IsFloating](../Topic/CBasePane::IsFloating.md)|Указывает, располагается ли панель.|  
|[CBasePane::IsHorizontal](../Topic/CBasePane::IsHorizontal.md)|Определяет, является ли панель закреплена по горизонтали.|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](../Topic/CBasePane::IsInFloatingMultiPaneFrameWnd.md)|Определяет, является ли область фреймовом окне multi\- панели.|  
|[CBasePane::IsMDITabbed](../Topic/CBasePane::IsMDITabbed.md)|Определяет, была ли добавлена панель к дочернему окну mdi\-приложения как документ с вкладками.|  
|[CBasePane::IsPaneVisible](../Topic/CBasePane::IsPaneVisible.md)|Указывает, установлен ли пометить `WS_VISIBLE` для панели.|  
|[CBasePane::IsPointNearDockSite](../Topic/CBasePane::IsPointNearDockSite.md)|Определяет, является ли указанная точка находится рядом с сайта закрепления.|  
|[CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md)|Определяет, является ли панель можно изменить размер.|  
|[CBasePane::IsRestoredFromRegistry](../Topic/CBasePane::IsRestoredFromRegistry.md)|Определяет, является ли восстановлена панель из реестра.|  
|[CBasePane::IsTabbed](../Topic/CBasePane::IsTabbed.md)|Определяет, была ли вставлена в набор нашитого панель вкладок окна.|  
|`CBasePane::IsTooltipTopmost`|Для внутреннего использования.|  
|[CBasePane::IsVisible](../Topic/CBasePane::IsVisible.md)|Указывает, видима ли панель.|  
|[CBasePane::LoadState](../Topic/CBasePane::LoadState.md)|Загружает состояние области из реестра.|  
|[CBasePane::MoveWindow](../Topic/CBasePane::MoveWindow.md)|Перемещает панель.|  
|[CBasePane::OnAfterChangeParent](../Topic/CBasePane::OnAfterChangeParent.md)|Вызываемый платформой, если родительский панели будет изменить.|  
|[CBasePane::OnBeforeChangeParent](../Topic/CBasePane::OnBeforeChangeParent.md)|Вызывается инфраструктурой перед панелью изменяет ее родительское окно.|  
|[CBasePane::OnDrawCaption](../Topic/CBasePane::OnDrawCaption.md)|Платформа вызывает этот метод, когда заголовок рисования.|  
|[CBasePane::OnMovePaneDivider](../Topic/CBasePane::OnMovePaneDivider.md)|Этот метод в настоящее время не используется.|  
|[CBasePane::OnPaneContextMenu](../Topic/CBasePane::OnPaneContextMenu.md)|Вызываемый платформой, когда он создает меню, содержащее список панелей.|  
|[CBasePane::OnRemoveFromMiniFrame](../Topic/CBasePane::OnRemoveFromMiniFrame.md)|Если панель с границами будет удалена от родительского мини фреймового окна.|  
|[CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md)|`CBasePane` не использует этот метод.|  
|`CBasePane::OnUpdateCmdUI`|Для внутреннего использования.|  
|[CBasePane::PaneFromPoint](../Topic/CBasePane::PaneFromPoint.md)|Возвращает панель, которая содержит заданную точку.|  
|`CBasePane::PreTranslateMessage`|Используемый классом [CWinApp](../../mfc/reference/cwinapp-class.md) для трансляции сообщения окна, прежде чем они будут передается функции [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows.  \(Переопределяет [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md)\).|  
|[CBasePane::RecalcLayout](../Topic/CBasePane::RecalcLayout.md)|`CBasePane` не использует этот метод.|  
|[CBasePane::RemovePaneFromDockManager](../Topic/CBasePane::RemovePaneFromDockManager.md)|Отменяет регистрацию панель и удаляет его из списка в диспетчере закрепления.|  
|[CBasePane::SaveState](../Topic/CBasePane::SaveState.md)|Сохраняет состояние области в реестр.|  
|[CBasePane::SelectDefaultFont](../Topic/CBasePane::SelectDefaultFont.md)|Выбирает шрифт по умолчанию для данного контекста устройства.|  
|`CBasePane::Serialize`|Считывает или записывает данный объект или архива.  \(Переопределяет [CObject::Serialize](../Topic/CObject::Serialize.md)\).|  
|[CBasePane::SetControlBarStyle](../Topic/CBasePane::SetControlBarStyle.md)|Задает стиль панели элементов управления.|  
|[CBasePane::SetDockingMode](../Topic/CBasePane::SetDockingMode.md)|Устанавливает режим для закрепления панелей.|  
|`CBasePane::SetMDITabbed`|Для внутреннего использования.|  
|[CBasePane::SetPaneAlignment](../Topic/CBasePane::SetPaneAlignment.md)|Задает выравнивание панели.|  
|`CBasePane::SetPaneRect`|Для внутреннего использования.|  
|[CBasePane::SetPaneStyle](../Topic/CBasePane::SetPaneStyle.md)|Задает стиль панели.|  
|`CBasePane::SetRestoredFromRegistry`|Для внутреннего использования.|  
|[CBasePane::SetWindowPos](../Topic/CBasePane::SetWindowPos.md)|Изменяет размер, положения и z\-порядка панелей.|  
|[CBasePane::ShowPane](../Topic/CBasePane::ShowPane.md)|Показать или скрывает панель.|  
|[CBasePane::StretchPane](../Topic/CBasePane::StretchPane.md)|Панель растянет вертикально или горизонтально.|  
|[CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md)|Удаляет панели закрепления из сайта по умолчанию ползунка или окна области, где его в настоящий момент закрепить.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CBasePane::DoPaint](../Topic/CBasePane::DoPaint.md)|Заполняет фон панели.|  
  
## Заметки  
 Если необходимо создать, то класс панели, который поддерживает расширенную закрепления отличается доступным в MFC, должен наследовать его от `CBasePane` или из [CPane Class](../../mfc/reference/cpane-class.md).  
  
## Советы по настройке  
 Следующие советы настройки относятся к [CBasePane Class](../../mfc/reference/cbasepane-class.md) и всем классам, которые наследуются от него.  
  
-   При создании панель, можно применить несколько новых стилей:  
  
    -   `AFX_CBRS_FLOAT` открывает панель плыть.  
  
    -   `AFX_CBRS_AUTOHIDE` включает режим автоматического скрытия.  
  
    -   `AFX_CBRS_CLOSE` содержит панель, которую необходимо закрыть \(скрытый\).  
  
     Эти флаги, которые можно объединить с битовой операции логического сложения.  
  
     Логические `CBasePane` реализует следующие виртуальные методы, чтобы отразить эти флаги: [CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md), [CBasePane::CanAutoHide](../Topic/CBasePane::CanAutoHide.md), [CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md).  Можно переопределять в производных классах, чтобы настраивать их функциональности.  
  
-   Можно настраивать функциональности закрепления путем переопределения [CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md).  Убедитесь в `FALSE` панели возврата из этого метода для предотвращения другую панель из закрепления на него.  
  
-   Если нужно создать статическая панель, которая не могут плыть и любую другую панель, которая предотвращает из закрепления перед ним \(похожий на панели outlook в примере OutlookDemo\), создайте его в качестве подписчиков, отличных от [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md) перемещаемый и переопределите для возврата `FALSE`.  Реализация по умолчанию возвращает `FALSE` если панель создана без стиля `AFX_CBRS_FLOAT`.  
  
-   Создайте все области с идентификаторами, отличное от \-1.  
  
-   Чтобы определить видимость области, используйте [CBasePane::IsVisible](../Topic/CBasePane::IsVisible.md).  Она правильно обрабатывает состояние видимости в режимах нашитых и автоматическом скрытии.  
  
-   Если нужно создать панель не плавающей запятой с возможностью изменения размера, создайте ее без стиля `AFX_CBRS_FLOAT` и вызовите [CFrameWnd::DockControlBar](../Topic/CFrameWnd::DockControlBar.md).  
  
-   Чтобы исключить панель из структуры закрепления или удалить панель инструментов из своей панели закрепления, вызовите [CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md).  Этот метод не следует вызывать для панелей в режиме автоматического скрытия или для панелей, которые находятся на вкладках нашитых windows.  
  
-   Если необходимо плыть или отстыковать панель, которая находится в режиме автоматического скрытия, необходимо вызвать [CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md) с `FALSE` в качестве первого аргумента, прежде чем вызывать метод [CBasePane::FloatPane](../Topic/CBasePane::FloatPane.md) или [CBasePane::UndockPane](../Topic/CBasePane::UndockPane.md).  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CBasePane`.  Примере показано, как получить панель от класса `CFrameWndEx` и, как задать режим, выравнивание панели закрепления и стиль панели.  Код из [Пример запуска площадки слова](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#2](../../mfc/reference/codesnippet/CPP/cbasepane-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
## Требования  
 **заголовок:** afxbasepane.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)