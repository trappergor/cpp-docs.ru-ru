---
title: "CMFCCustomColorsPropertyPage Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCCustomColorsPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCustomColorsPropertyPage class"
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMFCCustomColorsPropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет страницу свойств, которая может выбрать цвет в диалоговом окне цвет.  
  
## Синтаксис  
  
```  
class CMFCCustomColorsPropertyPage : public CPropertyPage  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|Конструктор по умолчанию.|  
  
### Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCCustomColorsPropertyPage::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|`CMFCCustomColorsPropertyPage::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CMFCCustomColorsPropertyPage::Setup](../Topic/CMFCCustomColorsPropertyPage::Setup.md)|Устанавливает компоненты цвета страницы свойств.|  
  
### Заметки  
 Класс `CMFCColorDialog` использует этот класс для отображения страницы свойств пользовательского цвета.  Дополнительные сведения о `CMFCColorDialog` см. в разделе [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md).  
  
## Пример  
 В следующем примере показано, как создать объект `CMFCCustomColorsPropertyPage` и установить компоненты цвета страницы свойств.  
  
 [!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/CPP/cmfccustomcolorspropertypage-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)  
  
## Требования  
 **заголовок:** afxcustomcolorspropertypage.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCStandardColorsPropertyPage Class](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)