---
title: "CMFCToolBarInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarInfo class"
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Содержит идентификаторы ресурсов изображений панели инструментов в различных состояниях.  `CMFCToolBarInfo` вспомогательный класс, который используется в качестве параметра метода [CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md).  
  
## Синтаксис  
  
```  
class CMFCToolBarInfo  
```  
  
## Члены  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolBarInfo::m\_uiColdResID](../Topic/CMFCToolBarInfo::m_uiColdResID.md)|Идентификатор ресурса растрового изображения панели инструментов, содержащее обычные \(холодные\) образы панели инструментов.|  
|[CMFCToolBarInfo::m\_uiDisabledResID](../Topic/CMFCToolBarInfo::m_uiDisabledResID.md)|Идентификатор ресурса растрового изображения панели инструментов, содержащего отключенные образы панели инструментов.|  
|[CMFCToolBarInfo::m\_uiHotResID](../Topic/CMFCToolBarInfo::m_uiHotResID.md)|Идентификатор ресурса растрового изображения панели инструментов, содержащий выбранные \(горячие\) образы панели инструментов.|  
|[CMFCToolBarInfo::m\_uiLargeColdResID](../Topic/CMFCToolBarInfo::m_uiLargeColdResID.md)|Идентификатор ресурса растрового изображения панели инструментов, которое содержит большие обычные образы панели инструментов.|  
|[CMFCToolBarInfo::m\_uiLargeDisabledResID](../Topic/CMFCToolBarInfo::m_uiLargeDisabledResID.md)|Идентификатор ресурса растрового изображения панели инструментов, которое содержит большие, отключенные образы панели инструментов.|  
|[CMFCToolBarInfo::m\_uiLargeHotResID](../Topic/CMFCToolBarInfo::m_uiLargeHotResID.md)|Идентификатор ресурса растрового изображения панели инструментов, которое содержит большие, выбранные образы панели инструментов.|  
|[CMFCToolBarInfo::m\_uiMenuDisabledResID](../Topic/CMFCToolBarInfo::m_uiMenuDisabledResID.md)|Идентификатор ресурса растрового изображения панели инструментов, содержащего отключенные образы меню.|  
|[CMFCToolBarInfo::m\_uiMenuResID](../Topic/CMFCToolBarInfo::m_uiMenuResID.md)|Идентификатор ресурса растрового изображения панели инструментов, содержащее образы меню.|  
  
## Заметки  
 Полное растровое изображение панели инструментов состоит из небольших изображений кнопок панели инструментов \(\) фиксированного размера.  Каждый идентификатор ресурса \(uri\), который хранится в объекте `CMFCToolBarInfo` растровое изображение, содержащее полный набор изображений панели инструментов в одном государстве \(например, изображений выбранные, запрещенные большие или меню\).  
  
## Иерархия наследования  
 [CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)  
  
## Требования  
 **заголовок:** afxtoolbar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md)