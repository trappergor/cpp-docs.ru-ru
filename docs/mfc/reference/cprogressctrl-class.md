---
title: "CProgressCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CProgressCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CProgressCtrl class"
  - "Internet Explorer 4.0 common controls"
  - "progress controls [C++], CProgressCtrl class"
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CProgressCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности управления "Индикатор выполнения" Windows общего.  
  
## Синтаксис  
  
```  
class CProgressCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CProgressCtrl::CProgressCtrl](../Topic/CProgressCtrl::CProgressCtrl.md)|Создает объект `CProgressCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CProgressCtrl::Create](../Topic/CProgressCtrl::Create.md)|Создает элемент управления "Индикатор выполнения" и вложение его к объекту `CProgressCtrl`.|  
|[CProgressCtrl::CreateEx](../Topic/CProgressCtrl::CreateEx.md)|Создает элемент управления "Индикатор выполнения" с заданными стилей расширенными Windows и вложение его к объекту `CProgressCtrl`.|  
|[CProgressCtrl::GetBarColor](../Topic/CProgressCtrl::GetBarColor.md)|Возвращает цвет области индикатора хода выполнения для текущего элемента управления "Индикатор выполнения".|  
|[CProgressCtrl::GetBkColor](../Topic/CProgressCtrl::GetBkColor.md)|Возвращает цвет фона текущего индикатора выполнения.|  
|[CProgressCtrl::GetPos](../Topic/CProgressCtrl::GetPos.md)|Возвращает текущее положение индикатора выполнения.|  
|[CProgressCtrl::GetRange](../Topic/CProgressCtrl::GetRange.md)|Возвращает верхние пределы диапазона нижней и управления "Индикатор выполнения".|  
|[CProgressCtrl::GetState](../Topic/CProgressCtrl::GetState.md)|Получает состояние текущего управления "Индикатор выполнения".|  
|[CProgressCtrl::GetStep](../Topic/CProgressCtrl::GetStep.md)|Получает приращение шага для индикатора выполнения текущего управления "Индикатор выполнения".|  
|[CProgressCtrl::OffsetPos](../Topic/CProgressCtrl::OffsetPos.md)|Перемещает текущую позицию управления "Индикатор выполнения" определенным шагом и перерисовывает панель, чтобы отразить новое положение.|  
|[CProgressCtrl::SetBarColor](../Topic/CProgressCtrl::SetBarColor.md)|Устанавливает цвет области индикатора хода выполнения на текущем элементе управления "Индикатор выполнения".|  
|[CProgressCtrl::SetBkColor](../Topic/CProgressCtrl::SetBkColor.md)|Устанавливает цвет фона для индикатора выполнения.|  
|[CProgressCtrl::SetMarquee](../Topic/CProgressCtrl::SetMarquee.md)|Режим бегущей строки поворотов с одиночным или выключение для текущего элемента управления "Индикатор выполнения".|  
|[CProgressCtrl::SetPos](../Topic/CProgressCtrl::SetPos.md)|Задает текущую позицию для управления "Индикатор выполнения" и перерисовывает панель, чтобы отразить новое положение.|  
|[CProgressCtrl::SetRange](../Topic/CProgressCtrl::SetRange.md)|Устанавливает минимальный и максимальный диапазон для элемента управления "Индикатор выполнения" и перерисовывает панели, отображая новые диапазоны.|  
|[CProgressCtrl::SetState](../Topic/CProgressCtrl::SetState.md)|Устанавливает состояние текущего управления "Индикатор выполнения".|  
|[CProgressCtrl::SetStep](../Topic/CProgressCtrl::SetStep.md)|Указывает приращение шага для управления "Индикатор выполнения".|  
|[CProgressCtrl::StepIt](../Topic/CProgressCtrl::StepIt.md)|Перемещает текущую позицию для управления "Индикатор выполнения" шагом этапа \(см. [SetStep](../Topic/CProgressCtrl::SetStep.md)\) и перерисовывает панель, чтобы отразить новое положение.|  
  
## Заметки  
 Элемент управления "Индикатор выполнения" окно, приложение может использовать для отображения хода выполнения длительной операции.  Он состоит из прямоугольника, который постепенно заполняется из левого направо с цветом выделения системы по мере выполнения операции.  
  
 Элемент управления "Индикатор выполнения" имеет диапазон и текущую позицию.  Диапазон, представляющий полную длительность операций и текущая позиция представляющий ход выполнения приложение делало к выполнению операции.  Процедура окна используется текущая позиция диапазона и указать процент индикатора выполнения, чтобы заполнить цветом выделения.  Поскольку выражаются значения диапазона и текущей позиции как знаковые целые числа, возможно, диапазон значений текущей позиции от – 2.147.483.648 до 2.147.483.647 инклюзивных.  
  
 Дополнительные сведения об использовании `CProgressCtrl` см. в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CProgressCtrl](../../mfc/using-cprogressctrl.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CProgressCtrl`  
  
## Требования  
 **заголовок:**  afxcmn.h  
  
## См. также  
 [Образец CMNCTRL2 MFC](../../top/visual-cpp-samples.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)