---
title: "Класс CMFCOutlookBar | Microsoft Docs"
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
  - "CMFCOutlookBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс CMFCOutlookBar"
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
caps.latest.revision: 34
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CMFCOutlookBar
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Нашитая области с внешним видом **Область переходов** в Microsoft Outlook 2000 и outlook 2003.  Объект `CMFCOutlookBar` содержит объект [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md) и ряде вкладок.  Вкладки могут быть или объектами [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md) или `CWnd`\- производными объектами.  Пользователю, панели outlook отображается как набор кнопок и области отображения.  Когда пользователь нажимает кнопку, соответствующую отображается область элемента управления или кнопки.  
  
## Синтаксис  
  
```  
class CMFCOutlookBar : public CBaseTabbedPane  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCOutlookBar::CMFCOutlookBar`|Конструктор по умолчанию.|  
|`CMFCOutlookBar::~CMFCOutlookBar`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](../Topic/CMFCOutlookBar::AllowDestroyEmptyTabbedPane.md)|Определяет, является ли нашитую пустую область можно удалить.  Переопределения \( [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../Topic/CBaseTabbedPane::AllowDestroyEmptyTabbedPane.md)\).|  
|[CMFCOutlookBar::CanAcceptPane](../Topic/CMFCOutlookBar::CanAcceptPane.md)|Определяет, является ли другая область можно закрепить в области панели outlook.  \(Переопределения CDockablePane::CanAcceptPane\).|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](../Topic/CMFCOutlookBar::CanSetCaptionTextToTabName.md)|Определяет, отображать ли заголовок для нашитой области той же текст, как активная вкладку.  Переопределения \( [CBaseTabbedPane::CanSetCaptionTextToTabName](../Topic/CBaseTabbedPane::CanSetCaptionTextToTabName.md)\).|  
|[CMFCOutlookBar::Create](../Topic/CMFCOutlookBar::Create.md)|Создается элемент управления панели outlook.|  
|[CMFCOutlookBar::CreateCustomPage](../Topic/CMFCOutlookBar::CreateCustomPage.md)|Создание настраиваемой вкладки панели outlook.|  
|`CMFCOutlookBar::CreateObject`|Используется средой выполнения для создания динамического экземпляр этого типа класса.|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](../Topic/CMFCOutlookBar::DoesAllowDynInsertBefore.md)|Определяет, может ли пользователь закрепление панели элементов управления на внешний стороне панели outlook.|  
|[CMFCOutlookBar::FloatTab](../Topic/CMFCOutlookBar::FloatTab.md)|Будет плавающим область, но только если область в данный момент находится в отделяемой вкладке.  Переопределения \( [CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md)\).|  
|[CMFCOutlookBar::GetButtonsFont](../Topic/CMFCOutlookBar::GetButtonsFont.md)|Возвращает шрифт текста кнопок панели outlook.|  
|[CMFCOutlookBar::GetTabArea](../Topic/CMFCOutlookBar::GetTabArea.md)|Возвращает размер и положение областей вкладки на панели outlook.  Переопределения \( [CBaseTabbedPane::GetTabArea](../Topic/CBaseTabbedPane::GetTabArea.md)\).|  
|`CMFCOutlookBar::GetThisClass`|Используется средой выполнения для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CMFCOutlookBar::IsMode2003](../Topic/CMFCOutlookBar::IsMode2003.md)|Определяет, является ли расширение функциональности имитаторов панели outlook, Microsoft Office Outlook 2003 \(см. примечания\).|  
|[CMFCOutlookBar::OnAfterAnimation](../Topic/CMFCOutlookBar::OnAfterAnimation.md)|Вызывается после активной вкладке [CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md) задает использование анимации.|  
|[CMFCOutlookBar::OnBeforeAnimation](../Topic/CMFCOutlookBar::OnBeforeAnimation.md)|Вызывается [CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md) перед страницей вкладок задает в качестве активной вкладки с помощью анимации.|  
|[CMFCOutlookBar::OnScroll](../Topic/CMFCOutlookBar::OnScroll.md)|Вызывается средой выполнения при панели outlook прокрутка вверх или вниз.|  
|[CMFCOutlookBar::RemoveCustomPage](../Topic/CMFCOutlookBar::RemoveCustomPage.md)|Удаление пользовательской вкладки панели outlook.|  
|[CMFCOutlookBar::SetButtonsFont](../Topic/CMFCOutlookBar::SetButtonsFont.md)|Задает шрифт текста кнопок панели outlook.|  
|[CMFCOutlookBar::SetMode2003](../Topic/CMFCOutlookBar::SetMode2003.md)|Определяет, является ли расширение функциональности имитаторов панели outlook, outlook 2003 \(см. примечания\).|  
  
## Заметки  
 Пример панели outlook см. в разделе [Пример OutlookDemo: Приложение MFC с возможностями outlook](../../top/visual-cpp-samples.md).  
  
## Реализация панели outlook  
 Для использования элемента управления `CMFCOutlookBar` в приложении, выполните следующие действия.  
  
1.  Внедрить объект `CMFCOutlookBar` в главный класс фреймового окна.  
  
    ```  
    class CMainFrame : public CMDIFrameWnd  
     { ...  
         CMFCOutlookBar         m_wndOutlookBar;  
         CMFCOutlookBarPane     m_wndOutlookPane;  
    ... };  
    ```  
  
2.  При обработке сообщения `WM_CREATE` в большой ЭВМ, вызовите метод [CMFCOutlookBar::Create](../Topic/CMFCOutlookBar::Create.md) для создания элемента управления TAB панели outlook.  
  
    ```  
    m_wndOutlookBar.Create (_T("Shortcuts"), this, CRect (0, 0, 100, 100), ID_VIEW_OUTLOOKBAR, WS_CHILD | WS_VISIBLE | CBRS_LEFT);  
    ```  
  
3.  Получите указатель в базовом буфере `CMFCOutlookBarTabCtrl` с помощью [CBaseTabbedPane::GetUnderlyingWindow](../Topic/CBaseTabbedPane::GetUnderlyingWindow.md).  
  
    ```  
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();  
    ```  
  
4.  Создайте объект [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md) для каждой вкладки, содержащей кнопки.  
  
    ```  
    m_wndOutlookPane.Create (&m_wndOutlookBar, AFX_DEFAULT_TOOLBAR_STYLE, ID_OUTLOOK_PANE_GENERAL, AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);  
    // make the Outlook pane detachable (enable docking)  
    m_wndOutlookPane.EnableDocking (CBRS_ALIGN_ANY);  
    // add buttons  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_MAINFRAME), "About", ID_APP_ABOUT);  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON), "Open", ID_FILE_OPEN);  
    ```  
  
5.  Вызовите [CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md) для добавления в каждой новой вкладки.  Присвойте параметру `bDetachable` значение `FALSE`, чтобы сделать страницы не отделяемой.  Или используйте [CMFCOutlookBarTabCtrl::AddControl](../Topic/CMFCOutlookBarTabCtrl::AddControl.md), чтобы добавить отделяемые страницы.  
  
    ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);   
    ```  
  
6.  Добавление `CWnd` производный от элемента управления \(например, [CMFCShellTreeCtrl Class](../../mfc/reference/cmfcshelltreectrl-class.md)\) вкладкой, создает элемент управления и вызвать функцию [CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md), чтобы добавить его на панели outlook.  
  
> [!NOTE]
>  Необходимо использовать уникальный идентификатор элемента управления для каждого объекта [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md) и для каждого `CWnd`\- производного объекта.  
  
 Динамическое добавление или удаление новые страницы во время выполнения, параметра [CMFCOutlookBar::CreateCustomPage](../Topic/CMFCOutlookBar::CreateCustomPage.md) и [CMFCOutlookBar::RemoveCustomPage](../Topic/CMFCOutlookBar::RemoveCustomPage.md).  
  
## Режим outlook 2003  
 В режиме 2003 outlook, кнопки вкладки расположены внизу области панели outlook.  Если недостаточно места отображения кнопки, они отображаются в виде значков похожей на панели инструментов области в нижней части области.  
  
 Используйте [CMFCOutlookBar::SetMode2003](../Topic/CMFCOutlookBar::SetMode2003.md), чтобы включить режим 2003 outlook.  Используйте [CMFCOutlookBarTabCtrl::SetToolbarImageList](../Topic/CMFCOutlookBarTabCtrl::SetToolbarImageList.md) для задания растровое изображение, содержащее Значки, которые отображаются в нижней части панели outlook.  Значки в растровом изображении должны быть упорядочены по индексу вкладки.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../Topic/CDockablePane%20Class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)  
  
## Требования  
 **Заголовок:** afxoutlookbar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [Класс CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md)