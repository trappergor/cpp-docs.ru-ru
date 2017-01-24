---
title: "CSliderCtrl Class | Microsoft Docs"
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
  - "CSliderCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSliderCtrl class"
  - "CSliderCtrl class, стандартные элементы управления"
  - "элементы управления "Ползунок", CSliderCtrl class"
  - "Windows common controls [C++], CSliderCtrl"
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSliderCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональность общего управления "ползунок" Windows.  
  
## Синтаксис  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSliderCtrl::CSliderCtrl](../Topic/CSliderCtrl::CSliderCtrl.md)|Создает объект `CSliderCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSliderCtrl::ClearSel](../Topic/CSliderCtrl::ClearSel.md)|Очищает текущее выделение в элементе управления "ползунок".|  
|[CSliderCtrl::ClearTics](../Topic/CSliderCtrl::ClearTics.md)|Удаляет текущие деления из элемента управления "ползунок".|  
|[CSliderCtrl::Create](../Topic/CSliderCtrl::Create.md)|Создает элемент управления "ползунок" и вложение его к объекту `CSliderCtrl`.|  
|[CSliderCtrl::CreateEx](../Topic/CSliderCtrl::CreateEx.md)|Создает элемент управления "ползунок" с заданными стилей расширенными Windows и вложение его к объекту `CSliderCtrl`.|  
|[CSliderCtrl::GetBuddy](../Topic/CSliderCtrl::GetBuddy.md)|Получает дескриптор для окна приятеля элемента управления "ползунок" в заданную позицию.|  
|[CSliderCtrl::GetChannelRect](../Topic/CSliderCtrl::GetChannelRect.md)|Извлекает размер канала элемента управления "ползунок".|  
|[CSliderCtrl::GetLineSize](../Topic/CSliderCtrl::GetLineSize.md)|Извлекает размер линии управления "ползунок".|  
|[CSliderCtrl::GetNumTics](../Topic/CSliderCtrl::GetNumTics.md)|Извлекает число делений в элементе управления "ползунок".|  
|[CSliderCtrl::GetPageSize](../Topic/CSliderCtrl::GetPageSize.md)|Получает размер страницы управления "ползунок".|  
|[CSliderCtrl::GetPos](../Topic/CSliderCtrl::GetPos.md)|Извлекает текущее положение ползунка.|  
|[CSliderCtrl::GetRange](../Topic/CSliderCtrl::GetRange.md)|Получает минимальную и максимальную позиции ползунка.|  
|[CSliderCtrl::GetRangeMax](../Topic/CSliderCtrl::GetRangeMax.md)|Получает максимальную позиция для ползунка.|  
|[CSliderCtrl::GetRangeMin](../Topic/CSliderCtrl::GetRangeMin.md)|Извлекает минимальная позиция для ползунка.|  
|[CSliderCtrl::GetSelection](../Topic/CSliderCtrl::GetSelection.md)|Получает диапазон текущего выделения.|  
|[CSliderCtrl::GetThumbLength](../Topic/CSliderCtrl::GetThumbLength.md)|Получает размер ползунка в текущем элементе управления trackbar.|  
|[CSliderCtrl::GetThumbRect](../Topic/CSliderCtrl::GetThumbRect.md)|Извлекает размер бегунка элемента управления "ползунок".|  
|[CSliderCtrl::GetTic](../Topic/CSliderCtrl::GetTic.md)|Извлекает индекс заданного деления.|  
|[CSliderCtrl::GetTicArray](../Topic/CSliderCtrl::GetTicArray.md)|Извлекает массив позиций деления для управления "ползунок".|  
|[CSliderCtrl::GetTicPos](../Topic/CSliderCtrl::GetTicPos.md)|Извлекает индекс заданного деления в клиентских координатах.|  
|[CSliderCtrl::GetToolTips](../Topic/CSliderCtrl::GetToolTips.md)|Получает дескриптор для элемента управления tooltip присвоенному к элементу управления "ползунок", если таковые имеются.|  
|[CSliderCtrl::SetBuddy](../Topic/CSliderCtrl::SetBuddy.md)|Присвоит окно как окно приятеля для управления "ползунок".|  
|[CSliderCtrl::SetLineSize](../Topic/CSliderCtrl::SetLineSize.md)|Задает размер линий управления "ползунок".|  
|[CSliderCtrl::SetPageSize](../Topic/CSliderCtrl::SetPageSize.md)|Задает размер страницы управления "ползунок".|  
|[CSliderCtrl::SetPos](../Topic/CSliderCtrl::SetPos.md)|Задает текущее положение ползунка.|  
|[CSliderCtrl::SetRange](../Topic/CSliderCtrl::SetRange.md)|Устанавливает минимальную и максимальную позиции ползунка.|  
|[CSliderCtrl::SetRangeMax](../Topic/CSliderCtrl::SetRangeMax.md)|Задает максимальную позицию ползунка.|  
|[CSliderCtrl::SetRangeMin](../Topic/CSliderCtrl::SetRangeMin.md)|Устанавливает минимальную позицию ползунка.|  
|[CSliderCtrl::SetSelection](../Topic/CSliderCtrl::SetSelection.md)|Устанавливает расстояние текущего выделения.|  
|[CSliderCtrl::SetThumbLength](../Topic/CSliderCtrl::SetThumbLength.md)|Устанавливает длину ползунка в текущем элементе управления trackbar.|  
|[CSliderCtrl::SetTic](../Topic/CSliderCtrl::SetTic.md)|Устанавливает позицию указанного деления.|  
|[CSliderCtrl::SetTicFreq](../Topic/CSliderCtrl::SetTicFreq.md)|Задает частоту делений на увеличение элемента управления "ползунок".|  
|[CSliderCtrl::SetTipSide](../Topic/CSliderCtrl::SetTipSide.md)|Элемент управления trackbar располагает подсказки, используемый элементом управления.|  
|[CSliderCtrl::SetToolTips](../Topic/CSliderCtrl::SetToolTips.md)|Присвоит элемент управления всплывающей подсказки для элемента управления "ползунок".|  
  
## Заметки  
 Элемент управления "ползунок" \(также называемый trackbar\) окно, содержащее ползунок и деления необязательно.  Когда пользователь перемещает ползунка с помощью мыши или ключи направления элемент управления отправляют сообщения уведомления для отображения изменений.  
  
 Элементы управления "ползунок" полезны, когда пользователь должен выбрать дискретное значение или набор последовательных значений в диапазоне.  Например, можно использовать элемент управления "ползунок", чтобы позволить пользователю устанавливать версию повторения клавиатуры, перемещая ползунок с заданным делению.  
  
 Этот элемент управления \(и, следовательно, класс `CSliderCtrl` \) доступны только для программ, выполняемых в рамках \/98 Windows версии 3.51 и Windows NT 95 и более поздних версий.  
  
 Ползунок перемещает с шагом, которые можно указать при его создании.  Например, если указать, что ползунок должен иметь диапазон 5, ползунок может находиться только 6 позиций. положение слева управления "ползунок" и одну позицию для каждого шага диапазона.  Обычно каждая из этих позиций соответствии с делением.  
  
 Создании ползунок с помощью конструктора и функции\-члена **Создать**`CSliderCtrl`.  После создания элемента управления "ползунок" можно с помощью функций\-членов в `CSliderCtrl` изменять многие из своих свойств.  Изменяет что можно сделать, чтобы включить устанавливать минимальное и максимальное позиции для рисования ползунка, деления, устанавливать диапазон выделения и изменения положения ползунка.  
  
 Дополнительные сведения об использовании `CSliderCtrl` см. в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CSliderCtrl`  
  
## Требования  
 **Header:**  afxcmn.h  
  
## См. также  
 [MFC просматривает CMNCTRL2](../../top/visual-cpp-samples.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl Class](../../mfc/reference/cprogressctrl-class.md)