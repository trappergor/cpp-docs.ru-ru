---
title: "Использование CStatusBarCtrl для создания объекта CStatusBarCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl - класс, создание"
  - "элементы управления строкой состояния, создание"
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование CStatusBarCtrl для создания объекта CStatusBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ниже приведен пример типичного использования [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):  
  
### Использование элемента управления в строке состояния с частями  
  
1.  Создайте объект `CStatusBarCtrl`.  
  
2.  Вызовите [SetMinHeight](../Topic/CStatusBarCtrl::SetMinHeight.md), если требуется указать минимальную высоту области рисования элемента управления строки состояния.  
  
3.  Вызовите метод [SetBkColor](../Topic/CStatusBarCtrl::SetBkColor.md), чтобы задать цвет фона элемента управления в строке состояния.  
  
4.  Вызовите метод [SetParts](../Topic/CStatusBarCtrl::SetParts.md), чтобы задать число частей в элементе управления строки состояния и координату правого края каждой из них.  
  
5.  Вызовите метод [SetText](../Topic/CStatusBarCtrl::SetText.md), чтобы задать текст в определенной части элемента управления в строке состояния.  Сообщение, что часть элемента управления, который был изменен, вызывая его отображения новый текст, когда элемент управления затем получает сообщение `WM_PAINT`.  
  
 В некоторых случаях строку состояния только для отображения линии текста.  В этом случае вызывать в [SetSimple](../Topic/CStatusBarCtrl::SetSimple.md).  Это размещение элемента управления в строке состояния в «простой режим», который указывает отдельную линии текста.  
  
## См. также  
 [Использование CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)