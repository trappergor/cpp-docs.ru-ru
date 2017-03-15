---
title: "CMFCStandardColorsPropertyPage Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCStandardColorsPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCStandardColorsPropertyPage class"
ms.assetid: b84b7cfb-bb24-4c65-804a-5b642cb64400
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMFCStandardColorsPropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет страницу свойств которой пользователи используют для выбора стандартных цветов в диалоговом окне цвет.  
  
## Синтаксис  
  
```  
class CMFCStandardColorsPropertyPage : public CPropertyPage  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCStandardColorsPropertyPage::CMFCStandardColorsPropertyPage`|Конструктор по умолчанию.|  
  
### Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCStandardColorsPropertyPage::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|`CMFCStandardColorsPropertyPage::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
  
### Заметки  
 Класс `CMFCColorDialog` использует этот класс для отображения стандартной страницы свойств цвета.  Дополнительные сведения о `CMFCColorDialog` см. в разделе [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)  
  
## Требования  
 **заголовок:** afxstandardcolorspropertypage.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCCustomColorsPropertyPage Class](../../mfc/reference/cmfccustomcolorspropertypage-class.md)