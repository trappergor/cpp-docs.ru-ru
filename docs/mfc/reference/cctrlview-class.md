---
title: "CCtrlView Class | Microsoft Docs"
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
  - "CCtrlView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCtrlView class"
  - "элементы управления [MFC], common"
  - "представления, and common controls"
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCtrlView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Адаптирует архитектуру документ\- вид к распространенным элементам управления, поддерживаемых версиях Windows NT 98 и Windows 3,51 и более поздних версий.  
  
## Синтаксис  
  
```  
class CCtrlView : public CView  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CCtrlView::CCtrlView](../Topic/CCtrlView::CCtrlView.md)|Создает объект `CCtrlView`.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CCtrlView::OnDraw](../Topic/CCtrlView::OnDraw.md)|Вызываемый платформой для рисования, используя задаваемые значения контекста устройства.|  
|[CCtrlView::PreCreateWindow](../Topic/CCtrlView::PreCreateWindow.md)|Перед созданием окна Windows с именем вложенного к данному объекту `CCtrlView`.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CCtrlView::m\_dwDefaultStyle](../Topic/CCtrlView::m_dwDefaultStyle.md)|Содержит стиль по умолчанию для класса представления.|  
|[CCtrlView::m\_strClass](../Topic/CCtrlView::m_strClass.md)|Содержит имя класса Windows для класса представления.|  
  
## Заметки  
 Класс `CCtrlView` и его производные, [CEditView](../Topic/CEditView%20Class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md) и [CRichEditView](../../mfc/reference/cricheditview-class.md), приспосабливают архитектуру документ\- вид с новым поддерживаемым распространенным элементам управления версиями 3.51, Windows 95 и Windows NT \/98 и более поздних версий.  Дополнительные сведения об архитектуре документ\- вид см. в разделе [Архитектура документов и представлений](../Topic/Document-View%20Architecture.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 `CCtrlView`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [CView Class](../Topic/CView%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CTreeView Class](../../mfc/reference/ctreeview-class.md)   
 [CListView Class](../../mfc/reference/clistview-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)