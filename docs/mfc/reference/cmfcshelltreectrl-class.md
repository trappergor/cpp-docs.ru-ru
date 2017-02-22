---
title: "CMFCShellTreeCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCShellTreeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCShellTreeCtrl class"
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCShellTreeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCShellTreeCtrl` расширяющий функциональность [CTreeCtrl Class](../../mfc/reference/ctreectrl-class.md) путем отображения иерархии элементов оболочки.  
  
## Синтаксис  
  
```  
class CMFCShellTreeCtrl : public CTreeCtrl  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCShellTreeCtrl::EnableShellContextMenu](../Topic/CMFCShellTreeCtrl::EnableShellContextMenu.md)|Включение или отключение контекстное меню.|  
|[CMFCShellTreeCtrl::GetFlags](../Topic/CMFCShellTreeCtrl::GetFlags.md)|Возвращает флаги сочетания, которые передаются в [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).|  
|[CMFCShellTreeCtrl::GetItemPath](../Topic/CMFCShellTreeCtrl::GetItemPath.md)|Возвращает путь к элементу.|  
|[CMFCShellTreeCtrl::GetRelatedList](../Topic/CMFCShellTreeCtrl::GetRelatedList.md)|Возвращает указатель на объект [CMFCShellListCtrl Class](../../mfc/reference/cmfcshelllistctrl-class.md), который используется вместе с этим объектом `CMFCShellTreeCtrl` для создания Обозреватель\- как окно.|  
|[CMFCShellTreeCtrl::OnChildNotify](../Topic/CMFCShellTreeCtrl::OnChildNotify.md)|Этот вызов функции\-члена родительским окном данного окна при получении сообщения уведомления, которое применяется к этому окну.  \(Переопределяет [CWnd::OnChildNotify](../Topic/CWnd::OnChildNotify.md)\).|  
|[CMFCShellTreeCtrl::OnGetItemIcon](../Topic/CMFCShellTreeCtrl::OnGetItemIcon.md)||  
|[CMFCShellTreeCtrl::OnGetItemText](../Topic/CMFCShellTreeCtrl::OnGetItemText.md)||  
|[CMFCShellTreeCtrl::Refresh](../Topic/CMFCShellTreeCtrl::Refresh.md)|Обновляет текущий объект и обновляет `CMFCShellTreeCtrl`.|  
|[CMFCShellTreeCtrl::SelectPath](../Topic/CMFCShellTreeCtrl::SelectPath.md)|Выбирает соответствующий элемент управления дерева на основе предоставленного пути PIDL или строки.|  
|[CMFCShellTreeCtrl::SetFlags](../Topic/CMFCShellTreeCtrl::SetFlags.md)|Наборы пометят для фильтрации контекст дерева \(аналогичный к флагам, используемым `IShellFolder::EnumObjects`\).|  
|[CMFCShellTreeCtrl::SetRelatedList](../Topic/CMFCShellTreeCtrl::SetRelatedList.md)|Устанавливает связь между текущим объектом `CMFCShellTreeCtrl` и объектом `CMFCShellListCtrl`.|  
  
## Заметки  
 Этот класс расширяет класс `CTreeCtrl`, позволяя программе, чтобы включить элементы оболочки Windows в дереве.  Этот класс может быть связан с объектом `CMFCShellListCtrl` для создания полного окно обозреватель моделей.  Затем выбрать элемент в дереве отобразит список элементов оболочки Windows в связанном списке.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CTreeCtrl](../../mfc/reference/ctreectrl-class.md)  
  
 [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)  
  
## Требования  
 **заголовок:** afxshelltreeCtrl.h  
  
## Пример  
 В следующем примере показано, как создать объект класса `CMFCShellTreeCtrl`.  Этот фрагмент кода является частью [Образец обозревателя](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/CPP/cmfcshelltreectrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/CPP/cmfcshelltreectrl-class_2.cpp)]  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CTreeCtrl Class](../../mfc/reference/ctreectrl-class.md)   
 [CMFCShellListCtrl Class](../../mfc/reference/cmfcshelllistctrl-class.md)