---
title: "CMFCToolTipInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolTipInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolTipInfo class"
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CMFCToolTipInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Хранит сведения о внешнем виде подсказок.  
  
## Синтаксис  
  
```  
class CMFCToolTipInfo  
```  
  
## Участники  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolTipInfo::operator\=](../Topic/CMFCToolTipInfo::operator=.md)||  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolTipInfo::m\_bBalloonTooltip](../Topic/CMFCToolTipInfo::m_bBalloonTooltip.md)|Логическая переменная, указывающая, имеет ли всплывающая подсказка вид выноски.|  
|[CMFCToolTipInfo::m\_bBoldLabel](../Topic/CMFCToolTipInfo::m_bBoldLabel.md)|Логическая переменная, указывающая, выделяются ли заголовки всплывающих подсказок жирным шрифтом.|  
|[CMFCToolTipInfo::m\_bDrawDescription](../Topic/CMFCToolTipInfo::m_bDrawDescription.md)|Логическая переменная, указывающая, содержит ли всплывающая подсказка описание.|  
|[CMFCToolTipInfo::m\_bDrawIcon](../Topic/CMFCToolTipInfo::m_bDrawIcon.md)|Логическая переменная, указывающая, содержит ли всплывающая подсказка значок.|  
|[CMFCToolTipInfo::m\_bDrawSeparator](../Topic/CMFCToolTipInfo::m_bDrawSeparator.md)|Логическая переменная, указывающая, имеется ли разделитель между заголовком всплывающей подсказки и описанием.|  
|[CMFCToolTipInfo::m\_bRoundedCorners](../Topic/CMFCToolTipInfo::m_bRoundedCorners.md)|Логическая переменная, указывающая, закруглены ли углы всплывающей подсказки.|  
|[CMFCToolTipInfo::m\_bVislManagerTheme](../Topic/CMFCToolTipInfo::m_bVislManagerTheme.md)|Логическая переменная, указывающая, должен ли вид всплывающей подсказки контролироваться диспетчером визуального представления \(см. раздел [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)\).|  
|[CMFCToolTipInfo::m\_clrBorder](../Topic/CMFCToolTipInfo::m_clrBorder.md)|Цвет границы всплывающей подсказки.|  
|[CMFCToolTipInfo::m\_clrFill](../Topic/CMFCToolTipInfo::m_clrFill.md)|Цвет фона всплывающей подсказки.|  
|[CMFCToolTipInfo::m\_clrFillGradient](../Topic/CMFCToolTipInfo::m_clrFillGradient.md)|Цвет градиентной заливки всплывающей подсказки.|  
|[CMFCToolTipInfo::m\_clrText](../Topic/CMFCToolTipInfo::m_clrText.md)|Цвет текста всплывающей подсказки.|  
|[CMFCToolTipInfo::m\_nGradientAngle](../Topic/CMFCToolTipInfo::m_nGradientAngle.md)|Угол градиентной заливки всплывающей подсказки.|  
|[CMFCToolTipInfo::m\_nMaxDescrWidth](../Topic/CMFCToolTipInfo::m_nMaxDescrWidth.md)|Максимальная возможная ширина описания во всплывающей подсказке \(в пикселях\).|  
  
## Заметки  
 Чтобы реализовать в своем приложении настроенные всплывающие подсказки, используйте совместно классы [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo` и [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md).  Пример использования этих классов см. в разделе [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md).  
  
## Пример  
 В следующем примере демонстрируется задание значений разных переменных\-членов класса `CMFCToolTipInfo`.  
  
 [!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/CPP/cmfctooltipinfo-class_1.cpp)]  
  
## Иерархия наследования  
 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)  
  
## Требования  
 **Заголовок:** afxtooltipctrl.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md)