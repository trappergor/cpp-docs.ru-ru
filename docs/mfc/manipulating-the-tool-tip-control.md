---
title: "Управление элементом управления всплывающей подсказки | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolTipCtrl - класс, управление атрибутами всплывающей подсказки"
  - "всплывающие подсказки [C++], атрибуты"
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Управление элементом управления всплывающей подсказки
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс `CToolTipCtrl` предоставляет группу в составе функции\-члены, элемент управления другие атрибуты объекта `CToolTipCtrl` и окна всплывающей подсказки.  
  
 Длительность начальных контекстного меню, и reshow для окон всплывающей подсказки можно задавать и получать с вызовом функции [GetDelayTime](../Topic/CToolTipCtrl::GetDelayTime.md) и [SetDelayTime](../Topic/CToolTipCtrl::SetDelayTime.md).  
  
 Изменение внешнего вида окна всплывающей подсказки со следующими функциями:  
  
-   [GetMargin](../Topic/CToolTipCtrl::GetMargin.md) [SetMargin](../Topic/CToolTipCtrl::SetMargin.md) извлекает и и задает ширину всплывающей подсказки между границей и текстом всплывающей подсказки.  
  
-   [GetMaxTipWidth](../Topic/CToolTipCtrl::GetMaxTipWidth.md) [SetMaxTipWidth](../Topic/CToolTipCtrl::SetMaxTipWidth.md) и получает и задает максимальную ширину окна всплывающей подсказки.  
  
-   [GetTipBkColor](../Topic/CToolTipCtrl::GetTipBkColor.md) [SetTipBkColor](../Topic/CToolTipCtrl::SetTipBkColor.md) извлекает и и задает цвет фона окна всплывающей подсказки.  
  
-   [GetTipTextColor](../Topic/CToolTipCtrl::GetTipTextColor.md) [SetTipTextColor](../Topic/CToolTipCtrl::SetTipTextColor.md) извлекает и и задает цвет текста окна всплывающей подсказки.  
  
 Элемент управления всплывающей подсказки для того, чтобы сообщить важных сообщений, например сообщения **WM\_LBUTTONXXX**, реле сообщения в элемент управления всплывающей подсказки.  Лучший метод для этого реле позвонить в [CToolTipCtrl::RelayEvent](../Topic/CToolTipCtrl::RelayEvent.md), в функции `PreTranslateMessage` окна ".  В следующем примере показан один из возможных метод \(беря на себя элемент управления всплывающей подсказки вызывает `m_ToolTip`\).  
  
 [!code-cpp[NVC_MFCControlLadenDialog#41](../mfc/codesnippet/CPP/manipulating-the-tool-tip-control_1.cpp)]  
  
 Немедленно, чтобы убрать окно всплывающей подсказки, вызовите функцию\-член [Поп](../Topic/CToolTipCtrl::Pop.md).  
  
## См. также  
 [Использование CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)