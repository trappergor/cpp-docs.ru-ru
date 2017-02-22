---
title: "Элементы заголовка в элементе управления &quot;Заголовок&quot; | Microsoft Docs"
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
  - "CHeaderCtrl - класс, элементы заголовка в"
  - "элементы управления [MFC], заголовок"
  - "элементы управления "заголовок", элементы заголовка в"
  - "элементы заголовка в элементах управления заголовка"
ms.assetid: ac79ef1f-a671-4ab2-93e9-b1aa016a48bf
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Элементы заголовка в элементе управления &quot;Заголовок&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Имеется значительный элемент управления над внешним видом и расширением функциональности элементов заголовка, составляющих элемент управления " Заголовок " \([CHeaderCtrl](../Topic/CHeaderCtrl%20Class.md)\).  Каждый элемент заголовка может получить строку, bitmapped изображение, изображение из связанного списка изображений или определенное приложением 32 бит значение, связанное с ним.  Строка, растровое изображение или изображение отображаются в элементе заголовка.  
  
 Можно настраивать внешний вид и содержимое новых элементов, когда они создаются вызовом [CHeaderCtrl::InsertItem](../Topic/CHeaderCtrl::InsertItem.md) или путем изменения существующего элемента, вызвав метод [CHeaderCtrl::GetItem](../Topic/CHeaderCtrl::GetItem.md) и [CHeaderCtrl::SetItem](../Topic/CHeaderCtrl::SetItem.md).  
  
## Дополнительные сведения  
  
-   [Настраивать внешний вид элемента заголовка](../Topic/Customizing%20the%20Header%20Item's%20Appearance.md)  
  
-   [Порядок элементов в элементе управления " Заголовок "](../mfc/ordering-items-in-the-header-control.md)  
  
-   [Предоставление поддержки перетаскивания элементов заголовка](../mfc/providing-drag-and-drop-support-for-header-items.md)  
  
-   [Использование списков изображений с элементами управления Заголовок](../mfc/using-image-lists-with-header-controls.md)  
  
## См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)