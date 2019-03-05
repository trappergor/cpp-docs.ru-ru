---
title: Способы создания всплывающих подсказок
ms.date: 11/04/2016
helpviewer_keywords:
- CToolTipCtrl class [MFC], creating tool tips
- tool tips [MFC], tool tip controls
- tool tips [MFC], creating
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
ms.openlocfilehash: 2ba935f52f24f62dded3b89df1563454cf7e0335
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276719"
---
# <a name="methods-of-creating-tool-tips"></a>Способы создания всплывающих подсказок

MFC предоставляет три класса для создания и управления всплывающая подсказка. [CWnd](../mfc/reference/cwnd-class.md), [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md), [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) и [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md). Функции-члены совет средства в этих классах, wrap общего элемента управления Windows API. Класс `CToolBarCtrl` и класс `CToolTipCtrl` являются производными от класса `CWnd`.

`CWnd` предоставляет четыре функции-члены для создания и управления всплывающих подсказок: [EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips), [CancelToolTips](../mfc/reference/cwnd-class.md#canceltooltips), [FilterToolTipMessage](../mfc/reference/cwnd-class.md#filtertooltipmessage), и [OnToolHitTest](../mfc/reference/cwnd-class.md#ontoolhittest). См. в статье эти функции-члены отдельных Дополнительные сведения о том, как они реализуют всплывающие подсказки.

Если вы создаете панели инструментов с помощью `CToolBarCtrl`, вы можете реализовать всплывающие подсказки для панели инструментов непосредственно с помощью следующих функций-членов: [GetToolTips](../mfc/reference/ctoolbarctrl-class.md#gettooltips) и [SetToolTips](../mfc/reference/ctoolbarctrl-class.md#settooltips). См. в статье эти функции отдельных членов и [обработка уведомлений всплывающих совет](../mfc/handling-tool-tip-notifications.md) Дополнительные сведения о том, как они реализуют всплывающие подсказки.

`CToolTipCtrl` Класс предоставляет функциональные возможности Windows распространенных всплывающая подсказка. Единый всплывающая подсказка может предоставить сведения для более одного средства. Это средство — либо это окно, такие как дочернего окна элемента управления или определяемые приложением прямоугольная область в клиентской области окна. [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md) класс является производным от `CToolTipCtrl` и предоставляет дополнительные стили оформления и функциональные возможности.

## <a name="see-also"></a>См. также

[Использование CToolTipCtrl](../mfc/using-ctooltipctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
