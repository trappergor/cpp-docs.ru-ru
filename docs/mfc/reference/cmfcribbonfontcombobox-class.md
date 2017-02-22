---
title: "CMFCRibbonFontComboBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonFontComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonFontComboBox class"
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMFCRibbonFontComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует поле со списком, содержащее список шрифтов.  Необходимо задать поле со списком на панели ленты.  
  
## Синтаксис  
  
```  
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox  
```  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|Деструктор.|  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](../Topic/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox.md)|Создает и инициализирует объект `CMFCRibbonFontComboBox`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonFontComboBox::BuildFonts](../Topic/CMFCRibbonFontComboBox::BuildFonts.md)|Заполняет поле со списком шрифтов на ленте на основе таких заданных параметров, как тип и семейство шрифтов, а также кодировка и шаг.|  
|`CMFCRibbonFontComboBox::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCRibbonFontComboBox::GetCharSet](../Topic/CMFCRibbonFontComboBox::GetCharSet.md)|Возвращает указанный набор символов.|  
|[CMFCRibbonFontComboBox::GetFontDesc](../Topic/CMFCRibbonFontComboBox::GetFontDesc.md)||  
|[CMFCRibbonFontComboBox::GetFontType](../Topic/CMFCRibbonFontComboBox::GetFontType.md)|Возвращает типы шрифтов, отображаемые в поле со списком.  Допустимые значения: DEVICE\_FONTTYPE, RASTER\_FONTTYPE и TRUETYPE\_FONTTYPE, а также любые их битовые комбинации.|  
|[CMFCRibbonFontComboBox::GetPitchAndFamily](../Topic/CMFCRibbonFontComboBox::GetPitchAndFamily.md)|Возвращает шаг и семейство шрифтов, отображаемых в поле со списком.|  
|`CMFCRibbonFontComboBox::GetThisClass`|Используется платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), связанный с этим типом класса.|  
|[CMFCRibbonFontComboBox::RebuildFonts](../Topic/CMFCRibbonFontComboBox::RebuildFonts.md)|Заполняет поле со списком шрифтов на ленте на основе таких ранее заданных параметров, как тип и семейство шрифтов, а также кодировка и шаг.|  
|[CMFCRibbonFontComboBox::SetFont](../Topic/CMFCRibbonFontComboBox::SetFont.md)|Выбирает указанный шрифт в поле со списком.|  
  
## Заметки  
 После создания объекта `CMFCRibbonFontComboBox` добавьте его на панель ленты, вызвав метод [CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
 [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)  
  
## Требования  
 **Заголовок:** afxRibbonComboBox.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCRibbonComboBox Class](../../mfc/reference/cmfcribboncombobox-class.md)