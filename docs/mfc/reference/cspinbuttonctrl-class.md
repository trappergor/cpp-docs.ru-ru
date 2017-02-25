---
title: "CSpinButtonCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSpinButtonCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSpinButtonCtrl class"
  - "CSpinButtonCtrl class, стандартные элементы управления"
  - "счетчик - элемент управления"
  - "поля со стрелками "вверх/вниз", счетчик - элемент управления"
  - "Windows common controls [C++], CSpinButtonCtrl"
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CSpinButtonCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональность элемент управления "Кнопка" общие "счетчик" Windows.  
  
## Синтаксис  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](../Topic/CSpinButtonCtrl::CSpinButtonCtrl.md)|Создает объект `CSpinButtonCtrl`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSpinButtonCtrl::Create](../Topic/CSpinButtonCtrl::Create.md)|Создает элемент управления "Кнопка" и "счетчик" вложение его к объекту `CSpinButtonCtrl`.|  
|[CSpinButtonCtrl::CreateEx](../Topic/CSpinButtonCtrl::CreateEx.md)|Создает элемент управления "Кнопка" прокруток с указанными стилей расширенными Windows и вложение его к объекту `CSpinButtonCtrl`.|  
|[CSpinButtonCtrl::GetAccel](../Topic/CSpinButtonCtrl::GetAccel.md)|Извлекает сведения о ускорения для элемента управления "Кнопка", "счетчик".|  
|[CSpinButtonCtrl::GetBase](../Topic/CSpinButtonCtrl::GetBase.md)|Извлекает текущий базы для элемента управления "Кнопка", "счетчик".|  
|[CSpinButtonCtrl::GetBuddy](../Topic/CSpinButtonCtrl::GetBuddy.md)|Извлекает указатель на текущий окно приятеля.|  
|[CSpinButtonCtrl::GetPos](../Topic/CSpinButtonCtrl::GetPos.md)|Получает текущую позицию элемента управления "Кнопка", "счетчик".|  
|[CSpinButtonCtrl::GetRange](../Topic/CSpinButtonCtrl::GetRange.md)|Извлекает верхнее и нижнее ограничение \(диапазон\), элемент управления "Кнопка", "счетчик".|  
|[CSpinButtonCtrl::SetAccel](../Topic/CSpinButtonCtrl::SetAccel.md)|Устанавливает ускорение для элемента управления "Кнопка", "счетчик".|  
|[CSpinButtonCtrl::SetBase](../Topic/CSpinButtonCtrl::SetBase.md)|Устанавливает базу для элемента управления "Кнопка", "счетчик".|  
|[CSpinButtonCtrl::SetBuddy](../Topic/CSpinButtonCtrl::SetBuddy.md)|Устанавливает окно приятеля, элемент управления "Кнопка", "счетчик".|  
|[CSpinButtonCtrl::SetPos](../Topic/CSpinButtonCtrl::SetPos.md)|Задает текущую позицию элемента управления.|  
|[CSpinButtonCtrl::SetRange](../Topic/CSpinButtonCtrl::SetRange.md)|Устанавливает верхнее и нижнее ограничение \(диапазон\), элемент управления "Кнопка", "счетчик".|  
  
## Заметки  
 "Элемент управления "Кнопка" прокруток" \(также известное как элемент управления " вверх\-вниз "\) пару кнопок со стрелками, которые пользователь может щелкнуть для увеличения или уменьшения значение, например позицию прокрутки или число отображаемых в элементе управления сопровождающий.  Значение, связанное с элементом управления "Кнопка", "счетчик" вызываются своим текущим положением.  Элемент управления "Кнопка" прокруток наиболее часто используется с окном, сопровождающий управления с именем "приятеля".  
  
 Этот элемент управления \(и, следовательно, класс `CSpinButtonCtrl` \) доступны только для программ, выполняемых в рамках \/98 Windows версии 3.51 и Windows NT 95 и более поздних версий.  
  
 Пользователю, элемент управления "Кнопка", "счетчик" и его окно приятеля часто выглядеть как отдельный элемент управления.  Можно указать, что элемент управления "Кнопка", "счетчик" автоматически располагает рядом с полем приятеля и что оно автоматически, для заголовок окна приятеля в его текущей позиции.  Можно использовать элемент управления "Кнопка" прокруток с элементом управления "Поле ввода" для запроса пользователя для числовых входных данных.  
  
 При нажатии стрелки перемещает текущую позицию, с помощью хранимой процедуры и щелкните стрелку перемещает текущую позицию минимальным.  По умолчанию минимальное значение 100, а максимальное \- 0.  Каждый раз, когда параметр min больше, чем значение параметра max \(например, когда использоваться параметры по умолчанию\), щелкните стрелку вверх уменьшает значение позиции и нижнего выносных элементов щелкните увеличения стрелки.  
  
 Элемент управления "Кнопка", "счетчик" без окна приятеля функций, таких как сортировка упрощенной полосы прокрутки.  Например, набор вкладок, иногда отображает элемент управления "Кнопка" прокруток для разрешения пользователя для прокрутки дополнительные вкладки в представление.  
  
 Дополнительные сведения об использовании `CSpinButtonCtrl` см. в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CSpinButtonCtrl`  
  
## Требования  
 **Header:**  afxcmn.h  
  
## См. также  
 [MFC просматривает CMNCTRL2](../../top/visual-cpp-samples.md)   
 [Класс CWnd](../Topic/CWnd%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl Class](../../mfc/reference/csliderctrl-class.md)