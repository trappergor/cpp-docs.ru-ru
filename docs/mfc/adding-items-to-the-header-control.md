---
title: "Добавление элементов в элемент управления &quot;Заголовок&quot; | Microsoft Docs"
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
  - "CHeaderCtrl - класс, добавление элементов"
  - "элементы управления [MFC], заголовок"
  - "элементы управления "заголовок", добавление элементов"
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Добавление элементов в элемент управления &quot;Заголовок&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

После создания элемент управления " Заголовок " \([CHeaderCtrl](../Topic/CHeaderCtrl%20Class.md)\) в текущем родительском окне добавьте столько элементов «title», сколько требуется. обычно в один столбец.  
  
### Добавление элемента заголовка  
  
1.  Подготовка структуры [HD\_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247).  
  
2.  Вызов [CHeaderCtrl::InsertItem](../Topic/CHeaderCtrl::InsertItem.md), передав структуру.  
  
3.  Повторяющийся шаги 1 и 2 для дополнительных вопросов.  
  
 Дополнительные сведения см. в разделе [Добавление элемента в элемент управления " Заголовок "](http://msdn.microsoft.com/library/windows/desktop/bb775238) в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)