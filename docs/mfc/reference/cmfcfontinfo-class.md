---
title: "CMFCFontInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCFontInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCFontInfo class"
  - "CMFCFontInfo::CMFCFontInfo constructor"
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCFontInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCFontInfo` описывает имя и другие атрибуты шрифта.  
  
## Синтаксис  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCFontInfo`|Создает объект `CMFCFontInfo`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCFontInfo::GetFullName](../Topic/CMFCFontInfo::GetFullName.md)|Возвращает сцепленные имена шрифтов и его кодировки \(сценария\).|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCFontInfo::m\_nCharSet](../Topic/CMFCFontInfo::m_nCharSet.md)|Значение, которое определяет кодировку \(скрипт\), связанное с шрифтом.|  
|[CMFCFontInfo::m\_nPitchAndFamily](../Topic/CMFCFontInfo::m_nPitchAndFamily.md)|Значение, указывающее шаг шрифта и семейство шрифтов.|  
|[CMFCFontInfo::m\_nType](../Topic/CMFCFontInfo::m_nType.md)|Значение, определяющее тип шрифта.|  
|[CMFCFontInfo::m\_strName](../Topic/CMFCFontInfo::m_strName.md)|Имя шрифта; например, **arial**.|  
|[CMFCFontInfo::m\_strScript](../Topic/CMFCFontInfo::m_strScript.md)|Имя кодировки \(скрипта\), связанного с шрифтом.|  
  
## Заметки  
 Можно вложить объект `CMFCFontInfo` к элементу класса [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  Вызовите метод [CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md) для получения указателя на объект `CMFCFontInfo`.  
  
## Пример  
 В следующем примере показано, как использовать различные члены класса `CMFCFontInfo`.  Примере показано, как получить объект `CMFCFontInfo` из `CMFCRibbonFontComboBox` и как получить доступ к его локальные переменные.  Данный пример является частью [Пример demo MSOffice 2007](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_MSOffice2007Demo#6](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#6)]  
  
## Требования  
 **заголовок:** afxtoolbarfontcombobox.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCToolBarFontSizeComboBox Class](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)