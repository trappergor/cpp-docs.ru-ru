---
title: "CListView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CListView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListView class"
  - "представления, and common controls"
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CListView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Упрощает использование элемента управления "Список" и [CListCtrl](../Topic/CListCtrl%20Class.md), класса, который инкапсулирует функциональные возможности элемента управления "Список" с архитектурой документ\- вид MFC.  
  
## Синтаксис  
  
```  
class CListView : public CCtrlView  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CListView::CListView](../Topic/CListView::CListView.md)|Создает объект `CListView`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CListView::GetListCtrl](../Topic/CListView::GetListCtrl.md)|Возвращает элемент управления "Список", связанного с представлением.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CListView::RemoveImageList](../Topic/CListView::RemoveImageList.md)|Удаляет указанный список образа из списка.|  
  
## Заметки  
 Дополнительные сведения об этой архитектуры см. в обзоре класса [CView](../Topic/CView%20Class.md) и крест\- ссылок процитированных существует.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CListView`  
  
## Требования  
 **Header:**  afxcview.h  
  
## См. также  
 [В образце ROWLIST MFC](../../top/visual-cpp-samples.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)