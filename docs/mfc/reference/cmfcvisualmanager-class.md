---
title: "CMFCVisualManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCVisualManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManager class"
ms.assetid: beed80f7-36a2-4d64-9f09-e807cfefc3fe
caps.latest.revision: 58
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 60
---
# CMFCVisualManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет поддержку для изменения внешнего вида приложения на глобальном уровне.  Класс `CMFCVisualManager` работает вместе с классом, который содержит инструкции отрисовки элемента управления графического интерфейса пользователя приложения, используя согласованный стиль.  Эти другие классы называются диспетчеров визуального представления и они наследуются от `CMFCBaseVisualManager`.  
  
## Синтаксис  
  
```  
class CMFCVisualManager : public CMFCBaseVisualManager  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCVisualManager::CMFCVisualManager`|Конструктор по умолчанию.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCVisualManager::AdjustFrames](../Topic/CMFCVisualManager::AdjustFrames.md)||  
|[CMFCVisualManager::AdjustToolbars](../Topic/CMFCVisualManager::AdjustToolbars.md)||  
|[CMFCVisualManager::AlwaysHighlight3DTabs](../Topic/CMFCVisualManager::AlwaysHighlight3DTabs.md)|Вызываемый средой, чтобы определить, следует ли вкладки всегда быть нарисована трехмерной с помощью цвета выделения.|  
|[CMFCVisualManager::DestroyInstance](../Topic/CMFCVisualManager::DestroyInstance.md)||  
|[CMFCVisualManager::DoDrawHeaderSortArrow](../Topic/CMFCVisualManager::DoDrawHeaderSortArrow.md)||  
|[CMFCVisualManager::DrawComboDropButtonWinXP](../Topic/CMFCVisualManager::DrawComboDropButtonWinXP.md)||  
|[CMFCVisualManager::DrawPushButtonWinXP](../Topic/CMFCVisualManager::DrawPushButtonWinXP.md)||  
|[CMFCVisualManager::DrawTextOnGlass](../Topic/CMFCVisualManager::DrawTextOnGlass.md)||  
|[CMFCVisualManager::GetAutoHideButtonTextColor](../Topic/CMFCVisualManager::GetAutoHideButtonTextColor.md)|Вызываемый платформой для получения цвет текста для автоматического скрытия кнопки.|  
|[CMFCVisualManager::GetButtonExtraBorder](../Topic/CMFCVisualManager::GetButtonExtraBorder.md)|Вызываемый платформой для получения увеличение размера кнопки которого текущий диспетчер визуального представления требуются для рисования кнопки.|  
|[CMFCVisualManager::GetCaptionBarTextColor](../Topic/CMFCVisualManager::GetCaptionBarTextColor.md)|Вызываемый платформой для получения цвет текста заголовка.|  
|[CMFCVisualManager::GetDockingTabsBordersSize](../Topic/CMFCVisualManager::GetDockingTabsBordersSize.md)|Вызываемый платформой для получения размер границы состыкованной нашитой панели.|  
|[CMFCVisualManager::GetHighlightedMenuItemTextColor](../Topic/CMFCVisualManager::GetHighlightedMenuItemTextColor.md)||  
|[CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md)|Возвращает указатель на объект `CMFCVisualManager`.|  
|[CMFCVisualManager::GetMDITabsBordersSize](../Topic/CMFCVisualManager::GetMDITabsBordersSize.md)|Вызываемый платформой для получения размер границы окна MDITabs.|  
|[CMFCVisualManager::GetMenuItemTextColor](../Topic/CMFCVisualManager::GetMenuItemTextColor.md)||  
|[CMFCVisualManager::GetMenuShadowDepth](../Topic/CMFCVisualManager::GetMenuShadowDepth.md)|Возвращает значение, указывающее ширину и высоту тени меню.|  
|[CMFCVisualManager::GetNcBtnSize](../Topic/CMFCVisualManager::GetNcBtnSize.md)|Вызываемый платформой для определения размера кнопок системы, основанных на текущем диспетчере визуального представления.  Кнопки системы кнопки в заголовке главного фрейма, сопоставить командам **Закрыть**, **Свернуть**, **Развернуть** и **Восстановить**.|  
|[CMFCVisualManager::GetPopupMenuBorderSize](../Topic/CMFCVisualManager::GetPopupMenuBorderSize.md)|Вызываемый платформой для получения размер границы для раскрывающегося меню.|  
|[CMFCVisualManager::GetPropertyGridGroupColor](../Topic/CMFCVisualManager::GetPropertyGridGroupColor.md)|Вызываемый платформой для получения цвет фона списка свойств.|  
|[CMFCVisualManager::GetPropertyGridGroupTextColor](../Topic/CMFCVisualManager::GetPropertyGridGroupTextColor.md)|Вызываемый платформой для получения цвет текста списка свойств.|  
|[CMFCVisualManager::GetRibbonHyperlinkTextColor](../Topic/CMFCVisualManager::GetRibbonHyperlinkTextColor.md)||  
|[CMFCVisualManager::GetRibbonPopupBorderSize](../Topic/CMFCVisualManager::GetRibbonPopupBorderSize.md)||  
|[CMFCVisualManager::GetRibbonQuickAccessToolBarTextColor](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarTextColor.md)||  
|[CMFCVisualManager::GetRibbonSliderColors](../Topic/CMFCVisualManager::GetRibbonSliderColors.md)||  
|[CMFCVisualManager::GetShowAllMenuItemsHeight](../Topic/CMFCVisualManager::GetShowAllMenuItemsHeight.md)||  
|[CMFCVisualManager::GetSmartDockingBaseGuideColors](../Topic/CMFCVisualManager::GetSmartDockingBaseGuideColors.md)||  
|[CMFCVisualManager::GetSmartDockingHighlightToneColor](../Topic/CMFCVisualManager::GetSmartDockingHighlightToneColor.md)||  
|[CMFCVisualManager::GetSmartDockingTheme](../Topic/CMFCVisualManager::GetSmartDockingTheme.md)|Возвращает тему, используемую для отображения меток умных закрепления.|  
|[CMFCVisualManager::GetStatusBarPaneTextColor](../Topic/CMFCVisualManager::GetStatusBarPaneTextColor.md)||  
|[CMFCVisualManager::GetTabFrameColors](../Topic/CMFCVisualManager::GetTabFrameColors.md)|Вызываемый платформой, чтобы получить набор цветов для использования, когда он отрисовывает кадр вкладки.|  
|[CMFCVisualManager::GetTabTextColor](../Topic/CMFCVisualManager::GetTabTextColor.md)||  
|[CMFCVisualManager::GetToolbarButtonTextColor](../Topic/CMFCVisualManager::GetToolbarButtonTextColor.md)|Вызываемый платформой, чтобы получить текущий цвет текста на кнопке панели инструментов.  Этот цвет меняется на основе текущего диспетчере визуального представления и состояние кнопки.|  
|[CMFCVisualManager::GetToolbarDisabledTextColor](../Topic/CMFCVisualManager::GetToolbarDisabledTextColor.md)|Вызываемый платформой, чтобы указать цвет текста, отображаемого на отключенных элементов панели инструментов.|  
|[CMFCVisualManager::GetToolbarHighlightColor](../Topic/CMFCVisualManager::GetToolbarHighlightColor.md)||  
|[CMFCVisualManager::GetToolTipInfo](../Topic/CMFCVisualManager::GetToolTipInfo.md)||  
|[CMFCVisualManager::HasOverlappedAutoHideButtons](../Topic/CMFCVisualManager::HasOverlappedAutoHideButtons.md)|Определяет, перекрывается ли автоматического скрытия кнопки.|  
|[CMFCVisualManager::IsDockingTabHasBorder](../Topic/CMFCVisualManager::IsDockingTabHasBorder.md)|Указывает, допускает ли текущий диспетчер визуального представления граница вокруг области закрепления с вкладками.|  
|[CMFCVisualManager::IsEmbossDisabledImage](../Topic/CMFCVisualManager::IsEmbossDisabledImage.md)|Определяет, должны ли быть выбиты отключенные изображений.|  
|[CMFCVisualManager::IsFadeInactiveImage](../Topic/CMFCVisualManager::IsFadeInactiveImage.md)|Вызываемый средой, чтобы определить, отображаются ли неактивные образы на панели инструментов или меню уменьшен яркостьыми.|  
|[CMFCVisualManager::IsMenuFlatLook](../Topic/CMFCVisualManager::IsMenuFlatLook.md)|Определяет, имеют ли кнопки меню плоский внешний вид.|  
|[CMFCVisualManager::IsOfficeXPStyleMenus](../Topic/CMFCVisualManager::IsOfficeXPStyleMenus.md)|Определяет, реализует ли диспетчер визуального представления меню XP\- стиля office.|  
|[CMFCVisualManager::IsOwnerDrawCaption](../Topic/CMFCVisualManager::IsOwnerDrawCaption.md)|Определяет, реализует ли диспетчер визуального представления текущего определяемые пользователем фреймового окна заголовки.|  
|[CMFCVisualManager::IsShadowHighlightedImage](../Topic/CMFCVisualManager::IsShadowHighlightedImage.md)|Указывает, имеет ли выбранный образ тень.|  
|[CMFCVisualManager::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManager::OnDrawAutoHideButtonBorder.md)|Вызываемый платформой, когда он рисует границу для автоматического скрытия кнопки.|  
|[CMFCVisualManager::OnDrawBarGripper](../Topic/CMFCVisualManager::OnDrawBarGripper.md)|Вызываемый платформой, когда он рисует захват области элементов управления.  Пользователь должен щелкнуть захват, чтобы переместить область элементов управления.|  
|[CMFCVisualManager::OnDrawBrowseButton](../Topic/CMFCVisualManager::OnDrawBrowseButton.md)|Вызываемый платформой, когда она рисует кнопку обзора, которая принадлежит к элементу управления "Поле ввода" \([CMFCEditBrowseCtrl Class](../Topic/CMFCEditBrowseCtrl%20Class.md)\).|  
|[CMFCVisualManager::OnDrawButtonBorder](../Topic/CMFCVisualManager::OnDrawButtonBorder.md)|Вызываемый платформой, когда она рисует границу кнопки панели инструментов.|  
|[CMFCVisualManager::OnDrawButtonSeparator](../Topic/CMFCVisualManager::OnDrawButtonSeparator.md)||  
|[CMFCVisualManager::OnDrawCaptionBarBorder](../Topic/CMFCVisualManager::OnDrawCaptionBarBorder.md)|Вызываемый платформой, когда она рисует границу заголовка.|  
|[CMFCVisualManager::OnDrawCaptionBarButtonBorder](../Topic/CMFCVisualManager::OnDrawCaptionBarButtonBorder.md)||  
|[CMFCVisualManager::OnDrawCaptionBarInfoArea](../Topic/CMFCVisualManager::OnDrawCaptionBarInfoArea.md)||  
|[CMFCVisualManager::OnDrawCaptionButton](../Topic/CMFCVisualManager::OnDrawCaptionButton.md)|Вызываемый платформой, когда она рисует кнопку заголовка.|  
|[CMFCVisualManager::OnDrawCheckBox](../Topic/CMFCVisualManager::OnDrawCheckBox.md)||  
|[CMFCVisualManager::OnDrawCheckBoxEx](../Topic/CMFCVisualManager::OnDrawCheckBoxEx.md)||  
|[CMFCVisualManager::OnDrawComboBorder](../Topic/CMFCVisualManager::OnDrawComboBorder.md)|Вызываемый платформой, когда она рисует границу кнопок полей со списком.|  
|[CMFCVisualManager::OnDrawComboDropButton](../Topic/CMFCVisualManager::OnDrawComboDropButton.md)|Вызываемый платформой, когда она рисует кнопку перетаскивания поля со списком.|  
|[CMFCVisualManager::OnDrawControlBorder](../Topic/CMFCVisualManager::OnDrawControlBorder.md)||  
|[CMFCVisualManager::OnDrawDefaultRibbonImage](../Topic/CMFCVisualManager::OnDrawDefaultRibbonImage.md)|Вызываемый платформой, когда он рисуется по умолчанию образ ленты.|  
|[CMFCVisualManager::OnDrawEditBorder](../Topic/CMFCVisualManager::OnDrawEditBorder.md)|Вызываемый платформой, когда он рисует границу вокруг объекта [CMFCToolBarEditBoxButton](../Topic/CMFCToolBarEditBoxButton%20Class.md).|  
|[CMFCVisualManager::OnDrawExpandingBox](../Topic/CMFCVisualManager::OnDrawExpandingBox.md)||  
|[CMFCVisualManager::OnDrawFloatingToolbarBorder](../Topic/CMFCVisualManager::OnDrawFloatingToolbarBorder.md)|Вызываемый платформой, когда он отрисовывает границы перемещаемой панели инструментов.  Перемещаемая панели инструментов панель инструментов, которая отображается в поле область.|  
|[CMFCVisualManager::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManager::OnDrawHeaderCtrlBorder.md)|Вызываемый платформой, когда она рисует границу, которая содержит элемент управления заголовка.|  
|[CMFCVisualManager::OnDrawHeaderCtrlSortArrow](../Topic/CMFCVisualManager::OnDrawHeaderCtrlSortArrow.md)|Вызываемый платформой, когда она рисует стрелку сортировки заголовка элемента управления.|  
|[CMFCVisualManager::OnDrawMenuArrowOnCustomizeList](../Topic/CMFCVisualManager::OnDrawMenuArrowOnCustomizeList.md)||  
|[CMFCVisualManager::OnDrawMenuBorder](../Topic/CMFCVisualManager::OnDrawMenuBorder.md)|Вызываемый платформой, когда она рисует границу меню.|  
|[CMFCVisualManager::OnDrawMenuCheck](../Topic/CMFCVisualManager::OnDrawMenuCheck.md)||  
|[CMFCVisualManager::OnDrawMenuItemButton](../Topic/CMFCVisualManager::OnDrawMenuItemButton.md)||  
|[CMFCVisualManager::OnDrawMenuLabel](../Topic/CMFCVisualManager::OnDrawMenuLabel.md)||  
|[CMFCVisualManager::OnDrawMenuResizeBar](../Topic/CMFCVisualManager::OnDrawMenuResizeBar.md)||  
|[CMFCVisualManager::OnDrawMenuScrollButton](../Topic/CMFCVisualManager::OnDrawMenuScrollButton.md)|Вызываемый платформой, когда она рисует кнопку прокрутки меню.|  
|[CMFCVisualManager::OnDrawMenuShadow](../Topic/CMFCVisualManager::OnDrawMenuShadow.md)||  
|[CMFCVisualManager::OnDrawMenuSystemButton](../Topic/CMFCVisualManager::OnDrawMenuSystemButton.md)|Вызываемый платформой, когда она рисует система меню застегивает **Закрыть**, **Свернуть**, **Развернуть** и **Восстановить**.|  
|[CMFCVisualManager::OnDrawMiniFrameBorder](../Topic/CMFCVisualManager::OnDrawMiniFrameBorder.md)||  
|[CMFCVisualManager::OnDrawOutlookBarSplitter](../Topic/CMFCVisualManager::OnDrawOutlookBarSplitter.md)|Вызываемый платформой, когда он рисуется разделитель для панели outlook.  Разделитель горизонтальную панель, используемую в групповым элементам управления.|  
|[CMFCVisualManager::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManager::OnDrawOutlookPageButtonBorder.md)|Вызываемый платформой, когда он рисует границу кнопки веб\-страницы outlook.  Кнопки веб\-страницы outlook появляются если панель панели outlook содержит несколько кнопок, чем он может отобразить.|  
|[CMFCVisualManager::OnDrawPaneBorder](../Topic/CMFCVisualManager::OnDrawPaneBorder.md)|Вызываемый платформой, когда он рисует границу [CPane Class](../../mfc/reference/cpane-class.md).|  
|[CMFCVisualManager::OnDrawPaneCaption](../Topic/CMFCVisualManager::OnDrawPaneCaption.md)|Вызываемый платформой, когда он отрисовывает заголовок для `CPane`.|  
|[CMFCVisualManager::OnDrawPaneDivider](../Topic/CMFCVisualManager::OnDrawPaneDivider.md)||  
|[CMFCVisualManager::OnDrawPopupWindowBorder](../Topic/CMFCVisualManager::OnDrawPopupWindowBorder.md)||  
|[CMFCVisualManager::OnDrawPopupWindowButtonBorder](../Topic/CMFCVisualManager::OnDrawPopupWindowButtonBorder.md)||  
|[CMFCVisualManager::OnDrawPopupWindowCaption](../Topic/CMFCVisualManager::OnDrawPopupWindowCaption.md)||  
|[CMFCVisualManager::OnDrawRibbonApplicationButton](../Topic/CMFCVisualManager::OnDrawRibbonApplicationButton.md)|Вызываемый платформой, когда она будет **Главная кнопка** на ленте.|  
|[CMFCVisualManager::OnDrawRibbonButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonButtonBorder.md)|Вызываемый платформой, когда она рисует границу кнопки ленты.|  
|[CMFCVisualManager::OnDrawRibbonButtonsGroup](../Topic/CMFCVisualManager::OnDrawRibbonButtonsGroup.md)|Вызываемый платформой, когда она рисует группа в составе кнопки на ленте.|  
|[CMFCVisualManager::OnDrawRibbonCaption](../Topic/CMFCVisualManager::OnDrawRibbonCaption.md)|Вызываемый платформой, когда она рисует заголовок главного фрейма, но только если область ленты интегрирована с кадром.|  
|[CMFCVisualManager::OnDrawRibbonCaptionButton](../Topic/CMFCVisualManager::OnDrawRibbonCaptionButton.md)|Вызываемый платформой, когда она рисует кнопку, расположенную на панели заголовок ленты.|  
|[CMFCVisualManager::OnDrawRibbonCategory](../Topic/CMFCVisualManager::OnDrawRibbonCategory.md)|Вызываемый платформой, когда она рисует категория " на ленте.|  
|[CMFCVisualManager::OnDrawRibbonCategoryCaption](../Topic/CMFCVisualManager::OnDrawRibbonCategoryCaption.md)|Вызываемый платформой, когда она рисует для категории заголовок ленты.|  
|[CMFCVisualManager::OnDrawRibbonCategoryScroll](../Topic/CMFCVisualManager::OnDrawRibbonCategoryScroll.md)||  
|[CMFCVisualManager::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManager::OnDrawRibbonCategoryTab.md)|Вызываемый платформой, когда она рисует вкладку для категории " на ленте.|  
|[CMFCVisualManager::OnDrawRibbonCheckBoxOnList](../Topic/CMFCVisualManager::OnDrawRibbonCheckBoxOnList.md)||  
|[CMFCVisualManager::OnDrawRibbonColorPaletteBox](../Topic/CMFCVisualManager::OnDrawRibbonColorPaletteBox.md)||  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButtonContext](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButtonContext.md)||  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButton.md)|Вызываемый платформой, когда она рисует кнопку области ленты по умолчанию.  Кнопка по умолчанию появляется, когда пользователь сжимает область ленты, чтобы он становится слишком мал для отображения элементов ленты.  Кнопка по умолчанию вместо нарисовано и элементы в виде элементов в меню ленты добавлены списке.|  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButtonIndicator](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButtonIndicator.md)||  
|[CMFCVisualManager::OnDrawRibbonGalleryBorder](../Topic/CMFCVisualManager::OnDrawRibbonGalleryBorder.md)||  
|[CMFCVisualManager::OnDrawRibbonGalleryButton](../Topic/CMFCVisualManager::OnDrawRibbonGalleryButton.md)||  
|[CMFCVisualManager::OnDrawRibbonKeyTip](../Topic/CMFCVisualManager::OnDrawRibbonKeyTip.md)||  
|[CMFCVisualManager::OnDrawRibbonLabel](../Topic/CMFCVisualManager::OnDrawRibbonLabel.md)|Вызываемый платформой, когда он отрисовывает метку ленты.|  
|[CMFCVisualManager::OnDrawRibbonMainPanelButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonMainPanelButtonBorder.md)|Вызываемый платформой, когда он рисует границу кнопки ленты, которая располагается на панели **Основной**.  Панель **Основной** панель, которая появляется, когда пользователь щелкает **Главная кнопка**.|  
|[CMFCVisualManager::OnDrawRibbonMainPanelFrame](../Topic/CMFCVisualManager::OnDrawRibbonMainPanelFrame.md)|Вызываемый платформой, когда она рисует кадр вокруг области **Основной**.|  
|[CMFCVisualManager::OnDrawRibbonMenuCheckFrame](../Topic/CMFCVisualManager::OnDrawRibbonMenuCheckFrame.md)||  
|[CMFCVisualManager::OnDrawRibbonPanel](../Topic/CMFCVisualManager::OnDrawRibbonPanel.md)|Вызываемый платформой, когда он рисуется область ленты.|  
|[CMFCVisualManager::OnDrawRibbonPanelCaption](../Topic/CMFCVisualManager::OnDrawRibbonPanelCaption.md)|Вызываемый платформой, когда она рисует панели заголовок ленты.|  
|[CMFCVisualManager::OnDrawRibbonProgressBar](../Topic/CMFCVisualManager::OnDrawRibbonProgressBar.md)|Вызываемый платформой, когда он рисует объект [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md).|  
|[CMFCVisualManager::OnDrawRibbonQuickAccessToolBarSeparator](../Topic/CMFCVisualManager::OnDrawRibbonQuickAccessToolBarSeparator.md)|Вызываемый платформой, когда он рисуется разделитель в **Панель быстрого доступа** ленты.|  
|[CMFCVisualManager::OnDrawRibbonRecentFilesFrame](../Topic/CMFCVisualManager::OnDrawRibbonRecentFilesFrame.md)|Вызываемый платформой, когда она рисует кадра относительно последнего списка файлов.|  
|[CMFCVisualManager::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManager::OnDrawRibbonSliderChannel.md)|Вызываемый платформой, когда он отрисовывает канал объекта [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md).|  
|[CMFCVisualManager::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManager::OnDrawRibbonSliderThumb.md)|Вызываемый платформой, когда он отрисовывает бегунок объекта `CMFCRibbonSlider`.|  
|[CMFCVisualManager::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManager::OnDrawRibbonSliderZoomButton.md)|Вызываемый платформой, когда он выполняет отрисовку кнопки масштаба объекта `CMFCRibbonSlider`.|  
|[CMFCVisualManager::OnDrawRibbonStatusBarPane](../Topic/CMFCVisualManager::OnDrawRibbonStatusBarPane.md)|Вызываемый платформой, когда он отрисовывает панели строки состояния ленты.|  
|[CMFCVisualManager::OnDrawRibbonTabsFrame](../Topic/CMFCVisualManager::OnDrawRibbonTabsFrame.md)|Вызываемый платформой, когда он отрисовывает кадр вокруг набора вкладок на ленте.|  
|[CMFCVisualManager::OnDrawScrollButtons](../Topic/CMFCVisualManager::OnDrawScrollButtons.md)||  
|[CMFCVisualManager::OnDrawSeparator](../Topic/CMFCVisualManager::OnDrawSeparator.md)|Вызываемый платформой, когда он рисуется разделитель.  Разделитель обычно используется на панели элементов управления для разделения групп в составе значки.|  
|[CMFCVisualManager::OnDrawShowAllMenuItems](../Topic/CMFCVisualManager::OnDrawShowAllMenuItems.md)||  
|[CMFCVisualManager::OnDrawSpinButtons](../Topic/CMFCVisualManager::OnDrawSpinButtons.md)|Вызываемый платформой, когда он выполняет отрисовку кнопки "счетчик".|  
|[CMFCVisualManager::OnDrawSplitterBorder](../Topic/CMFCVisualManager::OnDrawSplitterBorder.md)|Вызываемый платформой, когда он отрисовывает границу окна разбиения.|  
|[CMFCVisualManager::OnDrawSplitterBox](../Topic/CMFCVisualManager::OnDrawSplitterBox.md)|Вызываемый платформой, когда он отрисовывает окно перетаскивания разделитель для разбиения окна.|  
|[CMFCVisualManager::OnDrawStatusBarPaneBorder](../Topic/CMFCVisualManager::OnDrawStatusBarPaneBorder.md)|Вызываемый платформой, когда он отрисовывает границу для панели строки состояния.|  
|[CMFCVisualManager::OnDrawStatusBarProgress](../Topic/CMFCVisualManager::OnDrawStatusBarProgress.md)|Вызываемый платформой, когда он отображает индикатор выполнения строки состояния.|  
|[CMFCVisualManager::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManager::OnDrawStatusBarSizeBox.md)|Вызываемый платформой, когда он отрисовывает окно изменить размер строки состояния.|  
|[CMFCVisualManager::OnDrawTab](../Topic/CMFCVisualManager::OnDrawTab.md)|Вызываемый платформой, когда он рисует объект [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md).|  
|[CMFCVisualManager::OnDrawTabCloseButton](../Topic/CMFCVisualManager::OnDrawTabCloseButton.md)|Вызываемый платформой, когда он рисует кнопку **Закрыть** на активной вкладке.|  
|[CMFCVisualManager::OnDrawTabContent](../Topic/CMFCVisualManager::OnDrawTabContent.md)|Вызываемый платформой, когда он отрисовывает внутренней части вкладки \(образов, текст\).|  
|[CMFCVisualManager::OnDrawTabsButtonBorder](../Topic/CMFCVisualManager::OnDrawTabsButtonBorder.md)|Вызываемый платформой, когда он рисует границу кнопки вкладки.|  
|[CMFCVisualManager::OnDrawTask](../Topic/CMFCVisualManager::OnDrawTask.md)|Вызываемый платформой, когда он отрисовывает задачи на панели задач.|  
|[CMFCVisualManager::OnDrawTasksGroupAreaBorder](../Topic/CMFCVisualManager::OnDrawTasksGroupAreaBorder.md)|Вызываемый платформой, когда он рисует границу вокруг области группы в области задач.|  
|[CMFCVisualManager::OnDrawTasksGroupCaption](../Topic/CMFCVisualManager::OnDrawTasksGroupCaption.md)|Вызываемый платформой, когда он отрисовывает заголовок группы целевого назначения в области задач.|  
|[CMFCVisualManager::OnDrawTasksGroupIcon](../Topic/CMFCVisualManager::OnDrawTasksGroupIcon.md)||  
|[CMFCVisualManager::OnDrawTearOffCaption](../Topic/CMFCVisualManager::OnDrawTearOffCaption.md)|Вызываемый платформой, когда он отрисовывает перемещаемый заголовок для перемещаемой панели.|  
|[CMFCVisualManager::OnDrawToolBoxFrame](../Topic/CMFCVisualManager::OnDrawToolBoxFrame.md)||  
|[CMFCVisualManager::OnEraseMDIClientArea](../Topic/CMFCVisualManager::OnEraseMDIClientArea.md)|Вызываемый платформой, когда он сотрет клиентскую область MDI.|  
|[CMFCVisualManager::OnErasePopupWindowButton](../Topic/CMFCVisualManager::OnErasePopupWindowButton.md)||  
|[CMFCVisualManager::OnEraseTabsArea](../Topic/CMFCVisualManager::OnEraseTabsArea.md)|Вызываемый платформой, когда он сотрет область вкладки в окне вкладки.|  
|[CMFCVisualManager::OnEraseTabsButton](../Topic/CMFCVisualManager::OnEraseTabsButton.md)|Вызываемый платформой, когда он сотрет значок и текст кнопки вкладки.|  
|[CMFCVisualManager::OnEraseTabsFrame](../Topic/CMFCVisualManager::OnEraseTabsFrame.md)|Вызываемый платформой, когда он сотрет кадр вкладки.|  
|[CMFCVisualManager::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManager::OnFillAutoHideButtonBackground.md)|Вызываемый платформой, когда он заполняет фона кнопки автоматического скрытия.|  
|[CMFCVisualManager::OnFillBarBackground](../Topic/CMFCVisualManager::OnFillBarBackground.md)|Вызываемый платформой, когда он заполняет фон панели элементов управления.|  
|[CMFCVisualManager::OnFillButtonInterior](../Topic/CMFCVisualManager::OnFillButtonInterior.md)|Вызываемый платформой, когда он заполняет фон кнопки панели инструментов.|  
|[CMFCVisualManager::OnFillCaptionBarButton](../Topic/CMFCVisualManager::OnFillCaptionBarButton.md)||  
|[CMFCVisualManager::OnFillCommandsListBackground](../Topic/CMFCVisualManager::OnFillCommandsListBackground.md)|Вызываемый платформой, когда он заполняет фон кнопки панели инструментов, принадлежащую список команд, который, в свою очередь, часть диалогового окна настройки.|  
|[CMFCVisualManager::OnFillHeaderCtrlBackground](../Topic/CMFCVisualManager::OnFillHeaderCtrlBackground.md)|Вызываемый платформой, когда он заполняет фона заголовка элемента управления.|  
|[CMFCVisualManager::OnFillMiniFrameCaption](../Topic/CMFCVisualManager::OnFillMiniFrameCaption.md)|Вызываемый платформой, когда он заполняет заголовок мини фреймового окна.|  
|[CMFCVisualManager::OnFillOutlookBarCaption](../Topic/CMFCVisualManager::OnFillOutlookBarCaption.md)|Вызываемый платформой, когда он заполняет фон заголовка панели outlook.|  
|[CMFCVisualManager::OnFillOutlookPageButton](../Topic/CMFCVisualManager::OnFillOutlookPageButton.md)|Вызываемый платформой, когда он заполняет внутреннюю часть кнопок страниц outlook.|  
|[CMFCVisualManager::OnFillPopupWindowBackground](../Topic/CMFCVisualManager::OnFillPopupWindowBackground.md)|Вызываемый платформой, когда он заполняет фона контекстного меню окна.|  
|[CMFCVisualManager::OnFillRibbonButton](../Topic/CMFCVisualManager::OnFillRibbonButton.md)|Вызываемый платформой, когда он заполняет внутреннюю часть кнопки ленты.|  
|[CMFCVisualManager::OnFillRibbonEdit](../Topic/CMFCVisualManager::OnFillRibbonEdit.md)|Вызываемый платформой, когда он заполняет внутреннюю часть элемента управления "Поле ввода" ленты.|  
|[CMFCVisualManager::OnFillRibbonMainPanelButton](../Topic/CMFCVisualManager::OnFillRibbonMainPanelButton.md)|Вызываемый платформой, когда он заполняет внутреннюю часть кнопок ленты, расположенной на панели **Основной**.|  
|[CMFCVisualManager::OnFillRibbonMenuFrame](../Topic/CMFCVisualManager::OnFillRibbonMenuFrame.md)|Вызываемый платформой, когда он заполняет кадр меню главной панели ленты.|  
|[CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](../Topic/CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup.md)||  
|[CMFCVisualManager::OnFillSplitterBackground](../Topic/CMFCVisualManager::OnFillSplitterBackground.md)|Вызываемый платформой, когда он заполняет фон окна разбиения.|  
|[CMFCVisualManager::OnFillTab](../Topic/CMFCVisualManager::OnFillTab.md)|Вызываемый платформой, когда он заполняет фон вкладки.|  
|[CMFCVisualManager::OnFillTasksGroupInterior](../Topic/CMFCVisualManager::OnFillTasksGroupInterior.md)|Вызываемый платформой, когда он заполняет внутреннюю часть объекта [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) на [CMFCTasksPane](../Topic/CMFCTasksPane%20Class.md).|  
|[CMFCVisualManager::OnFillTasksPaneBackground](../Topic/CMFCVisualManager::OnFillTasksPaneBackground.md)|Вызываемый платформой, когда он заполняет фон элемента управления `CMFCTasksPane`.|  
|[CMFCVisualManager::OnHighlightMenuItem](../Topic/CMFCVisualManager::OnHighlightMenuItem.md)|Вызываемый платформой, когда он отображает выбранный пункт меню.|  
|[CMFCVisualManager::OnHighlightRarelyUsedMenuItems](../Topic/CMFCVisualManager::OnHighlightRarelyUsedMenuItems.md)|Вызываемый платформой, когда он отрисовывает выбранный и редко используемый пункт меню.|  
|[CMFCVisualManager::OnNcPaint](../Topic/CMFCVisualManager::OnNcPaint.md)|Вызываемый платформой, когда он рисуется область, отличный от клиента.|  
|[CMFCVisualManager::OnSetWindowRegion](../Topic/CMFCVisualManager::OnSetWindowRegion.md)|Вызываемый платформой, когда он устанавливает среду, которая содержит кадры и всплывающие меню.|  
|[CMFCVisualManager::OnUpdateSystemColors](../Topic/CMFCVisualManager::OnUpdateSystemColors.md)|Вызываемый платформой, когда она изменяет параметр системного цвета.|  
|[CMFCVisualManager::RedrawAll](../Topic/CMFCVisualManager::RedrawAll.md)|Перерисовывает все области элементов управления в приложении.|  
|[CMFCVisualManager::RibbonCategoryColorToRGB](../Topic/CMFCVisualManager::RibbonCategoryColorToRGB.md)||  
|[CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)|Устанавливает по умолчанию диспетчер визуального представления.|  
|[CMFCVisualManager::SetEmbossDisabledImage](../Topic/CMFCVisualManager::SetEmbossDisabledImage.md)|Включение или отключение выбитый режим для отключенных образов панели инструментов.|  
|[CMFCVisualManager::SetFadeInactiveImage](../Topic/CMFCVisualManager::SetFadeInactiveImage.md)|Включение или отключение световой эффект для неактивных изображений в меню или панели инструментов.|  
|[CMFCVisualManager::SetMenuFlatLook](../Topic/CMFCVisualManager::SetMenuFlatLook.md)|Устанавливает пометить указывающее, имеют ли кнопки меню плоский внешний вид приложения.|  
|[CMFCVisualManager::SetMenuShadowDepth](../Topic/CMFCVisualManager::SetMenuShadowDepth.md)|Задает ширину и высоту тени меню.|  
|[CMFCVisualManager::SetShadowHighlightedImage](../Topic/CMFCVisualManager::SetShadowHighlightedImage.md)|Устанавливает пометить которое указывает, следует ли отображать тень для отрисовки выбранные изображений.|  
  
## Заметки  
 Поскольку класс `CMFCVisualManager` контролирует графического интерфейса пользователя приложения, каждое приложение может содержать или один экземпляр `CMFCVisualManager` или один экземпляр класса, производного от `CMFCVisualManager`.  Приложение также может работать без `CMFCVisualManager`.  Используйте статический метод `GetInstance` для получения указателя на текущий `CMFCVisualManager`\- производный объект.  
  
 Для изменения внешнего вида приложения необходимо использовать другие классы, которые предоставляют методы для рисования все визуальные элементы приложения.  Некоторые примеры таких классов [CMFCVisualManagerOfficeXP Class](../../mfc/reference/cmfcvisualmanagerofficexp-class.md), [CMFCVisualManagerOffice2003 Class](../Topic/CMFCVisualManagerOffice2003%20Class.md) и [CMFCVisualManagerOffice2007 Class](../../mfc/reference/cmfcvisualmanageroffice2007-class.md).  Если необходимо изменить внешний вид приложения, передайте один из этих диспетчеров визуального представления в метод `SetDefaultManager`.  Пример, демонстрирующий, как приложение может передразнить представление Microsoft Office 2003 см. в разделе [CMFCVisualManagerOffice2003 Class](../Topic/CMFCVisualManagerOffice2003%20Class.md).  
  
 Все методы рисования виртуальный.  Это позволяет создать пользовательский визуальным стилем для графического интерфейса пользователя приложения.  Если требуется создать собственный визуальный стиль, наследуйте класс от одного из классов диспетчеров визуального представления и переопределите методы рисования, которые нужно изменить.  
  
## Пример  
 В этом образце показано, как создать стандартное и пользовательское `CMFCVisualManager` возражает.  
  
```  
void CMFCSkinsApp::SetSkin (int iIndex)  
{   // destroy the current visual manager  
   if (CMFCVisualManager::GetInstance () != NULL)  
   {  
      delete CMFCVisualManager::GetInstance ();  
   }  
   switch (iIndex)  
  {  
   case 0:  
      CMFCVisualManager::GetInstance (); // create the standard visual manager  
      break;  
   case 1:  
      new CMyVisualManager (); // create the first custom visual manager  
      break;  
   case 2:  
      new CMacStyle ();  // create the second custom visual manager  
      break;  
   }  
  
   // access the manager and set it properly  
   CMFCVisualManager::GetInstance ()->SetLook2000 ();  
   CMFCVisualManager::GetInstance ()->RedrawAll ();  
}  
```  
  
## Пример  
 В следующем примере показано, как извлечь значения по умолчанию объекта `CMFCVisualManager`.  Этот фрагмент кода является частью [Пример области задач](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_TasksPane#1](../../mfc/reference/codesnippet/CPP/cmfcvisualmanager-class_1.h)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
## Требования  
 **заголовок:** afxvisualmanager.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md)   
 [Диспетчер визуализации](../../mfc/visualization-manager.md)