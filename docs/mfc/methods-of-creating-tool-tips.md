---
title: "Способы создания всплывающих подсказок | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CToolTipCtrl class [MFC], creating tool tips
- tool tips [MFC], tool tip controls
- tool tips [MFC], creating
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c2d38bd76ff5c8d06daf474cf1c1dcc0286183bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="methods-of-creating-tool-tips"></a>Способы создания всплывающих подсказок
MFC предоставляет три класса для создания и управления ими средства элемента управления подсказки: [CWnd](../mfc/reference/cwnd-class.md), [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md), [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) и [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md). Функции-члены совет средства в этих классах, перенос общих элементов управления Windows API. Класс `CToolBarCtrl` и класс `CToolTipCtrl` являются производными от класса `CWnd`.  
  
 `CWnd`предоставляет четыре функции-члены для создания и управления всплывающие подсказки: [EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips), [CancelToolTips](../mfc/reference/cwnd-class.md#canceltooltips), [FilterToolTipMessage](../mfc/reference/cwnd-class.md#filtertooltipmessage), и [ OnToolHitTest](../mfc/reference/cwnd-class.md#ontoolhittest). См. Эти функции-члены отдельных Дополнительные сведения о том, как они реализуют всплывающие подсказки.  
  
 При создании панели инструментов с помощью `CToolBarCtrl`, можно реализовать всплывающие подсказки для панели инструментов непосредственно с помощью следующих функций-членов: [GetToolTips](../mfc/reference/ctoolbarctrl-class.md#gettooltips) и [SetToolTips](../mfc/reference/ctoolbarctrl-class.md#settooltips). Просмотреть эти функции отдельных членов и [обработка уведомлений всплывающих совет](../mfc/handling-tool-tip-notifications.md) Дополнительные сведения о том, как они реализуют всплывающие подсказки.  
  
 `CToolTipCtrl` Класс предоставляет функциональные возможности элемента управления Windows общих всплывающая подсказка. Всплывающая подсказка одного могут предоставить сведения для более чем одного набора инструментов. Это средство — либо это окно, такие как дочернего окна элемента управления или определяемые приложением прямоугольная область в клиентской области окна. [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md) класс является производным от `CToolTipCtrl` и предоставляет дополнительные стили оформления и функциональные возможности.  
  
## <a name="see-also"></a>См. также  
 [Использование CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

