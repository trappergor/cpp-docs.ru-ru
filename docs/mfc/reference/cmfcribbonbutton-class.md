---
title: "CMFCRibbonButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonButton class"
ms.assetid: 732e941c-9504-4b83-a691-d18075965d53
caps.latest.revision: 42
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 44
---
# CMFCRibbonButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCRibbonButton` реализует кнопки, которые можно размещать на элементах ленты, например на панелях, панелях быстрого доступа и во всплывающих меню.  
  
## Синтаксис  
  
```  
class CMFCRibbonButton : public CMFCRibbonBaseElement  
```  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonButton::CMFCRibbonButton](../Topic/CMFCRibbonButton::CMFCRibbonButton.md)|Создает объект "кнопка ленты".|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonButton::AddSubItem](../Topic/CMFCRibbonButton::AddSubItem.md)|Добавляет во всплывающее меню элемент, связанный с кнопкой.|  
|[CMFCRibbonButton::CanBeStretched](../Topic/CMFCRibbonButton::CanBeStretched.md)|\(Переопределяет метод [CMFCRibbonBaseElement::CanBeStretched](../Topic/CMFCRibbonBaseElement::CanBeStretched.md).\)|  
|[CMFCRibbonButton::CleanUpSizes](../Topic/CMFCRibbonButton::CleanUpSizes.md)|\(Переопределяет метод [CMFCRibbonBaseElement::CleanUpSizes](../Topic/CMFCRibbonBaseElement::CleanUpSizes.md).\)|  
|[CMFCRibbonButton::ClosePopupMenu](../Topic/CMFCRibbonButton::ClosePopupMenu.md)|\(Переопределяет метод [CMFCRibbonBaseElement::ClosePopupMenu](../Topic/CMFCRibbonBaseElement::ClosePopupMenu.md).\)|  
|[CMFCRibbonButton::DrawBottomText](../Topic/CMFCRibbonButton::DrawBottomText.md)||  
|[CMFCRibbonButton::DrawImage](../Topic/CMFCRibbonButton::DrawImage.md)|\(Переопределяет метод [CMFCRibbonBaseElement::DrawImage](../Topic/CMFCRibbonBaseElement::DrawImage.md).\)|  
|[CMFCRibbonButton::DrawRibbonText](../Topic/CMFCRibbonButton::DrawRibbonText.md)||  
|[CMFCRibbonButton::FindSubItemIndexByID](../Topic/CMFCRibbonButton::FindSubItemIndexByID.md)|Возвращает индекс элемента всплывающего меню, связанного с указанным идентификатором команды.|  
|[CMFCRibbonButton::GetCommandRect](../Topic/CMFCRibbonButton::GetCommandRect.md)||  
|[CMFCRibbonButton::GetCompactSize](../Topic/CMFCRibbonButton::GetCompactSize.md)|Возвращает компактный размер элемента ленты.  \(Переопределяет метод [CMFCRibbonBaseElement::GetCompactSize](../Topic/CMFCRibbonBaseElement::GetCompactSize.md).\)|  
|[CMFCRibbonButton::GetIcon](../Topic/CMFCRibbonButton::GetIcon.md)||  
|[CMFCRibbonButton::GetImageIndex](../Topic/CMFCRibbonButton::GetImageIndex.md)|Возвращает индекс изображения, связанного с кнопкой.|  
|[CMFCRibbonButton::GetImageSize](../Topic/CMFCRibbonButton::GetImageSize.md)|Возвращает размер изображения элемента ленты.  \(Переопределяет метод [CMFCRibbonBaseElement::GetImageSize](../Topic/CMFCRibbonBaseElement::GetImageSize.md).\)|  
|[CMFCRibbonButton::GetIntermediateSize](../Topic/CMFCRibbonButton::GetIntermediateSize.md)|Возвращает размер элемента ленты в промежуточное состояние.  \(Переопределяет метод [CMFCRibbonBaseElement::GetIntermediateSize](../Topic/CMFCRibbonBaseElement::GetIntermediateSize.md).\)|  
|[CMFCRibbonButton::GetMenu](../Topic/CMFCRibbonButton::GetMenu.md)|Возвращает дескриптор меню Windows, назначенному кнопке ленты.|  
|[CMFCRibbonButton::GetMenuRect](../Topic/CMFCRibbonButton::GetMenuRect.md)||  
|[CMFCRibbonButton::GetRegularSize](../Topic/CMFCRibbonButton::GetRegularSize.md)|Возвращает стандартный размер элемента ленты.  \(Переопределяет метод [CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md).\)|  
|[CMFCRibbonButton::GetSubItems](../Topic/CMFCRibbonButton::GetSubItems.md)||  
|[CMFCRibbonButton::GetTextRowHeight](../Topic/CMFCRibbonButton::GetTextRowHeight.md)||  
|[CMFCRibbonButton::GetToolTipText](../Topic/CMFCRibbonButton::GetToolTipText.md)|Возвращает текст всплывающей подсказки элемента ленты.  \(Переопределяет метод [CMFCRibbonBaseElement::GetToolTipText](../Topic/CMFCRibbonBaseElement::GetToolTipText.md).\)|  
|[CMFCRibbonButton::HasCompactMode](../Topic/CMFCRibbonButton::HasCompactMode.md)|Задает, доступен ли для элемента ленты компактный режим.  \(Переопределяет метод [CMFCRibbonBaseElement::HasCompactMode](../Topic/CMFCRibbonBaseElement::HasCompactMode.md).\)|  
|[CMFCRibbonButton::HasIntermediateMode](../Topic/CMFCRibbonButton::HasIntermediateMode.md)|Задает, доступен ли для элемента ленты промежуточный режим.  \(Переопределяет метод [CMFCRibbonBaseElement::HasIntermediateMode](../Topic/CMFCRibbonBaseElement::HasIntermediateMode.md).\)|  
|[CMFCRibbonButton::HasLargeMode](../Topic/CMFCRibbonButton::HasLargeMode.md)|Определяет, доступен ли для элемента ленты крупный режим.  \(Переопределяет метод [CMFCRibbonBaseElement::HasLargeMode](../Topic/CMFCRibbonBaseElement::HasLargeMode.md).\)|  
|[CMFCRibbonButton::HasMenu](../Topic/CMFCRibbonButton::HasMenu.md)|\(Переопределяет метод [CMFCRibbonBaseElement::HasMenu](../Topic/CMFCRibbonBaseElement::HasMenu.md).\)|  
|[CMFCRibbonButton::IsAlwaysDrawBorder](../Topic/CMFCRibbonButton::IsAlwaysDrawBorder.md)||  
|[CMFCRibbonButton::IsAlwaysLargeImage](../Topic/CMFCRibbonButton::IsAlwaysLargeImage.md)|\(Переопределяет метод [CMFCRibbonBaseElement::IsAlwaysLargeImage](../Topic/CMFCRibbonBaseElement::IsAlwaysLargeImage.md).\)|  
|[CMFCRibbonButton::IsApplicationButton](../Topic/CMFCRibbonButton::IsApplicationButton.md)||  
|[CMFCRibbonButton::IsCommandAreaHighlighted](../Topic/CMFCRibbonButton::IsCommandAreaHighlighted.md)||  
|[CMFCRibbonButton::IsDefaultCommand](../Topic/CMFCRibbonButton::IsDefaultCommand.md)|Определяет, доступна ли для кнопки ленты команда по умолчанию.|  
|[CMFCRibbonButton::IsDefaultPanelButton](../Topic/CMFCRibbonButton::IsDefaultPanelButton.md)||  
|[CMFCRibbonButton::IsDrawTooltipImage](../Topic/CMFCRibbonButton::IsDrawTooltipImage.md)||  
|[CMFCRibbonButton::IsLargeImage](../Topic/CMFCRibbonButton::IsLargeImage.md)||  
|[CMFCRibbonButton::IsMenuAreaHighlighted](../Topic/CMFCRibbonButton::IsMenuAreaHighlighted.md)||  
|[CMFCRibbonButton::IsMenuOnBottom](../Topic/CMFCRibbonButton::IsMenuOnBottom.md)||  
|[CMFCRibbonButton::IsPopupDefaultMenuLook](../Topic/CMFCRibbonButton::IsPopupDefaultMenuLook.md)||  
|[CMFCRibbonButton::IsRightAlignMenu](../Topic/CMFCRibbonButton::IsRightAlignMenu.md)|Определяет, выровнено ли меню по правому краю.|  
|[CMFCRibbonButton::IsSingleLineText](../Topic/CMFCRibbonButton::IsSingleLineText.md)||  
|[CMFCRibbonButton::OnCalcTextSize](../Topic/CMFCRibbonButton::OnCalcTextSize.md)|\(Переопределяет метод [CMFCRibbonBaseElement::OnCalcTextSize](../Topic/CMFCRibbonBaseElement::OnCalcTextSize.md).\)|  
|[CMFCRibbonButton::OnDrawBorder](../Topic/CMFCRibbonButton::OnDrawBorder.md)||  
|[CMFCRibbonButton::OnDraw](../Topic/CMFCRibbonButton::OnDraw.md)|Вызывается платформой для отрисовки элемента ленты.  \(Переопределяет метод [CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md).\)|  
|[CMFCRibbonButton::OnFillBackground](../Topic/CMFCRibbonButton::OnFillBackground.md)||  
|[CMFCRibbonButton::RemoveAllSubItems](../Topic/CMFCRibbonButton::RemoveAllSubItems.md)|Удаляет из всплывающего меню все элементы.|  
|[CMFCRibbonButton::RemoveSubItem](../Topic/CMFCRibbonButton::RemoveSubItem.md)|Удаляет элемент из всплывающего меню.|  
|[CMFCRibbonButton::SetACCData](../Topic/CMFCRibbonButton::SetACCData.md)|\(Переопределяет метод [CMFCRibbonBaseElement::SetACCData](../Topic/CMFCRibbonBaseElement::SetACCData.md).\)|  
|[CMFCRibbonButton::SetAlwaysLargeImage](../Topic/CMFCRibbonButton::SetAlwaysLargeImage.md)|Задает размер свернутой кнопки: крупная или малая.|  
|[CMFCRibbonButton::SetDefaultCommand](../Topic/CMFCRibbonButton::SetDefaultCommand.md)|Делает для кнопки ленты доступной команду по умолчанию.|  
|[CMFCRibbonButton::SetDescription](../Topic/CMFCRibbonButton::SetDescription.md)|Задает описание элемента ленты.  \(Переопределяет метод [CMFCRibbonBaseElement::SetDescription](../Topic/CMFCRibbonBaseElement::SetDescription.md).\)|  
|[CMFCRibbonButton::SetImageIndex](../Topic/CMFCRibbonButton::SetImageIndex.md)|Назначает индекс изображению кнопки.|  
|[CMFCRibbonButton::SetMenu](../Topic/CMFCRibbonButton::SetMenu.md)|Назначает всплывающее меню кнопке ленты.|  
|[CMFCRibbonButton::SetParentCategory](../Topic/CMFCRibbonButton::SetParentCategory.md)|\(Переопределяет метод [CMFCRibbonBaseElement::SetParentCategory](../Topic/CMFCRibbonBaseElement::SetParentCategory.md).\)|  
|[CMFCRibbonButton::SetRightAlignMenu](../Topic/CMFCRibbonButton::SetRightAlignMenu.md)|Располагает всплывающее меню справа от кнопки.|  
|[CMFCRibbonButton::SetText](../Topic/CMFCRibbonButton::SetText.md)|Задает текст элемента ленты.  \(Переопределяет метод [CMFCRibbonBaseElement::SetText](../Topic/CMFCRibbonBaseElement::SetText.md).\)|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonButton::OnClick](../Topic/CMFCRibbonButton::OnClick.md)|Вызывается платформой по нажатию кнопки.|  
  
## Пример  
 В следующем примере демонстрируется использование различных методов класса `CMFCRibbonButton`.  Показывается создание объекта класса `CMFCRibbonButton`, назначение всплывающего меню кнопке ленты, назначение кнопке описания, удаление элемента из всплывающего меню, а также расположение всплывающего меню справа от края кнопки.  
  
 [!code-cpp[NVC_MFC_RibbonApp#7](../../mfc/reference/codesnippet/CPP/cmfcribbonbutton-class_1.cpp)]  
  
## Заметки  
 Чтобы использовать кнопку ленты в приложении, создайте объект "кнопка" и добавьте ее в подходящую [группу](../../mfc/reference/cmfcribbonpanel-class.md) ленты.  
  
```  
CMFCRibbonPanel* pPanel = pCategory->AddPanel (  
    _T("Clipboard"),                       // Panel name  
    m_PanelIcons.ExtractIcon (0));  // Panel icon  
// Create the first button ("Paste"):  
CMFCRibbonButton* pPasteButton =   
    new CMFCRibbonButton (ID_EDIT_PASTE, _T("Paste"), -1, 0);  
// The third parameter (-1) disables small images for button.  
// This button is always displayed with a large image  
// Associate a pop-up menu with the "Paste" button:  
pPasteButton->SetMenu (IDR_CONTEXT_MENU);  
// Add buttons to the panel. These buttons have only small images.  
pPanel->Add (new CMFCRibbonButton (ID_EDIT_CUT, _T("Cut"), 1));  
pPanel->Add (new CMFCRibbonButton (ID_EDIT_COPY, _T("Copy"), 2));  
pPanel->Add (new CMFCRibbonButton (ID_EDIT_PAINT, _T("Paint"), 9));  
```  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
## Требования  
 **Заголовок:** afxribbonbutton.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)