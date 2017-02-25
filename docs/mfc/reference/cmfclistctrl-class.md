---
title: "CMFCListCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCListCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCListCtrl class"
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CMFCListCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCListCtrl` расширяет возможности класса [CListCtrl Class](../Topic/CListCtrl%20Class.md), поддерживать расширенную функциональность элемента управления заголовка [CMFCHeaderCtrl Class](../Topic/CMFCHeaderCtrl%20Class.md).  
  
## Синтаксис  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](../Topic/CMFCListCtrl::EnableMarkSortedColumn.md)|Включает возможность пометить сортируемый столбец с другим цветом фона.|  
|[CMFCListCtrl::EnableMultipleSort](../Topic/CMFCListCtrl::EnableMultipleSort.md)|Включает несколько режим сортировки.|  
|[CMFCListCtrl::GetHeaderCtrl](../Topic/CMFCListCtrl::GetHeaderCtrl.md)|Возвращает ссылку на подчеркнутому элемент управления заголовка.|  
|[CMFCListCtrl::IsMultipleSort](../Topic/CMFCListCtrl::IsMultipleSort.md)|Проверяет, является ли элемент управления "Список" в нескольких режиме сортировки.|  
|[CMFCListCtrl::OnCompareItems](../Topic/CMFCListCtrl::OnCompareItems.md)|Вызываемый платформой, когда он должен сравнить 2 элемента управления "Список".|  
|[CMFCListCtrl::OnGetCellBkColor](../Topic/CMFCListCtrl::OnGetCellBkColor.md)|Вызываемый платформой, когда он должен указать цвет фона отдельной ячейки.|  
|[CMFCListCtrl::OnGetCellFont](../Topic/CMFCListCtrl::OnGetCellFont.md)|Вызываемый платформой, когда он должен получить шрифт для изображаемого ячейки.|  
|[CMFCListCtrl::OnGetCellTextColor](../Topic/CMFCListCtrl::OnGetCellTextColor.md)|Вызываемый платформой, когда он должен указать цвет текста отдельной ячейки.|  
|[CMFCListCtrl::RemoveSortColumn](../Topic/CMFCListCtrl::RemoveSortColumn.md)|Удаляет столбец сортировки из списка отсортированных столбцов.|  
|[CMFCListCtrl::SetSortColumn](../Topic/CMFCListCtrl::SetSortColumn.md)|Устанавливает столбец отсортированный текущей и порядок сортировки.|  
|[CMFCListCtrl::Sort](../Topic/CMFCListCtrl::Sort.md)|Сортирует элемент управления "Список".|  
  
## Заметки  
 `CMFCListCtrl` предлагает 2 улучшения к классу [CListCtrl Class](../Topic/CListCtrl%20Class.md).  Во\-первых, оно указывает на то, что доступный параметр сортировки столбца автоматически отрисовки стрелки сортировки в заголовке.  Во\-вторых, он поддерживает сортировку данных для нескольких столбцов одновременно.  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CMFCListCtrl`.  Примере показано, как создать элемент управления "Список", столбцы вставки элементов вставки, установите текст элемента и укажите шрифт элемента управления "Список".  Этот фрагмент кода является частью [Пример demo Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/reference/codesnippet/CPP/cmfclistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/reference/codesnippet/CPP/cmfclistctrl-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CListCtrl](../Topic/CListCtrl%20Class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
## Требования  
 **заголовок:** afxlistctrl.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CListCtrl Class](../Topic/CListCtrl%20Class.md)