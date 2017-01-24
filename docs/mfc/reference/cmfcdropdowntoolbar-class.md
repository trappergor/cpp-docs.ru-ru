---
title: "CMFCDropDownToolBar Class | Microsoft Docs"
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
  - "CMFCDropDownToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownToolBar class"
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
caps.latest.revision: 37
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDropDownToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Панель инструментов, которая появляется после нажатия и удерживания верхнего уровня пользователя кнопки панели инструментов.  
  
## Синтаксис  
  
```  
class CMFCDropDownToolBar : public CMFCToolBar  
```  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](../Topic/CMFCDropDownToolBar::AllowShowOnPaneMenu.md)|\(Переопределяет `CPane::AllowShowOnPaneMenu`\).|  
|[CMFCDropDownToolBar::LoadBitmap](../Topic/CMFCDropDownToolBar::LoadBitmap.md)|\(Переопределяет [CMFCToolBar::LoadBitmap](../Topic/CMFCToolBar::LoadBitmap.md)\).|  
|[CMFCDropDownToolBar::LoadToolBar](../Topic/CMFCDropDownToolBar::LoadToolBar.md)|\(Переопределяет [CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md)\).|  
|[CMFCDropDownToolBar::OnLButtonUp](../Topic/CMFCDropDownToolBar::OnLButtonUp.md)||  
|[CMFCDropDownToolBar::OnMouseMove](../Topic/CMFCDropDownToolBar::OnMouseMove.md)||  
|[CMFCDropDownToolBar::OnSendCommand](../Topic/CMFCDropDownToolBar::OnSendCommand.md)|\(Переопределяет `CMFCToolBar::OnSendCommand`\).|  
|[CMFCDropDownToolBar::OnUpdateCmdUI](../Topic/CMFCDropDownToolBar::OnUpdateCmdUI.md)|\(Переопределяет [CMFCToolBar::OnUpdateCmdUI](http://msdn.microsoft.com/ru-ru/571a38ab-2a56-4968-9796-273516126f80)\).|  
  
### Заметки  
 Объект `CMFCDropDownToolBar` объединяет внешнего вида панели инструментов с реакцией на событие раскрывающегося меню.  После нажатия и удерживания пользователя кнопка панели инструментов раскрывающаяся \(см. [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)\), раскрывающаяся панель инструментов отображаются, и пользователь может выбрать из раскрывающейся кнопки панели инструментов при прокрутке к ней и освобождении кнопки мыши.  После того как пользователь выбирает кнопку панели инструментов в раскрывающейся эта кнопка отображается в качестве текущей кнопку на верхнем уровне панели инструментов.  
  
 Раскрывающаяся панель инструментов нельзя настраивать или закрепить, и она не имеет перемещаемое состояние.  
  
 На следующем рисунке показан объект `CMFCDropDownToolBar`:  
  
 ![Пример CMFCDropDownToolbar](../../mfc/reference/media/cmfcdropdown.png "CMFCDropDown")  
  
 Создается объект `CMFCDropDownToolBar` так же, как будет создана обычная панель инструментов \(см. [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)\).  
  
 Вставить панель инструментов падающую вниз в родительской панели инструментов.  
  
 1.  Зарезервируйте фиктивное идентификатор ресурса для кнопки в родительском ресурсе панели инструментов.  
  
 2.  Создайте объект `CMFCDropDownToolBarButton`, который содержит панель инструментов падающую вниз \(дополнительные сведения см. в разделе [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../Topic/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton.md)\).  
  
 3.  Замените думмичная кнопку с объектом `CMFCDropDownToolBarButton` с помощью [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  
  
 Дополнительные сведения о кнопках панели инструментов см. в разделе [Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md).  Пример раскрывающейся панели инструментов см. в разделе проекта образец VisualStudioDemo.  
  
## Пример  
 В следующем примере показано, как использовать метод `Create` в классе `CMFCDropDownToolBar`.  Этот фрагмент кода является частью [Пример demo Visual Studio](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/reference/codesnippet/CPP/cmfcdropdowntoolbar-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/reference/codesnippet/CPP/cmfcdropdowntoolbar-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)  
  
## Требования  
 **заголовок:** afxdropdowntoolbar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [CMFCDropDownToolbarButton Class](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)   
 [Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)