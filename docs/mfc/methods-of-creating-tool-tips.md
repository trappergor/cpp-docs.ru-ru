---
title: "Способы создания всплывающих подсказок | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolTipCtrl - класс, всплывающие подсказки - создание"
  - "всплывающие подсказки [C++], создание"
  - "всплывающие подсказки [C++], элементы управления всплывающих подсказок"
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Способы создания всплывающих подсказок
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC предоставляет 3 класса для создания и управления элемент управления всплывающей подсказки. [CWnd](../Topic/CWnd%20Class.md), [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md), [CToolTipCtrl](../Topic/CToolTipCtrl%20Class.md) и [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md).  Функции\-члены всплывающей подсказки в этих классах создания API общего элемента управления Windows.  Класс `CToolBarCtrl` и класс `CToolTipCtrl` являются производными от класса `CWnd`.  
  
 `CWnd` предоставляет 4 функции\-члена для создания и управления всплывающие подсказки: [EnableToolTips](../Topic/CWnd::EnableToolTips.md), [CancelToolTips](../Topic/CWnd::CancelToolTips.md), [FilterToolTipMessage](../Topic/CWnd::FilterToolTipMessage.md) и [OnToolHitTest](../Topic/CWnd::OnToolHitTest.md).  В разделе эти функции отдельного участника дополнительные сведения о том, как они реализуют всплывающие подсказки.  
  
 При создании панель инструментов с помощью `CToolBarCtrl`, можно реализовать всплывающие подсказки для этого инструмента непосредственно с помощью следующих функции\-члены. [GetToolTips](../Topic/CToolBarCtrl::GetToolTips.md) и [SetToolTips](../Topic/CToolBarCtrl::SetToolTips.md).  В разделе эти функции [Обрабатывать уведомления всплывающей подсказки](../mfc/handling-tool-tip-notifications.md) и отдельного участника дополнительные сведения о том, как они реализуют всплывающие подсказки.  
  
 Класс `CToolTipCtrl` предоставляет функцию управления всплывающей подсказки Windows ".  Один элемент управления всплывающей подсказки подробные сведения для более чем одного инструмента.  Средство или окно, например дочернее окно или элемент управления или приложением, прямоугольная область в клиентской области окна.  Класс [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md) является производным от `CToolTipCtrl` и предоставляет дополнительные стили и функции.  
  
## См. также  
 [Использование CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)