---
title: "CMFCVisualManagerWindows Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCVisualManagerWindows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerWindows class"
ms.assetid: 568b6e9e-8e67-4477-9a3d-2981cbd09861
caps.latest.revision: 46
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 48
---
# CMFCVisualManagerWindows Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerWindows` имитирует просмотр Microsoft Windows XP или перспективы, когда пользователь выбирает разделе Microsoft Windows XP или перспективы.  
  
## Синтаксис  
  
```  
class CMFCVisualManagerWindows : public CMFCVisualManagerOfficeXP  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCVisualManagerWindows::CMFCVisualManagerWindows`|Конструктор по умолчанию.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCVisualManagerWindows::AlwaysHighlight3DTabs](../Topic/CMFCVisualManagerWindows::AlwaysHighlight3DTabs.md)|Границы вызывают этот метод позволяет определить, следует ли вкладки всегда быть выделены 3\-d в приложении.  \(Переопределяет [CMFCVisualManager::AlwaysHighlight3DTabs](../Topic/CMFCVisualManager::AlwaysHighlight3DTabs.md)\).|  
|[CMFCVisualManagerWindows::DrawComboBorderWinXP](../Topic/CMFCVisualManagerWindows::DrawComboBorderWinXP.md)|\(Переопределяет `CMFCVisualManager::DrawComboBorderWinXP`\).|  
|[CMFCVisualManagerWindows::DrawComboDropButtonWinXP](../Topic/CMFCVisualManagerWindows::DrawComboDropButtonWinXP.md)|\(Переопределяет [CMFCVisualManager::DrawComboDropButtonWinXP](../Topic/CMFCVisualManager::DrawComboDropButtonWinXP.md)\).|  
|[CMFCVisualManagerWindows::DrawPushButtonWinXP](../Topic/CMFCVisualManagerWindows::DrawPushButtonWinXP.md)|\(Переопределяет [CMFCVisualManager::DrawPushButtonWinXP](../Topic/CMFCVisualManager::DrawPushButtonWinXP.md)\).|  
|[CMFCVisualManagerWindows::GetButtonExtraBorder](../Topic/CMFCVisualManagerWindows::GetButtonExtraBorder.md)|Платформа вызывает этот метод, когда они выпишут кнопки панели инструментов.  \(Переопределяет [CMFCVisualManager::GetButtonExtraBorder](../Topic/CMFCVisualManager::GetButtonExtraBorder.md)\).|  
|[CMFCVisualManagerWindows::GetCaptionButtonExtraBorder](../Topic/CMFCVisualManagerWindows::GetCaptionButtonExtraBorder.md)|\(Переопределяет [CMFCVisualManager::GetCaptionButtonExtraBorder](../Topic/CMFCVisualManager::GetCaptionButtonExtraBorder.md)\).|  
|[CMFCVisualManagerWindows::GetDockingPaneCaptionExtraHeight](../Topic/CMFCVisualManagerWindows::GetDockingPaneCaptionExtraHeight.md)|\(Переопределяет `CMFCVisualManager::GetDockingPaneCaptionExtraHeight`\).|  
|[CMFCVisualManagerWindows::GetHighlightedMenuItemTextColor](../Topic/CMFCVisualManagerWindows::GetHighlightedMenuItemTextColor.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::GetHighlightedMenuItemTextColor`\).|  
|[CMFCVisualManagerWindows::GetPopupMenuGap](../Topic/CMFCVisualManagerWindows::GetPopupMenuGap.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::GetPopupMenuGap`\).|  
|[CMFCVisualManagerWindows::GetToolbarButtonTextColor](../Topic/CMFCVisualManagerWindows::GetToolbarButtonTextColor.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::GetToolbarButtonTextColor`\).|  
|[CMFCVisualManagerWindows::IsDefaultWinXPPopupButton](../Topic/CMFCVisualManagerWindows::IsDefaultWinXPPopupButton.md)|\(Переопределяет [CMFCVisualManager::IsDefaultWinXPPopupButton](../Topic/CMFCVisualManager::IsDefaultWinXPPopupButton.md)\).|  
|[CMFCVisualManagerWindows::IsHighlightWholeMenuItem](../Topic/CMFCVisualManagerWindows::IsHighlightWholeMenuItem.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::IsHighlightWholeMenuItem`\).|  
|[CMFCVisualManagerWindows::IsOfficeStyleMenus](../Topic/CMFCVisualManagerWindows::IsOfficeStyleMenus.md)||  
|[CMFCVisualManagerWindows::IsOfficeXPStyleMenus](../Topic/CMFCVisualManagerWindows::IsOfficeXPStyleMenus.md)|Показывает, реализует ли диспетчер визуального представления меню XP\- стиля office.  \(Переопределяет [CMFCVisualManager::IsOfficeXPStyleMenus](../Topic/CMFCVisualManager::IsOfficeXPStyleMenus.md)\).|  
|[CMFCVisualManagerWindows::IsWindowsThemingSupported](../Topic/CMFCVisualManagerWindows::IsWindowsThemingSupported.md)|\(Переопределяет `CMFCVisualManager::IsWindowsThemingSupported`\).|  
|[CMFCVisualManagerWindows::IsWinXPThemeAvailable](../Topic/CMFCVisualManagerWindows::IsWinXPThemeAvailable.md)|Указывает, доступна ли тема Windows.  Раздел может быть либо разделе Windows XP или темой [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].|  
|[CMFCVisualManagerWindows::OnDrawBarGripper](../Topic/CMFCVisualManagerWindows::OnDrawBarGripper.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawBarGripper`\).|  
|[CMFCVisualManagerWindows::OnDrawBrowseButton](../Topic/CMFCVisualManagerWindows::OnDrawBrowseButton.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawBrowseButton`\).|  
|[CMFCVisualManagerWindows::OnDrawButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawButtonBorder.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawButtonBorder`\).|  
|[CMFCVisualManagerWindows::OnDrawButtonSeparator](../Topic/CMFCVisualManagerWindows::OnDrawButtonSeparator.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawButtonSeparator`\).|  
|[CMFCVisualManagerWindows::OnDrawCaptionButton](../Topic/CMFCVisualManagerWindows::OnDrawCaptionButton.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawCaptionButton`\).|  
|[CMFCVisualManagerWindows::OnDrawCaptionButtonIcon](../Topic/CMFCVisualManagerWindows::OnDrawCaptionButtonIcon.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawCaptionButtonIcon`\).|  
|[CMFCVisualManagerWindows::OnDrawCheckBoxEx](../Topic/CMFCVisualManagerWindows::OnDrawCheckBoxEx.md)|\(Переопределяет [CMFCVisualManager::OnDrawCheckBoxEx](../Topic/CMFCVisualManager::OnDrawCheckBoxEx.md)\).|  
|[CMFCVisualManagerWindows::OnDrawComboBorder](../Topic/CMFCVisualManagerWindows::OnDrawComboBorder.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawComboBorder`\).|  
|[CMFCVisualManagerWindows::OnDrawComboDropButton](../Topic/CMFCVisualManagerWindows::OnDrawComboDropButton.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawComboDropButton`\).|  
|[CMFCVisualManagerWindows::OnDrawControlBorder](../Topic/CMFCVisualManagerWindows::OnDrawControlBorder.md)|\(Переопределяет [CMFCVisualManager::OnDrawControlBorder](../Topic/CMFCVisualManager::OnDrawControlBorder.md)\).|  
|[CMFCVisualManagerWindows::OnDrawEditBorder](../Topic/CMFCVisualManagerWindows::OnDrawEditBorder.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawEditBorder`\).|  
|[CMFCVisualManagerWindows::OnDrawExpandingBox](../Topic/CMFCVisualManagerWindows::OnDrawExpandingBox.md)|\(Переопределяет [CMFCVisualManager::OnDrawExpandingBox](../Topic/CMFCVisualManager::OnDrawExpandingBox.md)\).|  
|[CMFCVisualManagerWindows::OnDrawFloatingToolbarBorder](../Topic/CMFCVisualManagerWindows::OnDrawFloatingToolbarBorder.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawFloatingToolbarBorder`\).|  
|[CMFCVisualManagerWindows::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManagerWindows::OnDrawHeaderCtrlBorder.md)|Платформа вызывает этот метод, когда они выпишут граница вокруг экземпляра [CMFCHeaderCtrl Class](../Topic/CMFCHeaderCtrl%20Class.md).  \(Переопределяет [CMFCVisualManager::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManager::OnDrawHeaderCtrlBorder.md)\).|  
|[CMFCVisualManagerWindows::OnDrawHeaderCtrlSortArrow](../Topic/CMFCVisualManagerWindows::OnDrawHeaderCtrlSortArrow.md)|Платформа вызывает данную функцию, если они выпишут стрелку сортировки управления заголовка.  \(Переопределяет [CMFCVisualManager::OnDrawHeaderCtrlSortArrow](../Topic/CMFCVisualManager::OnDrawHeaderCtrlSortArrow.md)\).|  
|[CMFCVisualManagerWindows::OnDrawMenuBorder](../Topic/CMFCVisualManagerWindows::OnDrawMenuBorder.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawMenuBorder`\).|  
|[CMFCVisualManagerWindows::OnDrawMenuSystemButton](../Topic/CMFCVisualManagerWindows::OnDrawMenuSystemButton.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawMenuSystemButton`\).|  
|[CMFCVisualManagerWindows::OnDrawMiniFrameBorder](../Topic/CMFCVisualManagerWindows::OnDrawMiniFrameBorder.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawMiniFrameBorder`\).|  
|[CMFCVisualManagerWindows::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawOutlookPageButtonBorder.md)|Вызываемый платформой, когда он рисует границу кнопки веб\-страницы outlook.  \(Переопределяет [CMFCVisualManager::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManager::OnDrawOutlookPageButtonBorder.md)\).|  
|[CMFCVisualManagerWindows::OnDrawPaneBorder](../Topic/CMFCVisualManagerWindows::OnDrawPaneBorder.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawPaneBorder`\).|  
|[CMFCVisualManagerWindows::OnDrawPaneCaption](../Topic/CMFCVisualManagerWindows::OnDrawPaneCaption.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawPaneCaption`\).|  
|[CMFCVisualManagerWindows::OnDrawPopupWindowButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawPopupWindowButtonBorder.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawPopupWindowButtonBorder`\).|  
|[CMFCVisualManagerWindows::OnDrawScrollButtons](../Topic/CMFCVisualManagerWindows::OnDrawScrollButtons.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawScrollButtons`\).|  
|[CMFCVisualManagerWindows::OnDrawSeparator](../Topic/CMFCVisualManagerWindows::OnDrawSeparator.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawSeparator`\).|  
|[CMFCVisualManagerWindows::OnDrawSpinButtons](../Topic/CMFCVisualManagerWindows::OnDrawSpinButtons.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawSpinButtons`\).|  
|[CMFCVisualManagerWindows::OnDrawStatusBarPaneBorder](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarPaneBorder.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawStatusBarPaneBorder`\).|  
|[CMFCVisualManagerWindows::OnDrawStatusBarProgress](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarProgress.md)|Платформа вызывает этот метод, когда они выпишут индикатора хода выполнения на объекте [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md).  \(Переопределяет [CMFCVisualManager::OnDrawStatusBarProgress](../Topic/CMFCVisualManager::OnDrawStatusBarProgress.md)\).|  
|[CMFCVisualManagerWindows::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarSizeBox.md)|Платформа вызывает этот метод, когда они выпишут окно размера для [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md).  \(Переопределяет [CMFCVisualManager::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManager::OnDrawStatusBarSizeBox.md)\).|  
|[CMFCVisualManagerWindows::OnDrawTab](../Topic/CMFCVisualManagerWindows::OnDrawTab.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawTab`\).|  
|[CMFCVisualManagerWindows::OnDrawTabCloseButton](../Topic/CMFCVisualManagerWindows::OnDrawTabCloseButton.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawTabCloseButton`\).|  
|[CMFCVisualManagerWindows::OnDrawTabsButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawTabsButtonBorder.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawTabsButtonBorder`\).|  
|[CMFCVisualManagerWindows::OnDrawTask](../Topic/CMFCVisualManagerWindows::OnDrawTask.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawTask`\).|  
|[CMFCVisualManagerWindows::OnDrawTasksGroupAreaBorder](../Topic/CMFCVisualManagerWindows::OnDrawTasksGroupAreaBorder.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawTasksGroupAreaBorder`\).|  
|[CMFCVisualManagerWindows::OnDrawTasksGroupCaption](../Topic/CMFCVisualManagerWindows::OnDrawTasksGroupCaption.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawTasksGroupCaption`\).|  
|[CMFCVisualManagerWindows::OnDrawTearOffCaption](../Topic/CMFCVisualManagerWindows::OnDrawTearOffCaption.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnDrawTearOffCaption`\).|  
|[CMFCVisualManagerWindows::OnErasePopupWindowButton](../Topic/CMFCVisualManagerWindows::OnErasePopupWindowButton.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnErasePopupWindowButton`\).|  
|[CMFCVisualManagerWindows::OnEraseTabsArea](../Topic/CMFCVisualManagerWindows::OnEraseTabsArea.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnEraseTabsArea`\).|  
|[CMFCVisualManagerWindows::OnEraseTabsButton](../Topic/CMFCVisualManagerWindows::OnEraseTabsButton.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnEraseTabsButton`\).|  
|[CMFCVisualManagerWindows::OnEraseTabsFrame](../Topic/CMFCVisualManagerWindows::OnEraseTabsFrame.md)|Платформа вызывает этот метод, когда они стирают кадр в [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md).  \(Переопределяет [CMFCVisualManager::OnEraseTabsFrame](../Topic/CMFCVisualManager::OnEraseTabsFrame.md)\).|  
|[CMFCVisualManagerWindows::OnFillBarBackground](../Topic/CMFCVisualManagerWindows::OnFillBarBackground.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnFillBarBackground`\).|  
|[CMFCVisualManagerWindows::OnFillButtonInterior](../Topic/CMFCVisualManagerWindows::OnFillButtonInterior.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnFillButtonInterior`\).|  
|[CMFCVisualManagerWindows::OnFillCommandsListBackground](../Topic/CMFCVisualManagerWindows::OnFillCommandsListBackground.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnFillCommandsListBackground`\).|  
|[CMFCVisualManagerWindows::OnFillMiniFrameCaption](../Topic/CMFCVisualManagerWindows::OnFillMiniFrameCaption.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`\).|  
|[CMFCVisualManagerWindows::OnFillOutlookPageButton](../Topic/CMFCVisualManagerWindows::OnFillOutlookPageButton.md)|Платформа вызывает этот метод, когда они заполняют внутреннюю часть кнопок страниц outlook.  \(Переопределяет [CMFCVisualManager::OnFillOutlookPageButton](../Topic/CMFCVisualManager::OnFillOutlookPageButton.md)\).|  
|[CMFCVisualManagerWindows::OnFillTasksGroupInterior](../Topic/CMFCVisualManagerWindows::OnFillTasksGroupInterior.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnFillTasksGroupInterior`\).|  
|[CMFCVisualManagerWindows::OnFillTasksPaneBackground](../Topic/CMFCVisualManagerWindows::OnFillTasksPaneBackground.md)|Платформа вызывает этот метод, когда их заполнения фона элемента управления [CMFCTasksPane](../Topic/CMFCTasksPane%20Class.md).  \(Переопределяет [CMFCVisualManager::OnFillTasksPaneBackground](../Topic/CMFCVisualManager::OnFillTasksPaneBackground.md)\).|  
|[CMFCVisualManagerWindows::OnHighlightMenuItem](../Topic/CMFCVisualManagerWindows::OnHighlightMenuItem.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnHighlightMenuItem`\).|  
|[CMFCVisualManagerWindows::OnHighlightRarelyUsedMenuItems](../Topic/CMFCVisualManagerWindows::OnHighlightRarelyUsedMenuItems.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnHighlightRarelyUsedMenuItems`\).|  
|[CMFCVisualManagerWindows::OnUpdateSystemColors](../Topic/CMFCVisualManagerWindows::OnUpdateSystemColors.md)|\(Переопределяет `CMFCVisualManagerOfficeXP::OnUpdateSystemColors`\).|  
|[CMFCVisualManagerWindows::SetOfficeStyleMenus](../Topic/CMFCVisualManagerWindows::SetOfficeStyleMenus.md)||  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCVisualManagerWindows::m\_b3DTabsXPTheme](../Topic/CMFCVisualManagerWindows::m_b3DTabsXPTheme.md)|Определяет, указывает ли раздел Windows XP вкладки 3\-d.|  
  
## Заметки  
 Используйте класс `CMFCVisualManagerWindows` для изменения внешнего вида приложения передразнить текущую тему Windows XP или [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] на компьютере, на котором выполняется приложение.  
  
 Однако раздел Windows может быть недоступны если приложение выполняется в версиях Windows ранее Windows XP или если разделы отключены, поскольку пользователь использует представление **Классический**.  Если тема не доступна, определенное приложение использует по умолчанию диспетчер визуального представления в [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md).  
  
## Пример  
 В следующем примере демонстрируется способ применения `CMFCVisualManagerWindows`.  Этот фрагмент кода является частью [Пример demo рабочего стола предупреждений](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#10](../../mfc/reference/codesnippet/CPP/cmfcvisualmanagerwindows-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
## Требования  
 **заголовок:** afxvisualmanagerwindows.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP Class](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)