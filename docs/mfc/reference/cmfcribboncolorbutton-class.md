---
title: "Класс CMFCRibbonColorButton | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonColorButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "класс CMFCRibbonColorButton"
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 38
---
# Класс CMFCRibbonColorButton
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCRibbonColorButton` реализует кнопку цвета, которую можно добавить на панель ленты. Кнопка цвета ленты отображает раскрывающееся меню, содержащее одну или несколько палитр.  
  
## Синтаксис  
  
```  
class CMFCRibbonColorButton : public CMFCRibbonGallery  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonColorButton::CMFCRibbonColorButton](../Topic/CMFCRibbonColorButton::CMFCRibbonColorButton.md)||  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonColorButton::AddColorsGroup](../Topic/CMFCRibbonColorButton::AddColorsGroup.md)|Добавляет группу цветов в стандартную область цветов.|  
|[CMFCRibbonColorButton::EnableAutomaticButton](../Topic/CMFCRibbonColorButton::EnableAutomaticButton.md)|Указывает, нажата ли кнопка **Автоматически**.|  
|[CMFCRibbonColorButton::EnableOtherButton](../Topic/CMFCRibbonColorButton::EnableOtherButton.md)|Активирует кнопку **Другие**.|  
|[CMFCRibbonColorButton::GetAutomaticColor](../Topic/CMFCRibbonColorButton::GetAutomaticColor.md)||  
|[CMFCRibbonColorButton::GetColor](../Topic/CMFCRibbonColorButton::GetColor.md)|Возвращает выбранный в данный момент цвет.|  
|[CMFCRibbonColorButton::GetColorBoxSize](../Topic/CMFCRibbonColorButton::GetColorBoxSize.md)|Возвращает размер цветовых элементов, отображаемых на цветовой панели.|  
|[CMFCRibbonColorButton::GetColumns](../Topic/CMFCRibbonColorButton::GetColumns.md)||  
|[CMFCRibbonColorButton::GetHighlightedColor](../Topic/CMFCRibbonColorButton::GetHighlightedColor.md)|Возвращает цвет элемента, выбранного в данный момент во всплывающей цветовой палитре.|  
|[CMFCRibbonColorButton::RemoveAllColorGroups](../Topic/CMFCRibbonColorButton::RemoveAllColorGroups.md)|Удаляет все группы цветов из стандартной области цветов.|  
|[CMFCRibbonColorButton::SetColor](../Topic/CMFCRibbonColorButton::SetColor.md)|Выбирает цвет в стандартной области цветов.|  
|[CMFCRibbonColorButton::SetColorBoxSize](../Topic/CMFCRibbonColorButton::SetColorBoxSize.md)|Задает размер всех цветовых элементов, отображаемых на цветовой панели.|  
|[CMFCRibbonColorButton::SetColorName](../Topic/CMFCRibbonColorButton::SetColorName.md)||  
|[CMFCRibbonColorButton::SetColumns](../Topic/CMFCRibbonColorButton::SetColumns.md)||  
|[CMFCRibbonColorButton::SetDocumentColors](../Topic/CMFCRibbonColorButton::SetDocumentColors.md)|Задает список значений RGB, которые должны отображаться в области цветов документа.|  
|[CMFCRibbonColorButton::SetPalette](../Topic/CMFCRibbonColorButton::SetPalette.md)||  
|[CMFCRibbonColorButton::UpdateColor](../Topic/CMFCRibbonColorButton::UpdateColor.md)||  
  
## Заметки  
 Когда пользователь нажимает кнопку цвета на ленте, отображается цветовая панель. По умолчанию эта панель содержит палитру выбора цвета, называемую стандартной областью цветов. Помимо этого, цветовая панель может содержать кнопку **Автоматически**, которая позволяет пользователю выбрать цвет по умолчанию, и кнопку **Другие**, которая позволяет открыть всплывающую цветовую палитру с дополнительными цветами.  
  
## Пример  
 В приведенном ниже примере демонстрируется использование различных методов класса `CMFCRibbonColorButton`. В нем показано, как создать объект `CMFCRibbonColorButton`, задать большое изображение, активировать кнопку **Автоматически**, активировать кнопку **Другие**, задать число столбцов, задать размер всех цветовых элементов, отображаемых на цветовой панели, добавить группу цветов в стандартную область цветов и указать список значений RGB, которые должны отображаться в области цветов документа. Этот фрагмент кода входит в состав [примера Draw Client](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/CPP/cmfcribboncolorbutton-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)  
  
## Требования  
 **Заголовок:** afxribboncolorbutton.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCRibbonGallery Class](../../mfc/reference/cmfcribbongallery-class.md)