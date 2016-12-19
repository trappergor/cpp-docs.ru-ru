---
title: "CMFCImageEditorPaletteBar Class | Microsoft Docs"
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
  - "CMFCImageEditorPaletteBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCImageEditorPaletteBar class"
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCImageEditorPaletteBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональность панели диалогового окна палитра цветов редактора изображений.  
  
## Синтаксис  
  
```  
class CMFCImageEditorPaletteBar : public CMFCToolBar  
```  
  
## Члены  
  
### Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCImageEditorPaletteBar::GetRowHeight](../Topic/CMFCImageEditorPaletteBar::GetRowHeight.md)|Возвращает высоту кнопок панели инструментов.  \(Переопределяет [CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md)\).|  
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](../Topic/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable.md)|Определяет, является ли панель инструментов может отображаться кнопки, удлиняли границы.  \(Переопределяет [CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md)\).|  
  
### Заметки  
 Данный класс не предназначен для непосредственного использования в коде.  
  
 Инфраструктура использует этот класс для отображения панели палитра цветов в диалоговом окне редактор изображений.  Дополнительные сведения о диалоговом окне редактор изображений см. в разделе [CMFCImageEditorDialog Class](../Topic/CMFCImageEditorDialog%20Class.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)  
  
## Требования  
 **заголовок:** afximageeditordialog.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCImageEditorDialog Class](../Topic/CMFCImageEditorDialog%20Class.md)