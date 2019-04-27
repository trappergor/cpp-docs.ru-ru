---
title: Управление элементом управления всплывающей подсказки
ms.date: 11/04/2016
helpviewer_keywords:
- CToolTipCtrl class [MFC], manipulating tool tip attributes
- tool tips [MFC], attributes
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
ms.openlocfilehash: d8c994748239871f17b878dd8ea7505a2a8a0b65
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226161"
---
# <a name="manipulating-the-tool-tip-control"></a>Управление элементом управления всплывающей подсказки

Класс `CToolTipCtrl` предоставляет функции, которые управляют различных атрибутов группы член `CToolTipCtrl` объекта и окно подсказки.

Начальный, всплывающее окно и reshow длительность для окна подсказки можно задавать и получать с вызовами [GetDelayTime](../mfc/reference/ctooltipctrl-class.md#getdelaytime) и [SetDelayTime](../mfc/reference/ctooltipctrl-class.md#setdelaytime).

Изменение внешнего вида окна подсказки со следующими функциями:

- [GetMargin](../mfc/reference/ctooltipctrl-class.md#getmargin) и [SetMargin](../mfc/reference/ctooltipctrl-class.md#setmargin) получает и задает текст подсказки ширину между границы подсказки инструментов и средства.

- [GetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#getmaxtipwidth) и [SetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#setmaxtipwidth) получает и задает максимальную ширину средство совет окна.

- [GetTipBkColor](../mfc/reference/ctooltipctrl-class.md#gettipbkcolor) и [SetTipBkColor](../mfc/reference/ctooltipctrl-class.md#settipbkcolor) получает и задает цвет фона средства окно подсказок.

- [GetTipTextColor](../mfc/reference/ctooltipctrl-class.md#gettiptextcolor) и [SetTipTextColor](../mfc/reference/ctooltipctrl-class.md#settiptextcolor) получает и задает цвет текста, средства окно подсказок.

В порядке для управления всплывающей подсказки получать уведомления о важных сообщений, например сообщений WM_LBUTTONXXX должен пересылать сообщения для вашей всплывающая подсказка. Лучшим способом для этого ретранслятора является для выполнения вызова к [CToolTipCtrl::RelayEvent](../mfc/reference/ctooltipctrl-class.md#relayevent)в `PreTranslateMessage` функции окна-владельца. В следующем примере показано одно из возможных способов (при условии, что он вызывается `m_ToolTip`):

[!code-cpp[NVC_MFCControlLadenDialog#41](../mfc/codesnippet/cpp/manipulating-the-tool-tip-control_1.cpp)]

Чтобы немедленно удалить окно подсказки, вызовите [Pop](../mfc/reference/ctooltipctrl-class.md#pop) функция-член.

## <a name="see-also"></a>См. также

[Использование CToolTipCtrl](../mfc/using-ctooltipctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
