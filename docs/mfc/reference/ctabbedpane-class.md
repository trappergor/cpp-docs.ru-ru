---
title: "CTabbedPane Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTabbedPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabbedPane class"
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CTabbedPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует функциональные возможности области с отделяемыми вкладками.  
  
## Синтаксис  
  
```  
class CTabbedPane : public CBaseTabbedPane  
```  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CTabbedPane::CTabbedPane`|Конструктор по умолчанию.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTabbedPane::DetachPane](../Topic/CTabbedPane::DetachPane.md)|\(Переопределяет метод [CBaseTabbedPane::DetachPane](../Topic/CBaseTabbedPane::DetachPane.md).\)|  
|[CTabbedPane::EnableTabAutoColor](../Topic/CTabbedPane::EnableTabAutoColor.md)|Включает или выключает автоматическую цветовую маркировку вкладок.|  
|[CTabbedPane::FloatTab](../Topic/CTabbedPane::FloatTab.md)|Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке.  \(Переопределяет метод [CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md).\)|  
|[CTabbedPane::GetTabArea](../Topic/CTabbedPane::GetTabArea.md)|Возвращает размер и положение области вкладок в окне с вкладками.|  
|[CTabbedPane::GetTabWnd](../Topic/CTabbedPane::GetTabWnd.md)||  
|[CTabbedPane::HasAutoHideMode](../Topic/CTabbedPane::HasAutoHideMode.md)|Определяет возможность переключения панели с вкладками в режим автоматического скрытия.  \(Переопределяет метод [CBaseTabbedPane::HasAutoHideMode](../Topic/CBaseTabbedPane::HasAutoHideMode.md).\)|  
|[CTabbedPane::IsTabLocationBottom](../Topic/CTabbedPane::IsTabLocationBottom.md)|Определяет, расположены ли вкладки в нижней части окна.|  
|[CTabbedPane::ResetTabs](../Topic/CTabbedPane::ResetTabs.md)|Переводит все панели с вкладками в состояние по умолчанию.|  
|[CTabbedPane::SetTabAutoColors](../Topic/CTabbedPane::SetTabAutoColors.md)|Задает список пользовательских цветов, которые могут применяться, когда включена функция автоматической цветовой маркировки вкладок.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CTabbedPane::m\_bTabsAlwaysTop](../Topic/CTabbedPane::m_bTabsAlwaysTop.md)|Расположение вкладок в приложении по умолчанию.|  
|[CTabbedPane::m\_pTabWndRTC](../Topic/CTabbedPane::m_pTabWndRTC.md)|Сведения о классе среды выполнения для настраиваемого объекта, производного от класса `CMFCTabCtrl`.|  
  
## Заметки  
 Платформа автоматически создает экземпляр этого класса, когда пользователь прикрепляет одну панель к другой, подводя указатель мыши к заголовку второй панели.  Все панели с вкладками, созданные платформой, имеют идентификатор \-1.  
  
 Чтобы вместо вкладок в стиле Outlook задействовать обычные вкладки, передайте стиль `AFX_CBRS_REGULAR_TABS` методу [CDockablePane::CreateEx](../Topic/CDockablePane::CreateEx.md).  
  
 Если создать панель с отделяемыми вкладками, она может быть автоматически уничтожена платформой, поэтому лучше не оставлять указатель.  Чтобы получить указатель на панель с вкладками, вызовите метод `CBasePane::GetParentTabbedPane`.  
  
## Пример  
 В этом примере создается объект `CTabbedPane`.  После этого используется метод [CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md), чтобы прикрепить дополнительные вкладки.  
  
```  
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);  
if (!pTabbededBar->Create (_T(""), this, CRect (0, 0, 200, 200),  
                           TRUE,   
                           (UINT) -1,  
                           WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |  
                           WS_CLIPCHILDREN | CBRS_LEFT |    
                           CBRS_FLOAT_MULTI))  
{  
    TRACE0("Failed to create Solution Explorer bar\n");  
    return FALSE;      // fail to create  
}  
  
pTabbededBar->AddTab (&m_wndClassView);  
pTabbededBar->AddTab (&m_wndResourceView);  
pTabbededBar->AddTab (&m_wndFileView);  
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);  
DockPane(pTabbededBar);  
```  
  
## Пример  
 Другой способ создания объекта панели элементов управления с вкладками — использовать метод [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md).  Метод `AttachToTabWnd` динамически создает объект "Панель с вкладками", используя сведения о классе среды выполнения, заданные методом [CDockablePane::SetTabbedPaneRTC](../Topic/CDockablePane::SetTabbedPaneRTC.md).  
  
 В этом примере рассматривается динамическое создание панели с вкладками, прикрепление двух вкладок друг к другу, а также преобразование второй вкладки в неотделяемую.  
  
```  
DockPane(&m_wndClassView);  
CTabbedPane* pTabbedBar = NULL;  
m_wndResourceView.AttachToTabWnd (&m_wndClassView, DM_SHOW, TRUE,  
                                  (CDockablePane**) &pTabbedBar);  
m_wndFileView.AttachToTabWnd (pTabbedBar, DM_SHOW, TRUE,  
                              (CDockablePane**) &pTabbedBar);  
pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1, FALSE);  
```  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../Topic/CDockablePane%20Class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)  
  
## Требования  
 **Заголовок:** afxTabbedPane.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CDockablePane Class](../Topic/CDockablePane%20Class.md)   
 [Класс CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)