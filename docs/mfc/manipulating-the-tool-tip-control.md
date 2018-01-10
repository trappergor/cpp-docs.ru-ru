---
title: "Управление элементом управления всплывающей подсказки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CToolTipCtrl class [MFC], manipulating tool tip attributes
- tool tips [MFC], attributes
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ae30c39a26379aaa8a6f786b5fe2542abde2c2df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="manipulating-the-tool-tip-control"></a>Управление элементом управления всплывающей подсказки
Класс `CToolTipCtrl` предоставляет функции, которые управляют различных атрибутов из группы члена `CToolTipCtrl` объекта и подсказки.  
  
 Начальный, всплывающее окно и reshow длительности для подсказки окна инструментов можно задавать и получать с помощью вызова к [GetDelayTime](../mfc/reference/ctooltipctrl-class.md#getdelaytime) и [SetDelayTime](../mfc/reference/ctooltipctrl-class.md#setdelaytime).  
  
 Изменение внешнего вида окна подсказка со следующими функциями:  
  
-   [GetMargin](../mfc/reference/ctooltipctrl-class.md#getmargin) и [SetMargin](../mfc/reference/ctooltipctrl-class.md#setmargin) получает и задает расстояние между границей совет инструментов и средство текст подсказки.  
  
-   [GetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#getmaxtipwidth) и [SetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#setmaxtipwidth) получает и задает максимальную ширину средства окно подсказок.  
  
-   [GetTipBkColor](../mfc/reference/ctooltipctrl-class.md#gettipbkcolor) и [SetTipBkColor](../mfc/reference/ctooltipctrl-class.md#settipbkcolor) получает и задает цвет фона средства окно подсказок.  
  
-   [GetTipTextColor](../mfc/reference/ctooltipctrl-class.md#gettiptextcolor) и [SetTipTextColor](../mfc/reference/ctooltipctrl-class.md#settiptextcolor) получает и задает цвет текста средства окно подсказок.  
  
 В порядке для управления всплывающей подсказки получать уведомления о важных сообщений, таких как **WM_LBUTTONXXX** сообщений, должен пересылать сообщения для вашего управления всплывающей подсказки. Наилучший способ это ретрансляции требуется вызвать [CToolTipCtrl::RelayEvent](../mfc/reference/ctooltipctrl-class.md#relayevent)в `PreTranslateMessage` функция окна-владельца. В следующем примере показан один из возможных способов (предполагается, что всплывающая подсказка называется `m_ToolTip`):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#41](../mfc/codesnippet/cpp/manipulating-the-tool-tip-control_1.cpp)]  
  
 Чтобы немедленно удалить подсказки, вызовите [Pop](../mfc/reference/ctooltipctrl-class.md#pop) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Использование CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

