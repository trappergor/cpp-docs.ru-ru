---
title: "Параметры элемента управления &quot;Индикатор выполнения&quot; | Microsoft Docs"
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
  - "CProgressCtrl - класс, параметры"
  - "элементы управления хода выполнения [C++], параметры"
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Параметры элемента управления &quot;Индикатор выполнения&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Базовые параметры для контроля за ходом выполнения \([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)\) и текущая позиция диапазона.  Представляет диапазон всю длительность операций.  Текущая позиция представляет ход выполнения, приложение делало в выполнении операции.  Все изменения в диапазон или причины позиции элемент управления ходом выполнения, чтобы redraw.  
  
 По умолчанию диапазон — 0 — 100 и первоначальная позиция задано значение 0.  Для извлечения текущих параметров диапазона для контроля за ходом выполнения используйте функции\-члена [GetRange](../Topic/CProgressCtrl::GetRange.md).  Чтобы изменить диапазон, используйте функции\-члена [SetRange](../Topic/CProgressCtrl::SetRange.md).  
  
 Чтобы установить позицию, используйте [SetPos](../Topic/CProgressCtrl::SetPos.md).  Для извлечения текущая позиция без указания новое значение используйте функцию [GetPos](../Topic/CProgressCtrl::GetPos.md).  Например, может потребоваться в простой запрос на состояние текущей операции.  
  
 Для перемещения текущая позиция контроля за ходом выполнения используйте [StepIt](../Topic/CProgressCtrl::StepIt.md).  Чтобы задать количество каждого шага используйте [SetStep](../Topic/CProgressCtrl::SetStep.md)  
  
## См. также  
 [Использование CProgressCtrl](../mfc/using-cprogressctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)