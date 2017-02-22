---
title: "CMFCRibbonMiniToolBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonMiniToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonMiniToolBar class"
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMFCRibbonMiniToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует контекстно\-зависимую панель инструментов контекстного меню.  
  
## Синтаксис  
  
```  
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu  
```  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Конструктор по умолчанию.|  
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCRibbonMiniToolBar::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCRibbonMiniToolBar::GetThisClass`|Используется платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), связанный с этим типом класса.|  
|[CMFCRibbonMiniToolBar::IsContextMenuMode](../Topic/CMFCRibbonMiniToolBar::IsContextMenuMode.md)||  
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](../Topic/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar.md)|\(Переопределяет метод `CMFCPopupMenu::IsRibbonMiniToolBar`.\)|  
|[CMFCRibbonMiniToolBar::SetCommands](../Topic/CMFCRibbonMiniToolBar::SetCommands.md)|Задает список команд, отображаемых на панели инструментов.|  
|[CMFCRibbonMiniToolBar::Show](../Topic/CMFCRibbonMiniToolBar::Show.md)|Отображает мини\-панель инструментов по указанным координатам экрана.|  
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](../Topic/CMFCRibbonMiniToolBar::ShowWithContextMenu.md)|Отображает мини\-панель инструментов вместе с контекстным меню.|  
  
## Заметки  
 Мини\-панель инструментов обычно отображается, когда пользователь выделяет объект в документе.  Например, после выделения блока текста в текстовом редакторе отображается мини\-панель инструментов с командами форматирования текста.  
  
 Когда указатель мыши выходит за пределы мини\-панели инструментов, она становится прозрачной.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../Topic/CMFCPopupMenu%20Class.md)  
  
 `CMFCRibbonPanelMenu`  
  
 [CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)  
  
## Требования  
 **Заголовок:** afxRibbonMiniToolBar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)