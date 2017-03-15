---
title: "Использование CToolTipCtrl для создания объекта CToolTipCtrl и управления им | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolTipCtrl - класс, использование"
  - "всплывающие подсказки [C++], создание"
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Использование CToolTipCtrl для создания объекта CToolTipCtrl и управления им
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ниже приведен пример потребления [CToolTipCtrl](../Topic/CToolTipCtrl%20Class.md):  
  
### Создание и управление CToolTipCtrl  
  
1.  Создайте объект `CToolTipCtrl`.  
  
2.  Вызовите метод [Создать](../Topic/CToolTipCtrl::Create.md), чтобы создать общий элемент управления всплывающей подсказки Windows и вложить его в объект `CToolTipCtrl`.  
  
3.  Вызовите метод [AddTool](../Topic/CToolTipCtrl::AddTool.md), чтобы зарегистрировать средство с элементом управления всплывающей подсказки, будут выведены сведения, хранящиеся во всплывающей подсказке, когда курсор в средстве.  
  
4.  Вызовите [SetToolInfo](../Topic/CToolTipCtrl::SetToolInfo.md) для задания информации о подсказке поддержку для средства.  
  
5.  Вызовите [SetToolRect](../Topic/CToolTipCtrl::SetToolRect.md) для задания нового ограничивающего прямоугольника для средства.  
  
6.  Вызовите [HitTest](../Topic/CToolTipCtrl::HitTest.md) для выполнения точку, чтобы определить, является ли она внутри ограничивающего прямоугольника заданного средства и, если да, извлечь сведения о средстве.  
  
7.  Вызовите [GetToolCount](../Topic/CToolTipCtrl::GetToolCount.md) для получения количества зарегистрированных средств с элементом управления всплывающей подсказки.  
  
## См. также  
 [Использование CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)