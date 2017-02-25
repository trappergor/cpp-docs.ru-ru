---
title: "CTabView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTabView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabView class"
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 34
---
# CTabView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CTabView` упрощает применение класса набора вкладок \([CMFCTabCtrl](../../mfc/reference/ctabview-class.md)\) в приложениях, использующих MFC и архитектуру документ обнаружения.  
  
## Синтаксис  
  
```  
class CTabbedView : public CView  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTabView::AddView](../Topic/CTabView::AddView.md)|Добавляет новое представление в набор вкладок.|  
|[CTabView::FindTab](../Topic/CTabView::FindTab.md)|Возвращает индекс указанного представления в наборе вкладок.|  
|[CTabView::GetActiveView](../Topic/CTabView::GetActiveView.md)|Возвращает указатель текущего активного представления|  
|[CTabView::GetTabControl](../Topic/CTabView::GetTabControl.md)|Возвращает ссылку на набор вкладок, связанный с представлением.|  
|[CTabView::RemoveView](../Topic/CTabView::RemoveView.md)|Удаляет представление из набора вкладок.|  
|[CTabView::SetActiveView](../Topic/CTabView::SetActiveView.md)|Делает активными представления.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTabView::IsScrollBar](../Topic/CTabView::IsScrollBar.md)|Вызываемый платформой создать представление табуляции для определения, имеет ли представление вкладок общедоступную горизонтальную полосу прокрутки.|  
|[CTabView::OnActivateView](../Topic/CTabView::OnActivateView.md)|Вызываемый платформой, если представление вкладок будет сделать активным или в неактивное состояние.|  
  
## Заметки  
 Этот класс позволяет легко поместить представление с вкладками в приложение " документ\-представление ".  `CTabView``CView`\- производный класс, который содержит внедренный объект `CMFCTabCtrl`.  `CTabView` обрабатывает все сообщения, которые требуются для поддержки объект `CMFCTabCtrl`.  Просто создайте класс, наследуемый от `CTabView` и заткните его в приложение, затем добавьте `CView`\- производные классы с помощью метода `AddView`.  Набор вкладок отобразит эти представления в виде вкладок.  
  
 Например, можно создать документ, могут представляться различными способами: например, электронная таблица, диаграмма редактируемые форма и т д  Можно создать отдельные представления при рисовании данные при необходимости вставить их в соответствующие `CTabView`\- производный объект и их нашитым без дополнительного программирования.  
  
 [В примере TabbedView: Приложение MFC для демонстрации вид с вкладками](../../top/visual-cpp-samples.md) иллюстрирует потребление `CTabView`.  
  
## Пример  
 В следующем примере показано, как `CTabView` используется в примере TabbedView.  
  
 [!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/CPP/ctabview-class_1.h)]  
  
## Требования  
 **заголовок:** afxTabView.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CTabView Class](../../mfc/reference/ctabview-class.md)   
 [CView Class](../Topic/CView%20Class.md)