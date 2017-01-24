---
title: "CMFCDropDownFrame Class | Microsoft Docs"
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
  - "CMFCDropDownFrame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownFrame class"
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDropDownFrame Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности падающую вниз фреймового окна раскрывающиеся панели инструментов кнопки панели инструментов и раскрывающиеся.  
  
## Синтаксис  
  
```  
class CMFCDropDownFrame : public CMiniFrameWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CMFCDropDownFrame::CMFCDropDownFrame`|Конструктор по умолчанию.|  
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Деструктор.|  
  
### Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCDropDownFrame::Create](../Topic/CMFCDropDownFrame::Create.md)|Создает объект `CMFCDropDownFrame`.|  
|`CMFCDropDownFrame::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|[CMFCDropDownFrame::GetParentMenuBar](../Topic/CMFCDropDownFrame::GetParentMenuBar.md)|Получает родительскую строку меню кадра раскрывающегося списка.|  
|[CMFCDropDownFrame::GetParentPopupMenu](../Topic/CMFCDropDownFrame::GetParentPopupMenu.md)|Возвращает родительский элемент контекстного меню меню кадра раскрывающегося списка.|  
|`CMFCDropDownFrame::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CMFCDropDownFrame::RecalcLayout](../Topic/CMFCDropDownFrame::RecalcLayout.md)|Перемещает выпадающий кадр.|  
|[CMFCDropDownFrame::SetAutoDestroy](../Topic/CMFCDropDownFrame::SetAutoDestroy.md)|Наборы удалено, является ли список дочерних элементов панели инструментов автоматически.|  
  
### Заметки  
 Данный класс не предназначен для непосредственного использования в коде.  
  
 Инфраструктура использует этот класс для реализации расширения функциональности кадра классы `CMFCDropDownToolbar` и `CMFCDropDownToolbarButton`.  Дополнительные сведения об этих классах содержатся в разделах [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md) и [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).  
  
## Пример  
 В следующем примере показано, как получить указатель на объект `CMFCDropDownFrame` от класса `CFrameWnd`, и, как задать раскрывающийся список дочерних элементов панели инструментов уничтожаемый автоматически.  
  
 [!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/CPP/cmfcdropdownframe-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)  
  
## Требования  
 **заголовок:** afxdropdowntoolbar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)