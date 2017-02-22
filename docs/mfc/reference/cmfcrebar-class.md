---
title: "CMFCReBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCReBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCReBar class"
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CMFCReBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Объект `CMFCReBar` панель элементов управления, предоставляющий структуру, сохраняемости, а также сведения о состоянии элементов управления " Главная панель.  
  
## Синтаксис  
  
```  
class CMFCReBar : public CPane  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCReBar::AddBar](../Topic/CMFCReBar::AddBar.md)|Добавляет диапазон на главной панели.|  
|[CMFCReBar::CalcFixedLayout](../Topic/CMFCReBar::CalcFixedLayout.md)|\(Переопределяет [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md)\).|  
|[CMFCReBar::CanFloat](../Topic/CMFCReBar::CanFloat.md)|\(Переопределяет [CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md)\).|  
|[CMFCReBar::Create](../Topic/CMFCReBar::Create.md)|Создает элемент управления "Главная панель" и вложение его к объекту `CMFCReBar`.|  
|[CMFCReBar::EnableDocking](../Topic/CMFCReBar::EnableDocking.md)|\(Переопределяет [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md)\).|  
|[CMFCReBar::GetReBarBandInfoSize](../Topic/CMFCReBar::GetReBarBandInfoSize.md)||  
|[CMFCReBar::GetReBarCtrl](../Topic/CMFCReBar::GetReBarCtrl.md)|Предоставляет прямой доступ к базовому элементу управления [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) общему.|  
|[CMFCReBar::OnShowControlBarMenu](../Topic/CMFCReBar::OnShowControlBarMenu.md)|\(Переопределяет [CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md)\).|  
|[CMFCReBar::OnToolHitTest](../Topic/CMFCReBar::OnToolHitTest.md)|\(Переопределяет [CWnd::OnToolHitTest](../Topic/CWnd::OnToolHitTest.md)\).|  
|[CMFCReBar::OnUpdateCmdUI](../Topic/CMFCReBar::OnUpdateCmdUI.md)|\(Переопределяет [CBasePane::OnUpdateCmdUI](http://msdn.microsoft.com/ru-ru/e139f06a-9793-4ee2-bc3d-517389368c77)\).|  
|[CMFCReBar::SetPaneAlignment](../Topic/CMFCReBar::SetPaneAlignment.md)|\(Переопределяет [CBasePane::SetPaneAlignment](../Topic/CBasePane::SetPaneAlignment.md)\).|  
  
## Заметки  
 Объект `CMFCReBar` может содержать множество дочерние окна.  Сюда входят поля ввода, панели инструментов и списки.  Можно изменить размер главная панель или программно, пользователь мог вручную размер главная панель путем перетаскивания его панель отслеживания.  Можно также задать фон объекта главной панели в растровое изображение.  
  
 Объект главной панели ведет себя подобно объекту панели инструментов.  Элемент управления "Главная панель" может содержать один или несколько полосы, и каждый диапазон может содержать панель отслеживания, растровое изображение, текстовую подпись и дочернее окно.  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CMFCReBar`.  Примере показано, как создать элемент управления "Главная панель" и добавление полосы на него.  Функции полосы как внутренняя панель инструментов.  Этот фрагмент кода является частью [Образец тестирования главной панели](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/CPP/cmfcrebar-class_1.h)]  
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/CPP/cmfcrebar-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md) [CCmdTarget](../Topic/CCmdTarget%20Class.md) [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)  
  
## Требования  
 **заголовок:** afxRebar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CReBarCtrl Class](../../mfc/reference/crebarctrl-class.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)