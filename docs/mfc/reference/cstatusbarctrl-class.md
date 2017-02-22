---
title: "CStatusBarCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl class"
  - "status bar controls"
  - "Windows common controls [C++], CStatusBarCtrl"
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CStatusBarCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности элемента управления "Строка состояния" общего Windows.  
  
## Синтаксис  
  
```  
class CStatusBarCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CStatusBarCtrl::CStatusBarCtrl](../Topic/CStatusBarCtrl::CStatusBarCtrl.md)|Создает объект `CStatusBarCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CStatusBarCtrl::Create](../Topic/CStatusBarCtrl::Create.md)|Создает элемент управления "Строка состояния" и вложение его к объекту `CStatusBarCtrl`.|  
|[CStatusBarCtrl::CreateEx](../Topic/CStatusBarCtrl::CreateEx.md)|Создает элемент управления " Строка состояния с указанными стилей расширенными Windows и вложение его к объекту `CStatusBarCtrl`.|  
|[CStatusBarCtrl::DrawItem](../Topic/CStatusBarCtrl::DrawItem.md)|Вызываемый, когда визуальный аспект элемента управления "Строка состояния" рисования владельцем изменяется.|  
|[CStatusBarCtrl::GetBorders](../Topic/CStatusBarCtrl::GetBorders.md)|Извлекает текущие ширины горизонтальных и вертикальных границ элемента управления "Строка состояния".|  
|[CStatusBarCtrl::GetIcon](../Topic/CStatusBarCtrl::GetIcon.md)|Получает значок для части \(также известной как области\) в элементе управления области текущего состояния.|  
|[CStatusBarCtrl::GetParts](../Topic/CStatusBarCtrl::GetParts.md)|Получает количество частей в элементе управления "Строка состояния".|  
|[CStatusBarCtrl::GetRect](../Topic/CStatusBarCtrl::GetRect.md)|Получает ограничивающий прямоугольник части в элементе управления "Строка состояния".|  
|[CStatusBarCtrl::GetText](../Topic/CStatusBarCtrl::GetText.md)|Извлекает текст из заданных части элемента управления "Строка состояния".|  
|[CStatusBarCtrl::GetTextLength](../Topic/CStatusBarCtrl::GetTextLength.md)|Восстановите длину \(в символах\), текст из данной части элемента управления "Строка состояния".|  
|[CStatusBarCtrl::GetTipText](../Topic/CStatusBarCtrl::GetTipText.md)|Извлекает текст подсказки для панели в строке состояния.|  
|[CStatusBarCtrl::IsSimple](../Topic/CStatusBarCtrl::IsSimple.md)|Проверяет элемент управления окна состояния для определения, является ли он в простом режиме.|  
|[CStatusBarCtrl::SetBkColor](../Topic/CStatusBarCtrl::SetBkColor.md)|Устанавливает цвет фона строки состояния.|  
|[CStatusBarCtrl::SetIcon](../Topic/CStatusBarCtrl::SetIcon.md)|Задает значок для панели в строке состояния.|  
|[CStatusBarCtrl::SetMinHeight](../Topic/CStatusBarCtrl::SetMinHeight.md)|Устанавливает минимальную высоту области рисования элемента управления строки состояния.|  
|[CStatusBarCtrl::SetParts](../Topic/CStatusBarCtrl::SetParts.md)|Устанавливает количество частей в элементе управления "Строка состояния" и координату правого края каждой части.|  
|[CStatusBarCtrl::SetSimple](../Topic/CStatusBarCtrl::SetSimple.md)|Определяет, указывает ли элемент управления "Строка состояния" обычный текст или отображаются все контрольные части заданы во время предыдущего вызова `SetParts`.|  
|[CStatusBarCtrl::SetText](../Topic/CStatusBarCtrl::SetText.md)|Устанавливает текст в данной части элемента управления "Строка состояния".|  
|[CStatusBarCtrl::SetTipText](../Topic/CStatusBarCtrl::SetTipText.md)|Задает текст всплывающей подсказки для панели в строке состояния.|  
  
## Заметки  
 Элемент управления "Строка состояния" горизонтальное окно, как правило, показываемое в нижней части родительского окна, в которой приложение может отображать различные типы сведений о состоянии.  Элемент управления " Строка состояния можно разбить на части для отображения нескольких типов сведений.  
  
 Этот элемент управления \(и, следовательно, класс `CStatusBarCtrl` \) доступны только для программ, выполняемых в рамках \/98 Windows версии 3.51 и Windows NT 95 и более поздних версий.  
  
 Дополнительные сведения об использовании `CStatusBarCtrl` см. в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CStatusBarCtrl`  
  
## Требования  
 **Header:**  afxcmn.h  
  
## См. также  
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl Class](../../mfc/reference/ctoolbarctrl-class.md)