---
title: "CMFCShellListCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCShellListCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCShellListCtrl class"
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCShellListCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCShellListCtrl` предоставляет функциональные возможности элемента управления "Список" Windows и развернуть его, включив возможность отображать список элементов оболочки.  
  
## Синтаксис  
  
```  
class CMFCShellListCtrl : public CMFCListCtrl  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCShellListCtrl::DisplayFolder](../Topic/CMFCShellListCtrl::DisplayFolder.md)|Отображает список элементов, содержащихся в предоставленной папке.|  
|[CMFCShellListCtrl::DisplayParentFolder](../Topic/CMFCShellListCtrl::DisplayParentFolder.md)|Отображает список элементов, содержащихся в папке, которая является родительским для отображаемой в текущий момент папки.|  
|[CMFCShellListCtrl::EnableShellContextMenu](../Topic/CMFCShellListCtrl::EnableShellContextMenu.md)|Включение или отключение контекстное меню.|  
|[CMFCShellListCtrl::GetCurrentFolder](../Topic/CMFCShellListCtrl::GetCurrentFolder.md)|Возвращает путь текущей папки.|  
|[CMFCShellListCtrl::GetCurrentFolderName](../Topic/CMFCShellListCtrl::GetCurrentFolderName.md)|Получает имя текущей папки.|  
|[CMFCShellListCtrl::GetCurrentItemIdList](../Topic/CMFCShellListCtrl::GetCurrentItemIdList.md)|Возвращает PIDL текущего элемента управления "Список".|  
|[CMFCShellListCtrl::GetCurrentShellFolder](../Topic/CMFCShellListCtrl::GetCurrentShellFolder.md)|Возвращает указатель на текущий каталог командной оболочки.|  
|[CMFCShellListCtrl::GetItemPath](../Topic/CMFCShellListCtrl::GetItemPath.md)|Возвращает текстовый путь к элементу.|  
|[CMFCShellListCtrl::GetItemTypes](../Topic/CMFCShellListCtrl::GetItemTypes.md)|Типы элементов оболочки возвращений, отображаемых элементом управления "Список".|  
|[CMFCShellListCtrl::IsDesktop](../Topic/CMFCShellListCtrl::IsDesktop.md)|Проверяет, если выбранная в данный момент папку папка рабочего стола.|  
|[CMFCShellListCtrl::OnCompareItems](../Topic/CMFCShellListCtrl::OnCompareItems.md)|Платформа вызывает этот метод, когда они сравниваются 2 элементов.  \(Переопределяет [CMFCListCtrl::OnCompareItems](../Topic/CMFCListCtrl::OnCompareItems.md)\).|  
|[CMFCShellListCtrl::OnFormatFileDate](../Topic/CMFCShellListCtrl::OnFormatFileDate.md)|Вызываемый, когда платформа получает дату файла, представленная элементом управления "Список".|  
|[CMFCShellListCtrl::OnFormatFileSize](../Topic/CMFCShellListCtrl::OnFormatFileSize.md)|Вызываемый, когда платформа преобразования размер файла элемента управления "Список".|  
|[CMFCShellListCtrl::OnGetItemIcon](../Topic/CMFCShellListCtrl::OnGetItemIcon.md)|Вызываемый, когда платформа получает значок элемента управления "Список".|  
|[CMFCShellListCtrl::OnGetItemText](../Topic/CMFCShellListCtrl::OnGetItemText.md)|Вызываемый, когда платформа преобразуют текст элемента управления "Список".|  
|[CMFCShellListCtrl::OnSetColumns](../Topic/CMFCShellListCtrl::OnSetColumns.md)|Вызывается инфраструктурой при установке имена столбцов.|  
|[CMFCShellListCtrl::Refresh](../Topic/CMFCShellListCtrl::Refresh.md)|Обновляет и обновляет элемент управления "Список".|  
|[CMFCShellListCtrl::SetItemTypes](../Topic/CMFCShellListCtrl::SetItemTypes.md)|Задает тип элементов, отображаемых элементом управления "Список".|  
  
## Заметки  
 Класс `CMFCShellListCtrl` расширяющий функциональность [CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md), позволяя программе для перечисления элементов оболочки Windows.  Формат отображения, используемый в качестве из списка для окна обозревателя.  
  
 Объект [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) может быть связан с объектом `CMFCShellListCtrl` для создания полного окно обозреватель моделей.  Затем выберите элемент `CMFCShellTreeCtrl` создает объект `CMFCShellListCtrl` перечислить содержимое выбранного элемента.  
  
## Пример  
 В следующем примере показано, как создать объект класса `CMFCShellListCtrl` и способ отображения родительскую папку отображаемой в данный момент папки.  Этот фрагмент кода является частью [Образец обозревателя](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#1](../../mfc/reference/codesnippet/CPP/cmfcshelllistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#2](../../mfc/reference/codesnippet/CPP/cmfcshelllistctrl-class_2.cpp)]  
[!code-cpp[NVC_MFC_Explorer#3](../../mfc/reference/codesnippet/CPP/cmfcshelllistctrl-class_3.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CListCtrl](../Topic/CListCtrl%20Class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)  
  
## Требования  
 **заголовок:** afxshelllistCtrl.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md)   
 [CMFCShellTreeCtrl Class](../../mfc/reference/cmfcshelltreectrl-class.md)