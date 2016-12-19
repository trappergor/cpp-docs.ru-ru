---
title: "CTreeView Class | Microsoft Docs"
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
  - "CTreeView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeView class"
  - "CTreeView class, стандартные элементы управления"
  - "directory lists"
  - "file lists [C++]"
  - "tree view controls"
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTreeView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Упрощает применение управления дерева и [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), класса, который инкапсулирует функциональные возможности дерево\- элемента управления с архитектурой документ\- вид MFC.  
  
## Синтаксис  
  
```  
class CTreeView : public CCtrlView  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTreeView::CTreeView](../Topic/CTreeView::CTreeView.md)|Создает объект `CTreeView`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTreeView::GetTreeCtrl](../Topic/CTreeView::GetTreeCtrl.md)|Возвращает элемент управления дерева, связанный с представлением.|  
  
## Заметки  
 Дополнительные сведения об этой архитектуры см. в обзоре класса [CView](../Topic/CView%20Class.md) и крест\- ссылок процитированных существует.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CTreeView`  
  
## Требования  
 **Header:**  afxcview.h  
  
## См. также  
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CView Class](../Topic/CView%20Class.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [CTreeCtrl Class](../../mfc/reference/ctreectrl-class.md)