---
title: "CMFCToolTipCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolTipCtrl class"
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCToolTipCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Расширенная реализация всплывающей подсказки на основе [CToolTipCtrl Class](../Topic/CToolTipCtrl%20Class.md).  Подсказка на основе класса `CMFCToolTipCtrl` может отображать значок, метку и описание.  Можно настроить его внешний вид с помощью градиентной заливки, пользовательских цветов текста и границы, полужирного шрифта, скругленных углов или стиля всплывающего предупреждения.  
  
## Синтаксис  
  
```  
class CMFCToolTipCtrl : public CToolTipCtrl  
```  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|Конструктор по умолчанию.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCToolTipCtrl::GetIconSize](../Topic/CMFCToolTipCtrl::GetIconSize.md)|Возвращает размер значка во всплывающей подсказке.|  
|[CMFCToolTipCtrl::GetParams](../Topic/CMFCToolTipCtrl::GetParams.md)|Возвращает параметры отображения всплывающей подсказки.|  
|[CMFCToolTipCtrl::OnDrawBorder](../Topic/CMFCToolTipCtrl::OnDrawBorder.md)|Рисует границу всплывающей подсказки.|  
|[CMFCToolTipCtrl::OnDrawDescription](../Topic/CMFCToolTipCtrl::OnDrawDescription.md)||  
|[CMFCToolTipCtrl::OnDrawIcon](../Topic/CMFCToolTipCtrl::OnDrawIcon.md)|Отображает значок во всплывающей подсказке.|  
|[CMFCToolTipCtrl::OnDrawLabel](../Topic/CMFCToolTipCtrl::OnDrawLabel.md)|Рисует заголовок всплывающей подсказки или вычисляет размер метки.|  
|[CMFCToolTipCtrl::OnDrawSeparator](../Topic/CMFCToolTipCtrl::OnDrawSeparator.md)|Рисует разделитель между меткой и описанием во всплывающей подсказке.|  
|[CMFCToolTipCtrl::OnFillBackground](../Topic/CMFCToolTipCtrl::OnFillBackground.md)|Заливает фон всплывающей подсказки.|  
|[CMFCToolTipCtrl::SetDescription](../Topic/CMFCToolTipCtrl::SetDescription.md)|Задает описание, которое отображается во всплывающей подсказке.|  
|[CMFCToolTipCtrl::SetFixedWidth](../Topic/CMFCToolTipCtrl::SetFixedWidth.md)||  
|[CMFCToolTipCtrl::SetHotRibbonButton](../Topic/CMFCToolTipCtrl::SetHotRibbonButton.md)||  
|[CMFCToolTipCtrl::SetLocation](../Topic/CMFCToolTipCtrl::SetLocation.md)||  
|[CMFCToolTipCtrl::SetParams](../Topic/CMFCToolTipCtrl::SetParams.md)|Задает внешний вид всплывающей подсказки с помощью объекта `CMFCToolTipInfo`.|  
  
## Заметки  
 Чтобы задействовать в своем приложении настроенные всплывающие подсказки, используйте совместно объекты `CMFCToolTipCtrl`, `CMFCToolTipInfo` и [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md).  
  
 Например, чтобы реализовать всплывающие подсказки в виде выносок, сделайте следующее:  
  
 1.  Используйте метод [CWinAppEx Class](../../mfc/reference/cwinappex-class.md) для инициализации диспетчера всплывающих подсказок в своем приложении.  
  
 2.  Создайте структуру `CMFCToolTipInfo`, чтобы задать необходимый стиль оформления:  
  
```  
CMFCToolTipInfo params;  
 params.m_bBoldLabel = FALSE;  
 params.m_bDrawDescription = FALSE;  
 params.m_bDrawIcon = FALSE;  
 params.m_bRoundedCorners = TRUE;  
 params.m_bDrawSeparator = FALSE;  
 if (m_bCustomColors)  
 {  
  params.m_clrFill = RGB (255, 255, 255);  
  params.m_clrFillGradient = RGB (228, 228, 240);  
  params.m_clrText = RGB (61, 83, 80);  
  params.m_clrBorder = RGB (144, 149, 168);  
 }  
```  
  
 3.  Используйте метод [CTooltipManager::SetTooltipParams](../Topic/CTooltipManager::SetTooltipParams.md), чтобы задать стиль оформления для всех всплывающих подсказок приложения \(могут применяться стили, определенные в объекте `CMFCToolTipInfo`\):  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMFCToolTipCtrl), &params);  
```  
  
 Для управления поведением всплывающей подсказки и ее отрисовкой вы также можете получить новый производный класс из класса `CMFCToolTipCtrl`.  Чтобы задать новый класс элемента управления "Всплывающая подсказка", используйте метод `CTooltipManager::SetTooltipParams`:  
  
```  
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMyToolTipCtrl))  
```  
  
 Чтобы восстановить класс элемента управления "Всплывающая подсказка" по умолчанию и сбросить оформление подсказки на стандартное, укажите значение NULL в классе среды выполнения и параметрах всплывающей подсказки в методе `SetTooltipParams`:  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    NULL, NULL);  
```  
  
## Пример  
 В следующем примере демонстрируется создание объекта `CMFCToolTipCtrl`, задание описания, отображаемого во всплывающей подсказке, а также задание ширины элемента управления "Всплывающая подсказка".  
  
 [!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/CPP/cmfctooltipctrl-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CToolTipCtrl](../Topic/CToolTipCtrl%20Class.md)  
  
 [CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)  
  
## Требования  
 **Заголовок:** afxtooltipctrl.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CToolTipCtrl Class](../Topic/CToolTipCtrl%20Class.md)   
 [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipInfo Class](../../mfc/reference/cmfctooltipinfo-class.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)