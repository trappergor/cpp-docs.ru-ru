---
title: "COleIPFrameWnd Class | Microsoft Docs"
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
  - "COleIPFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleIPFrameWnd class"
  - "in-place editing"
  - "OLE, редактирование"
  - "OLE, in-place activation"
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleIPFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Основание системы счисления для окна редактирования локально приложения.  
  
## Синтаксис  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleIPFrameWnd::COleIPFrameWnd](../Topic/COleIPFrameWnd::COleIPFrameWnd.md)|Создает объект `COleIPFrameWnd`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleIPFrameWnd::OnCreateControlBars](../Topic/COleIPFrameWnd::OnCreateControlBars.md)|Вызываемый платформой, когда элемент будет активировать для редактирования на локальном компьютере.|  
|[COleIPFrameWnd::RepositionFrame](../Topic/COleIPFrameWnd::RepositionFrame.md)|Вызываемый платформой для перемещения окна редактирования локально.|  
  
## Заметки  
 Этот класс создает и располагает области элементов управления в окне документа контейнерного приложения.  Он также обрабатывает уведомления, создаваемые внедренным объектом [COleResizeBar](../../mfc/reference/coleresizebar-class.md), когда пользователь изменяет размер окна редактирования локально.  
  
 Дополнительные сведения об использовании `COleIPFrameWnd` см. в статье [активация](../../mfc/activation-cpp.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## Требования  
 **Header:**  afxole.h  
  
## См. также  
 [MFC просматривает HIERSVR](../../top/visual-cpp-samples.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)