---
title: "CMFCVisualManagerWindows7 Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxvisualmanagerwindows7/CMFCVisualManagerWindows7"
  - "CMFCVisualManagerWindows7"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerWindows7 class"
ms.assetid: e8d87df1-0c09-4b58-8ade-4e911f796e42
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMFCVisualManagerWindows7 Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerWindows7` дает приложению внешнего вида приложения [!INCLUDE[win7](../../build/includes/win7_md.md)].  
  
## Синтаксис  
  
```  
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCVisualManagerWindows7::CMFCVisualManagerWindows7](../Topic/CMFCVisualManagerWindows7::CMFCVisualManagerWindows7.md)|Конструктор по умолчанию.|  
|[CMFCVisualManagerWindows7::~CMFCVisualManagerWindows7](../Topic/CMFCVisualManagerWindows7::~CMFCVisualManagerWindows7.md)|По умолчанию деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCVisualManagerWindows7::CleanStyle`|Очищает текущий стиль оформления и сбросить по умолчанию визуальный стиль.|  
|`CMFCVisualManagerWindows7::CleanUp`|Удаляет все объекты в пользовательском интерфейсе и сбросить меню.|  
|`CMFCVisualManagerWindows7::DrawNcBtn`|Рисует кнопку в области клиента, не являющегося во фрейме.  Инфраструктура использует этот метод для рисования развернут и свернут, закрыть кнопки восстановления в правом верхнем углу границы окна.  Этот метод не вызывается, когда программа использует тему, Aero.|  
|`CMFCVisualManagerWindows7::DrawNcText`|Рисует текст в области клиента, не являющегося во фрейме.  Инфраструктура использует этот метод для рисования заголовок приложения в заголовке окна в верхней части фреймовое окно.|  
|`CMFCVisualManagerWindows7::DrawSeparator`|Рисует разделитель в [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md).|  
|`CMFCVisualManagerWindows7::GetRibbonBar`|Извлекает [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md), связанное с пользовательским интерфейсом.|  
|[CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor](../Topic/CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor.md)|Возвращает цвет фона поля ввода ленты.|  
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|Переопределяет метод [CMFCVisualManager::GetRibbonPopupBorderSize](../Topic/CMFCVisualManager::GetRibbonPopupBorderSize.md).|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|Переопределяет метод [CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset.md).|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|Переопределяет метод [CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin.md).|  
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|Переопределяет метод [CMFCVisualManagerWindows::IsHighlightWholeMenuItem](../Topic/CMFCVisualManagerWindows::IsHighlightWholeMenuItem.md).|  
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|Переопределяет метод [CMFCVisualManager::IsOwnerDrawMenuCheck](../Topic/CMFCVisualManager::IsOwnerDrawMenuCheck.md).|  
|`CMFCVisualManagerWindows7::IsRibbonPresent`|Определяет, присутствует ли `CMFCRibbonBar` и является видимым.|  
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|Переопределяет метод [CMFCVisualManagerWindows::OnDrawButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawButtonBorder.md).|  
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|Переопределяет метод [CMFCVisualManagerWindows::OnDrawCheckBoxEx](../Topic/CMFCVisualManagerWindows::OnDrawCheckBoxEx.md).|  
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|Переопределяет метод [CMFCVisualManagerWindows::OnDrawComboDropButton](../Topic/CMFCVisualManagerWindows::OnDrawComboDropButton.md).|  
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|Переопределяет метод [CMFCVisualManager::OnDrawDefaultRibbonImage](../Topic/CMFCVisualManager::OnDrawDefaultRibbonImage.md).|  
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|Переопределяет метод [CMFCVisualManagerWindows::OnDrawMenuBorder](../Topic/CMFCVisualManagerWindows::OnDrawMenuBorder.md).|  
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|Переопределяет метод [CMFCVisualManager::OnDrawMenuCheck](../Topic/CMFCVisualManager::OnDrawMenuCheck.md).|  
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|Переопределяет метод [CMFCVisualManager::OnDrawMenuLabel](../Topic/CMFCVisualManager::OnDrawMenuLabel.md).|  
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|Переопределяет метод `CMFCVisualManager::OnDrawRadioButton`.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonApplicationButton](../Topic/CMFCVisualManager::OnDrawRibbonApplicationButton.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonButtonBorder.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonCaption](../Topic/CMFCVisualManager::OnDrawRibbonCaption.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonCaptionButton](../Topic/CMFCVisualManager::OnDrawRibbonCaptionButton.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonCategory](../Topic/CMFCVisualManager::OnDrawRibbonCategory.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManager::OnDrawRibbonCategoryTab.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButton.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonGalleryButton](../Topic/CMFCVisualManager::OnDrawRibbonGalleryButton.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|Переопределяет метод `CMFCVisualManager::OnDrawRibbonLaunchButton`.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonMenuCheckFrame](../Topic/CMFCVisualManager::OnDrawRibbonMenuCheckFrame.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonPanel](../Topic/CMFCVisualManager::OnDrawRibbonPanel.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonPanelCaption](../Topic/CMFCVisualManager::OnDrawRibbonPanelCaption.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonProgressBar](../Topic/CMFCVisualManager::OnDrawRibbonProgressBar.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonRecentFilesFrame](../Topic/CMFCVisualManager::OnDrawRibbonRecentFilesFrame.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManager::OnDrawRibbonSliderChannel.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManager::OnDrawRibbonSliderThumb.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManager::OnDrawRibbonSliderZoomButton.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonStatusBarPane](../Topic/CMFCVisualManager::OnDrawRibbonStatusBarPane.md).|  
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|Переопределяет метод [CMFCVisualManager::OnDrawRibbonTabsFrame](../Topic/CMFCVisualManager::OnDrawRibbonTabsFrame.md).|  
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|Переопределяет метод [CMFCVisualManagerWindows::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarSizeBox.md).|  
|`CMFCVisualManagerWindows7::OnFillBarBackground`|Переопределяет метод [CMFCVisualManagerWindows::OnFillBarBackground](../Topic/CMFCVisualManagerWindows::OnFillBarBackground.md).|  
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|Переопределяет метод [CMFCVisualManagerWindows::OnFillButtonInterior](../Topic/CMFCVisualManagerWindows::OnFillButtonInterior.md).|  
|[CMFCVisualManagerWindows7::OnFillMenuImageRect](../Topic/CMFCVisualManagerWindows7::OnFillMenuImageRect.md)|Платформа вызывает этот метод, когда они заполняют область вокруг образов пункта меню.|  
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|Переопределяет метод [CMFCVisualManager::OnFillRibbonButton](../Topic/CMFCVisualManager::OnFillRibbonButton.md).|  
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|Переопределяет метод [CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](../Topic/CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup.md).|  
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|Переопределяет метод [CMFCVisualManagerWindows::OnHighlightMenuItem](../Topic/CMFCVisualManagerWindows::OnHighlightMenuItem.md).|  
|`CMFCVisualManagerWindows7::OnNcActivate`|Переопределяет метод [CMFCVisualManager::OnNcActivate](../Topic/CMFCVisualManager::OnNcActivate.md).|  
|`CMFCVisualManagerWindows7::OnNcPaint`|Переопределяет метод [CMFCVisualManager::OnNcPaint](../Topic/CMFCVisualManager::OnNcPaint.md).|  
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|Переопределяет метод [CMFCVisualManagerWindows::OnUpdateSystemColors](../Topic/CMFCVisualManagerWindows::OnUpdateSystemColors.md).|  
|`CMFCVisualManagerWindows7::SetResourceHandle`|Задает дескриптор ресурса \(uri\), который описывает атрибуты диспетчеров визуального представления.|  
|`CMFCVisualManagerWindows7::SetStyle`|Задает цветовую схему графического интерфейса пользователя `CMFCVisualManagerWindows7`.|  
  
## Заметки  
 Используйте класс `CMFCVisualManagerWindows7` для изменения внешнего вида приложения передразнить по умолчанию приложение [!INCLUDE[win7](../../build/includes/win7_md.md)].  Этот класс не может быть допустимым, если приложение запускается в версиях Windows ранее [!INCLUDE[win7](../../build/includes/win7_md.md)].  В этом сценарии указанного приложения по умолчанию использует диспетчер визуального представления в [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md).  
  
 CMFCVisualManagerWindows7 наследует несколько методов из [CMFCVisualManagerWindows Class](../../mfc/reference/cmfcvisualmanagerwindows-class.md), так и от класса `CMFCVisualManager`.  Методы, перечисленные в предыдущем разделе новые методы в класс `CMFCVisualManagerWindows7`.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
 `CMFCVisualManagerWindows7`  
  
## Требования  
 **заголовок:**  afxvisualmanagerwindows7.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerWindows Class](../../mfc/reference/cmfcvisualmanagerwindows-class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)