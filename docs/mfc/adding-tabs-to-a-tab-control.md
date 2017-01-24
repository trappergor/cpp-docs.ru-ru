---
title: "Добавление вкладок в элемент управления &quot;Вкладка&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CTabCtrl - класс, добавление вкладок"
  - "размещение вкладок на CTabCtrls"
  - "элементы управления вкладка, добавление вкладок"
  - "вкладки, добавление в класс CTabCtrl"
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Добавление вкладок в элемент управления &quot;Вкладка&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

После создания элемента управления "вкладка" \([CTabCtrl](../Topic/CTabCtrl%20Class.md)\), добавьте необходимое количество вкладок, сколько требуется.  
  
### Добавление элемента вкладки  
  
1.  Подготовка структуры [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554).  
  
2.  Вызов [CTabCtrl::InsertItem](../Topic/CTabCtrl::InsertItem.md), передав структуру.  
  
3.  Повторяющийся шаги 1 и 2 для дополнительных элементов вкладки.  
  
 Дополнительные сведения см. в разделе [Создание элемента управления "вкладка"](http://msdn.microsoft.com/library/windows/desktop/bb760550) в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## См. также  
 [Использование CTabCtrl](../mfc/using-ctabctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)