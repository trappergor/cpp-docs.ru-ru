---
title: "CAutoHideDockSite Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAutoHideDockSite"
  - "AllowShowOnPaneMenu"
  - "CAutoHideDockSite::AllowShowOnPaneMenu"
  - "CAutoHideDockSite.AllowShowOnPaneMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AllowShowOnPaneMenu method"
  - "CAutoHideDockSite class"
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 33
---
# CAutoHideDockSite Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CAutoHideDockSite` расширяет [CDockSite Class](../../mfc/reference/cdocksite-class.md) панели закрепления автоматического скрытия ".  
  
## Синтаксис  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CAutoHideDockSite::CAutoHideDockSite`|Создает объект `CAutoHideDockSite`.|  
|`CAutoHideDockSite::~CAutoHideDockSite`|Деструктор.|  
  
### Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|`CAutoHideDockSite::AllowShowOnPaneMenu`|Указывает, отображается ли `CAutoHideDockSite` в меню панели.|  
|[CAutoHideDockSite::CanAcceptPane](../Topic/CAutoHideDockSite::CanAcceptPane.md)|Определяет, является ли базовый объект является производным от [CMFCAutoHideBar Class](../Topic/CMFCAutoHideBar%20Class.md) панели.|  
|[CAutoHideDockSite::DockPane](../Topic/CAutoHideDockSite::DockPane.md)|Закрепит панель к данному объекту `CAuotHideDockSite`.|  
|[CAutoHideDockSite::GetAlignRect](../Topic/CAutoHideDockSite::GetAlignRect.md)|Извлекает размер сайта закрепления в координатах экрана.|  
|[CAutoHideDockSite::RepositionPanes](../Topic/CAutoHideDockSite::RepositionPanes.md)|Перерисовывает панель, на `CAutoHideDockSite` с глобальными полями и дистанционированием кнопки.|  
|[CAutoHideDockSite::SetOffsetLeft](../Topic/CAutoHideDockSite::SetOffsetLeft.md)|Устанавливает поля на левой стороне панели закрепления.|  
|[CAutoHideDockSite::SetOffsetRight](../Topic/CAutoHideDockSite::SetOffsetRight.md)|Устанавливает поля в правой части панели закрепления.|  
|[CAutoHideDockSite::UnSetAutoHideMode](../Topic/CAutoHideDockSite::UnSetAutoHideMode.md)|Вызовы [CMFCAutoHideBar::UnSetAutoHideMode](../Topic/CMFCAutoHideBar::UnSetAutoHideMode.md) для объектов на `CAutoHideDockSite`.|  
  
### Элементы данных  
  
|||  
|-|-|  
|Имя|Описание|  
|[CAutoHideDockSite::m\_nExtraSpace](../Topic/CAutoHideDockSite::m_nExtraSpace.md)|Определяет размер пространства между панели инструментов панели закрепления и граничную.  Эта область определяется из левого края, верхнего края в зависимости от выравнивания для закрепления.|  
  
## Заметки  
 При вызове [CFrameWndEx::EnableAutoHidePanes](../Topic/CFrameWndEx::EnableAutoHidePanes.md), инфраструктура автоматически создают объект `CAutoHideDockSite`.  В большинстве случаев следует создавать экземпляр или использования этого класса напрямую.  
  
 На панели закрепления разрыв между левыми панели закрепления и левым [CMFCAutoHideButton Class](../../mfc/reference/cmfcautohidebutton-class.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## Пример  
 В следующем примере показано, как получить объект `CAutoHideDockSite` из объекта `CMFCAutoHideBar`, и, как задать левые и правое поле панели закрепления.  
  
 [!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/CPP/cautohidedocksite-class_1.cpp)]  
  
## Требования  
 **заголовок:** afxautohidedocksite.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CDockSite Class](../../mfc/reference/cdocksite-class.md)