---
title: "CScrollBar Class | Microsoft Docs"
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
  - "CScrollBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления [MFC], полоса прокрутки"
  - "CScrollBar class"
  - "полосы прокрутки"
  - "SCROLLBAR window class"
  - "Windows common controls [C++], CScrollBar"
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CScrollBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности элемента управления " полоса прокрутки Windows.  
  
## Синтаксис  
  
```  
class CScrollBar : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CScrollBar::CScrollBar](../Topic/CScrollBar::CScrollBar.md)|Создает объект `CScrollBar`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CScrollBar::Create](../Topic/CScrollBar::Create.md)|Создает полоса прокрутки Windows и вложение его к объекту `CScrollBar`.|  
|[CScrollBar::EnableScrollBar](../Topic/CScrollBar::EnableScrollBar.md)|Включение или отключение одну или обе полосы прокрутки со стрелками.|  
|[CScrollBar::GetScrollBarInfo](../Topic/CScrollBar::GetScrollBarInfo.md)|Извлекает сведения о полосе прокрутки с помощью структуры `SCROLLBARINFO`.|  
|[CScrollBar::GetScrollInfo](../Topic/CScrollBar::GetScrollInfo.md)|Извлекает сведения о полосе прокрутки.|  
|[CScrollBar::GetScrollLimit](../Topic/CScrollBar::GetScrollLimit.md)|Извлекает ограничение полосы прокрутки|  
|[CScrollBar::GetScrollPos](../Topic/CScrollBar::GetScrollPos.md)|Извлекает текущее положение ползунка полосы прокрутки.|  
|[CScrollBar::GetScrollRange](../Topic/CScrollBar::GetScrollRange.md)|Извлекает текущее положение полосы прокрутки минимума и максимума для данной полосы прокрутки.|  
|[CScrollBar::SetScrollInfo](../Topic/CScrollBar::SetScrollInfo.md)|Задает сведения о полосе прокрутки.|  
|[CScrollBar::SetScrollPos](../Topic/CScrollBar::SetScrollPos.md)|Задает текущее положение ползунка полосы прокрутки.|  
|[CScrollBar::SetScrollRange](../Topic/CScrollBar::SetScrollRange.md)|Задает минимальное и максимальное значения позиции для данной полосы прокрутки.|  
|[CScrollBar::ShowScrollBar](../Topic/CScrollBar::ShowScrollBar.md)|Показать или скрывает полоса прокрутки.|  
  
## Заметки  
 Создается элемент управления " полоса прокрутки в шаге 2.  Во\-первых, вызовите конструктор `CScrollBar` для создания объекта `CScrollBar`, а затем вызвать функцию\-член [Создание](../Topic/CScrollBar::Create.md) чтобы создать элемент управления " полоса прокрутки Windows и вложить его к объектному `CScrollBar`.  
  
 При создании объекта `CScrollBar` в диалоговое окно \(через ресурс диалогового окна\), то `CScrollBar` автоматически удалено, когда пользователь закрывает диалоговое окно.  
  
 При создании объекта `CScrollBar` в это окно можно также удалить его.  
  
 При создании объекта `CScrollBar` в стеке, он удален автоматически.  При создании объекта `CScrollBar` в куче с помощью функции **новый**, необходимо вызвать метод **удалить** в объекте, чтобы удалить его, когда пользователь завершает полоса прокрутки Windows.  
  
 При выборе любая память в объекте `CScrollBar`, следует переопределить `CScrollBar` деструктор для удаления распределений.  
  
 Дополнительные сведения об использовании `CScrollBar` см. в разделе [элементы управления](../../mfc/controls-mfc.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CScrollBar`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CEdit Class](../Topic/CEdit%20Class.md)   
 [CListBox Class](../Topic/CListBox%20Class.md)   
 [CStatic Class](../Topic/CStatic%20Class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)