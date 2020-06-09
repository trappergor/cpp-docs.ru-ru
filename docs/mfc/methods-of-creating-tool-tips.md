---
title: Способы создания всплывающих подсказок
ms.date: 11/04/2016
helpviewer_keywords:
- CToolTipCtrl class [MFC], creating tool tips
- tool tips [MFC], tool tip controls
- tool tips [MFC], creating
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
ms.openlocfilehash: 26f31705068df009e906d50451efa9ea6572d7e6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625458"
---
# <a name="methods-of-creating-tool-tips"></a>Способы создания всплывающих подсказок

MFC предоставляет три класса для создания и управления всплывающей подсказкой: [CWnd](reference/cwnd-class.md), [CToolBarCtrl](reference/ctoolbarctrl-class.md), [CToolTipCtrl](reference/ctooltipctrl-class.md) и [кмфктултипктрл](reference/cmfctooltipctrl-class.md). Функции-члены подсказок в этих классах служат оболочкой для API-интерфейса Windows Common Control. Класс `CToolBarCtrl` и класс `CToolTipCtrl` являются производными от класса `CWnd` .

`CWnd`предоставляет четыре функции элементов для создания советов и управления ими: [енаблетултипс](reference/cwnd-class.md#enabletooltips), [канцелтултипс](reference/cwnd-class.md#canceltooltips), [филтертултипмессаже](reference/cwnd-class.md#filtertooltipmessage)и [онтулхиттест](reference/cwnd-class.md#ontoolhittest). Дополнительные сведения о том, как они реализуют подсказки, см. в этих отдельных функциях элементов.

Если вы создаете панель инструментов с помощью `CToolBarCtrl` , вы можете реализовать подсказки для этой панели инструментов непосредственно, используя следующие функции-члены: [подсказки](reference/ctoolbarctrl-class.md#gettooltips) и [сеттултипс](reference/ctoolbarctrl-class.md#settooltips). Дополнительные сведения о том, как они реализуют советы, см. в статье отдельные функции участников и [обработка уведомлений с помощью всплывающих подсказок](handling-tool-tip-notifications.md) .

`CToolTipCtrl`Класс предоставляет функциональные возможности элемента управления Windows Common Tool подсказки. Один элемент управления "всплывающая подсказка" может предоставлять сведения для нескольких инструментов. Инструмент — это либо окно, например дочернее окно, либо элемент управления, либо определяемая приложением прямоугольная область в клиентской области окна. Класс [кмфктултипктрл](reference/cmfctooltipctrl-class.md) является производным от `CToolTipCtrl` и предоставляет дополнительные визуальные стили и функции.

## <a name="see-also"></a>См. также раздел

[Использование CToolTipCtrl](using-ctooltipctrl.md)<br/>
[Элементы управления](controls-mfc.md)
