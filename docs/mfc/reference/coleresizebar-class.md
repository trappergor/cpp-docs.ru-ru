---
title: "COleResizeBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleResizeBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleResizeBar class"
  - "control bars, изменение размеров"
  - "in-place items"
  - "in-place items, изменение размеров"
  - "OLE items, изменение размеров"
  - "resizing in-place OLE items"
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleResizeBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Тип области элементов управления, которая поддерживает изменение размеров элементов OLE в\- размещения.  
  
## Синтаксис  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleResizeBar::COleResizeBar](../Topic/COleResizeBar::COleResizeBar.md)|Создает объект `COleResizeBar`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleResizeBar::Create](../Topic/COleResizeBar::Create.md)|Создает и инициализирует дочернее окно Windows и связывает его с объектом `COleResizeBar`.|  
  
## Заметки  
 Объекты `COleResizeBar` отображаются как [CRectTracker](../../mfc/reference/crecttracker-class.md) с насиженной границей и внешними маркерами размера.  
  
 Объекты `COleResizeBar` обычно внедренные элементы объектов фреймового окна, производных от класса [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md).  
  
 Дополнительные сведения см. в статье [активация](../../mfc/activation-cpp.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## Требования  
 **Header:**  afxole.h  
  
## См. также  
 [MFC просматривает SUPERPAD](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleServerDoc Class](../Topic/COleServerDoc%20Class.md)