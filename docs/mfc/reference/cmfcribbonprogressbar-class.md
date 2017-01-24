---
title: "CMFCRibbonProgressBar Class | Microsoft Docs"
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
  - "CMFCRibbonProgressBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonProgressBar class"
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonProgressBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует визуальный элемент управления, который отображает ход выполнения длительной операции.  
  
## Синтаксис  
  
```  
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](../Topic/CMFCRibbonProgressBar::CMFCRibbonProgressBar.md)|Создания и инициализации объект `CMFCRibbonProgressBar`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonProgressBar::GetPos](../Topic/CMFCRibbonProgressBar::GetPos.md)|Возвращает текущий ход выполнения.|  
|[CMFCRibbonProgressBar::GetRangeMax](../Topic/CMFCRibbonProgressBar::GetRangeMax.md)|Возвращает максимальное значение текущего диапазона.|  
|[CMFCRibbonProgressBar::GetRangeMin](../Topic/CMFCRibbonProgressBar::GetRangeMin.md)|Возвращает минимальное значение текущего диапазона.|  
|[CMFCRibbonProgressBar::GetRegularSize](../Topic/CMFCRibbonProgressBar::GetRegularSize.md)|Возвращает обычный размер элемента ленты.  \(Переопределяет [CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md)\).|  
|[CMFCRibbonProgressBar::IsInfiniteMode](../Topic/CMFCRibbonProgressBar::IsInfiniteMode.md)|Указывает, работает ли индикатор выполнения в бесконечном режиме.|  
|[CMFCRibbonProgressBar::OnDraw](../Topic/CMFCRibbonProgressBar::OnDraw.md)|Вызываемый платформой для рисования элемента ленты.  \(Переопределяет [CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md)\).|  
|[CMFCRibbonProgressBar::SetInfiniteMode](../Topic/CMFCRibbonProgressBar::SetInfiniteMode.md)|Задает индикатор выполнения для работы в режиме бесконечном.|  
|[CMFCRibbonProgressBar::SetPos](../Topic/CMFCRibbonProgressBar::SetPos.md)|Задает текущий ход выполнения.|  
|[CMFCRibbonProgressBar::SetRange](../Topic/CMFCRibbonProgressBar::SetRange.md)|Задает минимальное и максимальное значения.|  
  
## Заметки  
 `CMFCRibbonProgressBar` может работать в 2 режимах: обычный и неограниченный.  В обычном режиме, индикатор выполнения заполнен из левого направо и останавливается при достижении максимального значения.  В режиме бесконечном индикатор выполнения заполнен повторно с минимальной значения к максимальному значению.  Можно указать бесконечный режим, чтобы указать, что операция выполняющихся, но время выполнения неизвестно.  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CMFCRibbonProgressBar`.  Примере показано, как настроить индикатор выполнения для работы в режиме бесконечном \(где время завершения операции неизвестно\), установите минимальное и максимальное значения для индикатора выполнения и укажите текущее положение индикатора выполнения.  Этот фрагмент кода является частью [Пример demo MS office 2007](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_MSOffice2007Demo#11](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#11)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)  
  
## Требования  
 **заголовок:** afxRibbonProgressBar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)